<template>
  <div class="wrap">
    <div v-if="showGallery" class="close"  @click="closeGalley"><img src="../assets/icon/close.png"></div>
    <div v-if="showGallery" class="gallery">
      <div class="rightArrow"><img  @click="nextPic" src="../assets/icon/LA.png"></div>
      <div class="galleryImg"> <img class="w-100 h-100"  :src="images[index]" ></div>
      <div class="leftArrow"><img  @click="lastPic" src="../assets/icon/RA.png"></div>

    </div>
    <div class="wrap2" ref="wrap2" v-bind:style="colStyle">
      <div class="row" ref="mainRow">

        <div class="column" ref="column0">
          <div v-for="(image ,key) in images"  :key="key">
            <img class="pic" ref="imgArray0" @click="changeIndex(key)" v-if="images[key] && key%3===0" :src="getBaseUrl+image"
                  style="width:100%">
          </div>
        </div>

        <div class="column" ref="column1">
          <div v-for="(image ,key) in images"  :key="key">
            <img class="pic" ref="imgArray1" @click="changeIndex(key)" v-if="images[key] && key%3===1" :src="getBaseUrl+image"
                 style="width:100%">
          </div>
        </div>

        <div class="column" ref="column2">
          <div  v-for="(image ,key) in images"  :key="key">
            <img class="pic" ref="imgArray2" @click="changeIndex(key)" v-if="images[key] && key%3===2" :src="getBaseUrl+image"
                  style="width:100%">
          </div>
        </div>

      </div>

    </div>

    <button class="btn" v-if="collapseFlag" @click="changeHeight">
      Click here to view more!
    </button>



    <button class="btn" v-else @click="changeHeight">
      Click here to collapse the Galley!
    </button>


  </div>
</template>

<script>

  export default {
    name: "Gallery",
    props:[
      'data'
    ],
    data() {
      return {
        j: 0,
        max: 15,
        colStyle: {
          maxHeight: "",
        },
        collapseFlag: true,
        images: this.data,
        index: null,
        mainRowHeight: null,
        imagesClone:[],
        showGallery:false,
        eventListenerFunc:null,



      };
    },
    computed:{
      getBaseUrl(){
        // return process.env.baseUrl+'/';
        return "";
      }
    },

    methods: {
      // getAltImage(name){
      //   return name.split('$')[1].split('.')[0];
      // },
      changeHeight() {
        if (this.collapseFlag === false) {
          this.colStyle.maxHeight = this.mainRowHeight / 3 + 'px';
          this.collapseFlag = true;
        } else {
          this.colStyle.maxHeight = this.mainRowHeight + 'px';
          this.collapseFlag = false;
        }

      },
      changeIndex(j){
        console.log("index")
        this.showGallery=true;
        this.index=j;
      },
      closeGalley(){
        this.showGallery=false;
        this.index=null;
      },
      nextPic(){
        this.index++;
        this.index=this.index%this.images.length;
      },
      lastPic(){
        this.index--;
        if (this.index<0){
          this.index=this.images.length-1;
        }
      }
    }
    ,
    mounted() {
      for (let i = 0; i < this.images.length; i++) {
        console.log(this.images[i])
      }
      this.images.forEach((item)=>{
        this.imagesClone.push({
          src:this.getBaseUrl+item,
        })
      })
      let imageLoaded = 0;
      let imagesArray = [];
      imagesArray = imagesArray.concat(this.$refs.imgArray0)
      imagesArray = imagesArray.concat(this.$refs.imgArray1)
      imagesArray = imagesArray.concat(this.$refs.imgArray2)
      console.log(imagesArray)
      for (const img of imagesArray) {
        img.onload = () => {
          imageLoaded++;
          if (imageLoaded === imagesArray.length - 1) {

            this.mainRowHeight = this.$refs.mainRow.offsetHeight;
            console.log(this.mainRowHeight)
            this.colStyle.maxHeight = this.$refs.mainRow.offsetHeight / 3 + 'px';
          }
        }
      }

      this.eventListenerFunc= ()=> {
        let size = this.$refs.mainRow.offsetHeight;
        this.mainRowHeight = size;
        if (this.collapseFlag === true) {
          this.colStyle.maxHeight = size / 3 + 'px';
        } else {
          this.colStyle.maxHeight = size + 100 + 'px';
        }
      }


      window.addEventListener('resize', this.eventListenerFunc)


    },
    beforeDestroy() {
      window.removeEventListener('resize',this.eventListenerFunc);
    },
  }
</script>


