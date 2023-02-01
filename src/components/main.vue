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
    <div class="bg">
        <div class="decoration-points-container">
            <div class="decoration-point" v-for="i of 400">
            </div>
        </div>
        <div class="decoration-circle blue"></div>
        <div class="decoration-circle purple"></div>
        <div class="decoration-text-container">
            <div class="decoration-text" v-for="i of 5" :key="i" :style="{opacity:i*0.2}">
                GOOSEEGGGAMES
            </div>
        </div>
    </div>
    <div id="content">

        <div class="maincard" id="main">
            <div class="card-bg">
               
            </div>
            <div class="card-container">
                <div class="card-left">
                    <div class="card-title">
                        鹅蛋工作室
                    </div>
                    <div class="card-title-sub">
                        Goose Egg Games
                    </div>
                    <div class="card-actions">
                        <v-btn class="card-action-btn" color="primary">
                            项目列表
                        </v-btn>
                        <v-btn class="card-action-btn" color="primary">
                            关于我们
                        </v-btn>
                    </div>
                </div>
                <div class="card-right">
                    PLACEHOLDER
                </div>
            </div>
        </div>
        
        <div class="card" id="projects">
            <div class="card-bg left"></div>
            <div class="card-container">
                <div class="card-title right">
                    <div class="card-title-text">
                        现有项目
                    </div>
                    <div class="card-title-sub-container">
                        <div class="card-title-sub">
                            PROJECTS
                        </div>
                    </div>
                </div>
                <v-carousel
                    id="project-images"
                    height="65vh"
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
            </div>
        </div>
        
        <div class="card" id="about-us">
            <div class="card-bg right"></div>
            <div class="card-container">
                <div class="card-title left">
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

        <div class="card" id="contact-us">
            <div class="card-bg left"></div>
            <div class="card-container">
                <div class="card-title right">
                    <div class="card-title-text">
                        联系我们
                    </div>
                    <div class="card-title-sub-container">
                        <div class="card-title-sub">
                            CONTACT
                        </div>
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
    display: flex;
    flex-direction: column;
    width: 100%;
    height: max-content;
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
    z-index: 200;
}

.card{
    vertical-align: middle;
    z-index: 150;
    position: relative;
    padding: 120px;
    margin-top: 100px;
    margin-bottom: 30px;
    box-sizing: border-box;
    height: 100vh;
    width: 100%;
    .card-bg{
        &.left{
            transform: rotate(-2deg) translate(-15vw , -150px);
        }
        &.right{
            transform: rotate(2deg) translate(-15vw , -118px);
        }
        background-color: rgba(255,255,255,1);
        box-shadow: 0 0 40px 10px rgba(0,0,0,0.1);
        width: 150vw;
        height: 110vh;
        position: absolute;
    }
    .card-container{
        width:1000px;
        height: 80vh;
        margin-left: auto;
        margin-right: auto;
        position: relative;
        padding-top: 110px;
        box-sizing: border-box;
        display: flex;
        .card-title{
            position: absolute;
            margin: auto;
            margin-bottom: 0px;
            border: solid rgb(30,30,30) 10px;
            width: 300px;
            height: 150px;
            background-color: rgb(255,255,255);
            top: -80px;
            .card-title-text{
                font-size: 4.2rem;
                font-weight: bold;
                position: absolute;
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
                    font-size: 3.2rem;
                    font-weight: bold;
                    position: absolute;
                    bottom: -35px;
                    line-height: 100px;
                    color: rgba(0,0,0,0.4)
                }
            }
            &.left{
                left: -100px;
                .card-title-text{
                    right: -10px;
                }
                .card-title-sub{
                    left: -10px;
                }
            }
            &.right{
                right: -100px;
                .card-title-text{
                    left: -10px;
                }
                .card-title-sub{
                    right: -10px;
                }
            }
        }
    }
}

.card#projects{
    #project-images{
        margin-top: 0px;
        width: 1200px;
        margin-left: -100px;
        margin-right: -100px;
    }
}

.maincard#main{
    height: 100vh;
    width: 100vw;
    position: relative;

    .card-container{
        width: 1000px;
        max-width: 80%;
        height: 100%;
        margin-left: auto;
        margin-right: auto;
        position: relative;
        display: flex;
        flex-direction: row;
        align-items: center;
        animation: fade-in 0.5s;
        .card-left{
            .card-title{
                font-size: 5rem;
                font-weight: bold;
            }
            .card-title-sub{
                font-size: 1.5rem;
            }
            .card-actions{
                margin-top: 50px;
                display: flex;
                flex-direction: row;
                .card-action-btn:not(:last-child){
                    margin-right: 10px;
                }
            }
        }
        .card-right{
            right: 0;
            margin-left: auto;
        }
    }
}
.bg{
    background-color: rgb(240,245,255);
    position: fixed;
    height: 100%;
    width: 100%;
}
.decoration-points-container{
    height: 100vh;
    width: 100vw;
    display: grid;
    grid-template-columns: repeat(20, 5%);
    grid-template-rows: repeat(20, 5%);
    opacity: 0.3;
    position: absolute;
    .decoration-point{
        margin: auto;
        height: 3px;
        width: 3px;
        border-radius: 100%;
        background-color: black;
        position: relative;

    }
}
.decoration-circle{
    opacity: 0.15;
    filter: blur(150px) saturate(0.7);
    position: absolute;
    height: 500px;
    width: 500px;
    border-radius: 100%;
    &.blue{
        background-color: blue;
        height: 900px;
        width: 900px;
        bottom: -200px;
        right: -200px;
        animation: shake 60s infinite 3s;
    }
    &.purple{
        background-color: purple;
        height: 600px;
        width: 600px;
        top: -100px;
        left: -100px;
        animation: shake 90s infinite;
    }
}
.decoration-text-container{
    position: absolute;
    display: flex;
    flex-direction: column;
    bottom: -5.5rem;
    left: 0px;
    transform: scaleX(1.05) scaleY(0.95);
    .decoration-text{
        line-height: 5.5rem;
        height: 10rem;
        margin-top: -6.5rem;
        font-size: 6rem;
        color: transparent;
        backdrop-filter: blur(10px);
        font-weight: 900;
        -webkit-text-stroke: 0.3px black;
        &:last-child{
            -webkit-text-stroke: 0.6px black;
        }
    }
}
</style>