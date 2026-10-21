<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import Products from './components/Products.vue'
import LivingRoom from './components/LivingRoom.vue'
import DiningRoom from './components/DiningRoom.vue'
import BedRoom from './components/BedRoom.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Cart from './components/Cart.vue'
import Order from './components/Order.vue'
import Footer from './components/Footer.vue'
import Addproduct from './components/Addproduct.vue'
import Gallery from './components/Gallery.vue'

export default {
  components: {
    Navbar,
    Home,
    About,
    Contact,
    Products,
    LivingRoom,
    BedRoom,
    DiningRoom,
    Cart,
    Order,
    Footer,
    Addproduct,
    Gallery
  },
  data() {
    return {
      currentpage: 'Home',
      currrentSection: 'products',
      addProduct: false,

      addShop: [],
      addKusina: [],
      addKwarto: [],

      addTocart: [],
      orderLists: [],
      totalCartprice: 0,
      categories: 'living'

    }
  }, methods: {
    section(p) {
      this.currentpage = p;
    },

    shops(featured) {
      this.addShop.push[featured];
      this.categories = 'living'
    },
    shops1(featured) {
      this.addShop.push[featured];
      this.categories = 'dining'
    },
  
    shops2(featured) {
      this.addShop.push[featured];
      this.categories = 'bedroom'
    },

    shopsNa(k) {
      this.addKusina.push[k];
    },

    shopsNapod(m) {
      this.addKwarto.push[m];
    },

    pushTocart(index) {
      this.addTocart.push({ ...index });
      this.totalCartprice += index.price;
    },

    pushtoOrder(price, name, img) {
      this.orderLists.push({ ...price, ...name, ...img });
    },

    checkOut() {
      this.totalCartprice = 0;
      this.addTocart = []
    },

    minusan(i) {
      this.totalCartprice -= i;
    },

    modal(a) {
      this.addProduct = a;
    },

    closemodaal(m) {
      this.addProduct = m;
    },

    addP(y, category) {
      if (category === 'living') {
        this.addShop.push(y);
      } else if (category === 'bedroom') {
        this.addKwarto.push(y);
      } else {
        this.addKusina.push(y);
      }
    },
    
    pushToTo(i){
      this.addTocart.push({...i})
      this.totalCartprice += i.price;
    },
    pushToTo2(j){
      this.addTocart.push({...j})
      this.totalCartprice += j.price;
    },
    pushToTo3(l){
      this.addTocart.push({...l})
      this.totalCartprice += l.price;
    },
    navScroll(){
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }

  }
}
</script>

<template>
  <Navbar @click="navScroll" @GoTo="section" />
  <Home v-if="currentpage === 'Home'" />
  <About v-if="currentpage === 'About'" />
  <Contact v-if="currentpage === 'Contact'" />

  <Products v-if="currentpage === 'Products'" @to-shop="shops" @to-shop1="shops1" @to-shop2="shops2" @send-i="pushTocart" @send-l="pushTocart"
    @send-j="pushTocart" @open="modal" :addNew="addShop" :addNapod="addKusina" :addNgani="addKwarto"
    @send-ii="pushToTo" @send-iii="pushToTo2" @send-iiii="pushToTo3" />

  <Cart @checkout="checkOut" @gotoOrder="pushtoOrder" v-if="currentpage === 'Cart'" @minus="minusan"
    :receivedproducts="addTocart" :totalAll=this.totalCartprice />
  <Gallery v-if="currentpage === 'Gallery'" />
  <Order v-if="currentpage === 'Order'" :orderlist="orderLists" />

  <LivingRoom v-if="currrentSection === 'living'" :sendToShop="addShop" />
  <BedRoom v-if="currrentSection === 'bedroom'" :sendtoKwarto="addKwarto" />
  <DiningRoom v-if="currrentSection === 'dining'" :sentoKusina="addKusina" />
  <Footer />
  <Addproduct v-if="addProduct" @close="closemodaal" @addMe="addP" @toCategories="shops" :categori="this.categories" />

</template>