<style scoped >

  .pic{
    border-radius: 5px;
    -webkit-box-shadow: rgba(0, 0, 0, 0.3) 0 1px 3px;
    -moz-box-shadow: rgba(0,0,0,0.3) 0 1px 3px;
    box-shadow: rgba(0, 0, 0, 0.3) 0 1px 3px;
    transition: transform .2s;
  }
  .pic:hover{
    -webkit-box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
    -moz-box-shadow: rgba(0,0,0,0.3) 0 5px 10px;
    box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
    transform: scale(1.01);
  }

  .close{
    top: 1px;
    right: 3px;
    position: fixed;
    z-index: 310;
    cursor: pointer;
  }

  .close>img{
    width: 18px;
    height: 18px;
  }

  .gallery{
    top: 0;
    left: 0;
    display: flex;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.6);
    z-index: 300;
    min-height: 100%;
    min-width: 100%;
    justify-content: center;
    justify-items: center;
    max-height: 100%;
    max-width: 100%;
  }

  .leftArrow{
    cursor: pointer;
    display: flex;
    justify-items: center;
    justify-content: center;
    align-items: center;
    align-content: center;
    width: 10%;
    min-height: 100%;
  }
  .rightArrow{
    cursor: pointer;
    display: flex;
    justify-items: center;
    justify-content: center;
    align-items: center;
    align-content: center;
    width: 10%;
    min-height: 100%;

  }

  .rightArrow>img{
    width: 28px;
    height: 28px;
  }
  .leftArrow>img{
    width: 28px;
    height: 28px;
  }
  .galleryImg{
    display: flex;
    justify-items: center;
    justify-content: center;
    align-items: center;
    align-content: center;
    max-height: 100%;

  }

  .galleryImg>img{
    object-fit: cover;
    max-width: 100%;
    max-height: 100%;
  }

  .wrap {
    max-width: 100%;
    box-sizing: border-box;
  }

  .wrap2 {
    overflow: hidden;
    -webkit-transition: max-height 2s;
    -moz-transition: max-height 2s;
    transition: max-height 2s;
    box-sizing: border-box;
    max-width: 100%;
    width: 100%;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
  }

  .row {
    margin: 0 auto;
    display: -ms-flexbox; /* IE10 */
    display: flex;
    -ms-flex-wrap: wrap; /* IE10 */
    flex-wrap: wrap;
    justify-content: center;
    max-width: 100%;
    width: 100%;
  }

  /* Create four equal columns that sits next to each other */
  .column {
    -ms-flex: 32%; /* IE10 */
    flex: 32%;
    max-width: 33%;
    padding: 0 4px;
  }


  .column img {
    margin-top: 8px;
    vertical-align: middle;
  }


  /*.btn {*/
  /*  background-color: rgba(51, 51, 51, 0.05);*/
  /*  border-radius: 8px;*/
  /*  border-width: 0;*/
  /*  color: #333333;*/
  /*  cursor: pointer;*/
  /*  display: inline-block;*/
  /*  font-family: "Haas Grot Text R Web", "Helvetica Neue", Helvetica, Arial, sans-serif;*/
  /*  font-size: 14px;*/
  /*  font-weight: 500;*/
  /*  line-height: 20px;*/
  /*  list-style: none;*/
  /*  margin: 0;*/
  /*  padding: 10px 12px;*/
  /*  text-align: center;*/
  /*  transition: all 200ms;*/
  /*  vertical-align: baseline;*/
  /*  white-space: nowrap;*/
  /*  user-select: none;*/
  /*  -webkit-user-select: none;*/
  /*  touch-action: manipulation;*/
  /*  width: 100%;*/
  /*}*/

  .btn {
    margin-top: 10px;
    width: 100%;
    appearance: none;
    background-color: #FAFBFC;
    border: 1px solid rgba(27, 31, 35, 0.15);
    border-radius: 6px;
    box-shadow: rgba(27, 31, 35, 0.04) 0 1px 0, rgba(255, 255, 255, 0.25) 0 1px 0 inset;
    box-sizing: border-box;
    color: #24292E;
    cursor: pointer;
    display: inline-block;
    font-family: -apple-system, system-ui, "Segoe UI", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
    font-size: 14px;
    font-weight: 500;
    line-height: 20px;
    list-style: none;
    padding: 6px 16px;
    position: relative;
    transition: background-color 0.2s cubic-bezier(0.3, 0, 0.5, 1);
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    vertical-align: middle;
    white-space: nowrap;
    word-wrap: break-word;
  }

  .btn:hover {
    background-color: #F3F4F6;
    text-decoration: none;
    transition-duration: 0.1s;
  }

  .btn:disabled {
    background-color: #FAFBFC;
    border-color: rgba(27, 31, 35, 0.15);
    color: #959DA5;
    cursor: default;
  }

  .btn:active {
    background-color: #EDEFF2;
    box-shadow: rgba(225, 228, 232, 0.2) 0 1px 0 inset;
    transition: none 0s;
  }

  .btn:focus {
    outline: 1px transparent;
  }

  .btn:before {
    display: none;
  }

  .btn:-webkit-details-marker {
    display: none;
  }


</style>


