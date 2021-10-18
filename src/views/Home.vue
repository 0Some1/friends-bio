<template>
  <div class="home">
    <BigImage :img="bigImage" ></BigImage>
    <h2 class=" mt-5 text-center">Biography</h2>
    <bio  class="bio m-auto shadow-sm"></bio>
    <h2 class="mt-5 text-center">Characters</h2>
    <cast></cast>
    <h2 class="mt-5 text-center">Gallery</h2>
    <Gallery class="w-100 m-auto" :data="images"></Gallery>
  </div>
</template>

<script>
// @ is an alias to /src

import Gallery from "../components/Gallery";
import BigImage from "@/components/BigImage";
import bio from "@/components/Bio"
import Cast from "@/components/Cast";

export default {
  name: 'Home',
  components: {
    Cast,
    BigImage,
    Gallery,
    bio,

  },
  data(){
    return{
      images: [
        "https://wallpapercave.com/download/joey-friends-wallpapers-wp8271675",
        "https://wallpapercave.com/download/chandler-bing-wallpapers-wp2102967",
        "https://wallpapercave.com/download/friends-tv-show-wallpapers-y57Tz5Q",
        "https://wallpapercave.com/download/friends-tv-show-wallpapers-VLqMEa1",
        "https://wallpapercave.com/download/friends-tv-show-wallpapers-zLeVJhN",
        "https://wallpapercave.com/download/friends-tv-show-wallpapers-NyvK0hA",
        "https://wallpapercave.com/download/friends-tv-show-wallpapers-NyvK0hA",
        "https://wallpapercave.com/wp/wp8896774.jpg",
        "https://wallpapercave.com/wp/wp8896902.jpg",
        "https://wallpapercave.com/wp/wp8896768.jpg",
        "https://wallpapercave.com/wp/wp4729573.jpg",
        "https://wallpapercave.com/wp/wp7638234.png",
        "https://wallpapercave.com/wp/wp4729577.jpg",
        "https://wallpapercave.com/wp/wp4741532.jpg",
        "https://wallpapercave.com/wp/wp7638246.jpg",
        "https://wallpapercave.com/wp/wp7289100.jpg",
        "https://wallpapercave.com/wp/wp7638301.jpg",
        "https://wallpapercave.com/wp/wp4023511.jpg",
        "https://wallpapercave.com/wp/wp7638345.jpg",
        "https://wallpapercave.com/wp/wp7638341.jpg",
        "https://wallpapercave.com/wp/wp3949715.jpg",
        "https://wallpapercave.com/wp/wp4729603.jpg",
        "https://wallpapercave.com/wp/wp4729608.jpg",
        "https://wallpapercave.com/wp/wp2590155.jpg",
        "https://wallpapercave.com/wp/wp8586321.jpg",
        "https://wallpapercave.com/wp/wp8586321.jpg",

      ],
      bigImage:""
    }
  }
}
</script>

<style scoped>

.bio{
  width: 95%;
}

</style>