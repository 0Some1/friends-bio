<template>
  <div>
    <b-img class="w-100 img-big" height="400px" src="../assets/big.jpg"  alt="Responsive image"></b-img>
  </div>
</template>

<script>
export default {
  name: "BigImage",
  props:[
      "img"
  ]
}
</script>

<style scoped>
.img-big{
  object-fit: cover;

}

</style>