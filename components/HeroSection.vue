<template>
    <section id="home" class="hero-section">
        <div class="section-container">
            <div class="hero-logo">
                <div class="polygon-container">
                     <div class="circle-red"></div>
                </div>
                <div class="polygon-container">
                   <div class="bar-blue"></div> 
                </div>
                <div class="polygon-container">
                    <div class="circle-yellow"></div>
                </div>   
            </div>
            <div class="arrow-container">
                <div class="arrow-down">
                    <svg xmlns="http://www.w3.org/2000/svg" class="arrow-svg h-6 w-6" fill="#000000" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
                    </svg>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import { Linear } from "gsap";
export default {
    name:'HeroSection',
    methods: {
        heroAnim(){
            const gsap = this.$gsap
            const heroAnim = new gsap.timeline()
            
            heroAnim.from(".circle-red", {
                x: '-600%',
                duration: 1.7,
            },0.1)

            heroAnim.from(".bar-blue", {
                y: '-300%',
                duration: 1.7,
            },0.6)

            heroAnim.from(".circle-yellow", {
                x: '600%',
                duration: 1.7,
            },1.2)

            heroAnim.from(".arrow-container", {
                opacity: 0,
                duration: 1,
            },3.7)

        },

    },

    mounted(){
        this.heroAnim();
    }
}
</script>

<style lang="scss">
.hero-section {
    overflow: hidden;

    .section-container {
        height: 100vh;
        margin: 0 auto;
        max-width: 1400px;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        
        
        h1{
            text-align: center;
            font-size: 90px;
            color: black;
        }
 
        .hero-logo {
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: -1;
            
            .polygone-container {
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .circle-red {
                background-color: #be1e2d;
                width: 150px;
                height: 150px;
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
            }

            .bar-blue {
                background-color: #21409a;
                width: 300px;
                height: 650px;
                -webkit-clip-path: inset(0 30% 0 30%);
                clip-path: inset(0 30% 0 30%);
            }

            .circle-yellow {
                background-color: #ffde17;
                width: 150px;
                height: 150px;
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
            }
        }

        .arrow-container {
            position: absolute;
            bottom: 25px;
            left: 40px;
            z-index: -1;

            .arrow-down {   
                width: 33px;
                height: 33px;
            }
        }

    } 

}

// // Extra small devices (portrait phones, tablet less than 1024px)
@media screen and (min-width: 100px) and (max-width: 1024px) { 
    .hero-section {
        .section-container  {
            height: 100vh;
            min-height: 700px;
        }
    }
}

@media screen and (min-width: 100px) and (max-width: 600px) { 
    .hero-section {
        .section-container  {
            .arrow-container {
                bottom: 10px;
                left: 18px;
            }

            .hero-logo {
                .circle-red {
                    width: 75px;
                    height: 75px;
                }
                .bar-blue {
                    width: 150px;
                    height: 350px;
                }
                .circle-yellow {
                    width: 75px;
                    height: 75px;
                }
            }
        }
    }
}

@media screen and (min-width: 1600px) { 
.hero-section {
        .section-container  {
            .arrow-container {
          
                left: 15%;
            }
        }
    } 
}
</style>