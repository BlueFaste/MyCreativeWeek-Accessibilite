<template>
  <div class="home">
    <Header></Header>
    <div class="px-10rem">

    </div>
    <Footer></Footer>
  </div>
</template>

<script>


import Header from "@/components/Header";
import Footer from "@/components/Footer";
export default {
  name: 'Home',
  components: {
    Footer,
    Header

  }
}
</script>
