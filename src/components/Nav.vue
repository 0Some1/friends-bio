<template>
<!--    <b-container fluid class="align-items-center bg-light rounded-sm mr-1 ml-1">-->
<!--      <b-row  align-v="baseline" class="w-100 p-1">-->
<!--        <b-col cols="2">-->
<!--          <img class="w-100 h-100" src="../assets/Friends_logo.svg">-->
<!--        </b-col>-->
<!--        <b-col cols="1">-->
<!--          <router-link to="/">Home</router-link>-->
<!--          <span class="p-1"></span>-->
<!--          <router-link to="/about">About</router-link>-->
<!--        </b-col>-->


<!--        <b-col cols="5" class="">-->

<!--        </b-col>-->
<!--        <b-col cols="2" class="align-content-start">-->
<!--          Friends Blog-->
<!--        </b-col>-->



<!--      </b-row>-->
<!--    </b-container>-->

  <div>
    <b-navbar  class="gray shadow-lg align-items-baseline">
      <b-navbar-nav href="#">
        <b-nav-item>
          <img class="w-100 h-100" src="../assets/Friends_logo.png">
        </b-nav-item>
      </b-navbar-nav>

      <b-navbar-nav right class="ml-auto">
        <b-nav-item  >
          <b-button variant="outline-dark"><router-link tag="li" to="/">Home</router-link></b-button>
        </b-nav-item>
        <b-nav-item  >
          <b-button variant="outline-dark"><router-link tag="li" to="/comment">Comments</router-link></b-button>
        </b-nav-item>
        <b-nav-item  >
          <b-button variant="outline-dark"><router-link tag="li" to="/about">About</router-link></b-button>
        </b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Nav"
}
</script>

<style scoped>
.small-size{
  width: 400px;
  height: 100px;
  object-fit: fill;
}
.gray{
  background-image: linear-gradient(to left, #ffffff, #fff3fe, #ffe6eb, #ffdec9, #fbdea8);
  /*background-image: linear-gradient(to left, #fbb65b, #fac16a, #f9cc79, #f9d689, #f9e09a);*/
}
</style>