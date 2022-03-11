<template>
  <Navbar menuItem="Github </>" title="TextUtils" url="https://github.com/CoderFleet/TextUtils-Vue" />
  <Alert v-show="showAlert"/>
  <div class="container my-3">
    <TextForm heading="Enter Text To Analyse" @true="copied"/>
  </div>
  <Footer />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Alert from "./components/Alert.vue";
import TextForm from "./components/TextForm.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  data() {
    return {
      showAlert : false,
    }
  },
  components: {
    TextForm,
    Navbar,
    Alert,
    Footer,
  },
  methods: {
    copied(){
      this.showAlert = !this.showAlert;
      setTimeout(()=>{
        this.showAlert = !this.showAlert;
      }, 1000)
    }
  },
};
</script>

<style>
@import url("https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css");
* {
  font-family: "Poppins";
}
</style>
