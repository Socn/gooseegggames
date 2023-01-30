<script>
export default {
    data: () => ({
        imgList: [
            "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
            "https://cdn.vuetifyjs.com/images/cards/hotel.jpg",
            "https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
        ]
    }),
  }

</script>

<template>
<head>
    <title>鹅蛋工作室 | GooseEggGames</title>
</head>

<v-toolbar border
  id="header"
>
    <v-img id="logo">
        Logo
    </v-img>
    <v-menu
      open-on-hover
      open-delay="50ms"
    >
      <template v-slot:activator="{ props }">
        <v-btn
          color="primary"
          v-bind="props"
          style="margin-left: auto;"
        >
          项目列表
        </v-btn>
      </template>

      <v-list>
        <v-list-item>
          <v-list-item-title>Simple</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
</v-toolbar>

<div id="body">
    <!-- <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax> -->
    <div id="content">
        <v-carousel
            id="images"
            height="600"
            hide-delimiter-background
            show-arrows="hover"
        >
            <v-carousel-item
                v-for="img in imgList"
                :key="img"
                :src=img
                cover
            >
            </v-carousel-item>
        </v-carousel>
        <div class="card" id="about-us">
            <div class="card-bg">

            </div>
            <div class="card-title">
                <div class="card-title-text">
                    关于我们
                </div>
                <div class="card-title-sub-container">
                    <div class="card-title-sub">
                        ABOUT US
                    </div>
                </div>
                
            </div>
        </div>
    </div>

    <v-footer border id="footer">Copyright © 2023 Goose Egg Studio</v-footer>
</div>

</template>

<style lang="scss">
#header{
    position: fixed;
    width: 100vw;
    background-color: rgb(255,255,255,0.5);
    backdrop-filter: blur(25px) saturate(0.8);
    z-index: 1000;
    #logo{
        max-width: 150px;
        height: 50px;
        border-radius: 10px;
        position: relative;
    }
}
#body{
    height: 100vh;
    overflow-y: overlay;
    padding-top: 0;
    box-sizing: border-box;
}
#body::-webkit-scrollbar{
    width: 14px;
    display: none;
    border-radius: 8px;
}
#body::-webkit-scrollbar-thumb {
    background: rgb(200,200,200);
    border-radius: 8px;
    border: solid rgb(255,255,255) 4.5px;
    z-index: 500;
}

#body::-webkit-scrollbar-thumb:hover {
    background: rgb(150,150,150);
    border: solid rgb(255,255,255) 3px;
}

#body::-webkit-scrollbar-track {
    border-radius: 10px;
    background-color: rgb(255,255,255);
}

#content{
    position: relative;
    display: block;
    width: 100%;
    height: 200vh;
    // margin-top: 64px;
}

#footer{
    position: relative;
    bottom: 0;
    height: 80px;
    /* background-color: rgb(233,233,233); */
    vertical-align: middle;
    line-height: 80px;
    text-align: center;
    border-right: none;
    border-left: none;
    border-bottom: none;
}

#images{
    z-index: 100;
    height: 500px;
}

.card{
    vertical-align: middle;
    z-index: 150;
    position: relative;
    padding: 100px;
    padding-top: 200px;
    .card-bg{
        transform: rotate(-2deg) translate(-15vw , -150px);
        background-color: rgb(255,255,255);
        width: 150vw;
        height: 800px;
        position: absolute;
    }
    .card-title{
        position: absolute;
        border: solid rgb(30,30,30) 10px;
        width: 300px;
        height: 150px;
        background-color: rgb(255,255,255);
        .card-title-text{
            font-size: 4rem;
            font-weight: bold;
            position: absolute;
            right: -10px;
            top: -20px;
            background-color: rgb(255,255,255);
        }
        .card-title-sub-container{
            width: 100%;
            height: 100%;
            overflow: hidden;
            position: relative;
            .card-title-sub{
                max-width: 200%;
                font-size: 3.5rem;
                font-weight: bold;
                position: absolute;
                left: -10px;
                bottom: -40px;
                line-height: 100px;
                color: rgba(0,0,0,0.4)
            }
        }
        
    }
    
}
</style>