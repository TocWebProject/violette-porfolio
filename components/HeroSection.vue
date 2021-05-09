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
        </div>
    </section>
</template>

<script>
export default {
    name:'HeroSection',
    methods: {
        heroLogoAnim(){
            const gsap = this.$gsap
            const heroLogoAnim = new gsap.timeline()
            
            heroLogoAnim.from(".circle-red", {
                x: '-600%',
                duration: 1.7,
            },0.1)

            heroLogoAnim.from(".bar-blue", {
                y: '-300%',
                duration: 1.7,
            },0.6)

            heroLogoAnim.from(".circle-yellow", {
                x: '600%',
                duration: 1.7,
            },1.2)
        }
    },
    mounted(){
        this.heroLogoAnim();
    }
}
</script>

<style lang="scss">
.hero-section {
    overflow: hidden !important;
    
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
            // background-color: burlywood;
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
                background-color: red;
                width: 150px;
                height: 150px;
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
            }
            .bar-blue {
                background-color: #07019B;
                width: 300px;
                height: 650px;
                -webkit-clip-path: inset(0 30% 0 30%);
                clip-path: inset(0 30% 0 30%);
            }
            .circle-yellow {
                background-color: yellow;
                width: 150px;
                height: 150px;
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
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

@media screen and (min-width: 100px) and (max-width: 660px) { 
    .hero-section {
        .section-container  {

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
</style>