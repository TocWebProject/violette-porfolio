<template>
    <section id="linogravures" class="lino-section">
        <div class="section-container">
            <h1>Linogravures</h1>
                <div class="baigneuse-top" id="baigneuse"></div>
                <div class="baigneuse-container">
                    <NuxtLink class="link-img-baigneuse" to="/labaigneuse">
                        <div class="overlay-card-baigneuse"></div>
                        <img  class="img-baigneuse" src="~assets/img/violette-baigneuse-vase.png" width="478" height="597" alt="linogravure noir et bleu" loading="lazy">
                    </NuxtLink>
                   <div class="baigneuse-text">
                        <h3>La baigneuse</h3>
                        <NuxtLink class="link-baigneuse" to="/labaigneuse">voir plus</NuxtLink>
                   </div>
                </div>

                <div class="nues-top" id="nues"></div>
                <div class="nues-container">
                    <div class="nues-text">
                        <h3>Nues</h3>
                        <NuxtLink class="link-nues" to="/nues">voir plus</NuxtLink>
                    </div>
                    <NuxtLink class="link-img-nues" to="/nues">
                        <div class="overlay-card-nues"></div>
                        <img  class="img-nues" src="~assets/img/violette-nues-plantes.png" width="478" height="597" alt="linogravure noir et bleu" loading="lazy">
                    </NuxtLink>
                </div>
            </div>
    </section>
</template>

<script>
export default {
    name:'LinoSection',
    methods: {
        animateOnScroll() {
            const gsap = this.$gsap

            gsap.to('.overlay-card-baigneuse', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.baigneuse-container',
                    start: "top 65%",
                    toggleActions: "restart pause play reverse",
                },
            })

            gsap.to('.overlay-card-nues', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.nues-container',
                    start: "top 65%",
                    toggleActions: "restart pause play reverse",
                },
            })
        }
    },

    mounted(){
        this.animateOnScroll();
    }
}
</script>

<style lang="scss">
.lino-section {
    background-color: #21409a;
    color: #ffffff;
    padding: 80px 0px 80px 0px;
  
    .section-container {
        margin: 0 auto;
        max-width: 1400px;
        height: auto;

        h1{
            margin: 50px 0px;
            text-align: center;
            font-size: 90px;
            color: #ffffff;
        }

        // BAIGNEUSE CARD
        .baigneuse-top {
            height: 50px;
        }

        .baigneuse-container {
            display: flex;
            justify-items: center;
            align-items: center;
            height: auto;
            margin-left: 99px;
            
            .baigneuse-text {
                margin-left: 80px;
                transform: translateY(-75px);

                h3 {
                    font-weight: 400;
                    font-size: 35px;
                }

                .link-baigneuse {
                    font-size: 16px;
                    letter-spacing: 1px;
                    margin-top: 3px;
                }
            }

            .link-img-baigneuse {
                position: relative;
                margin: 0px 20px;
                overflow: visible;
                

                .img-baigneuse {
                    max-width: 100%;
                    height: auto;
                }
                .overlay-card-baigneuse {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }
        }

        // NUES CARD
        .nues-top {
            height: 50px;
            transform: translateY(-180px);
        }

        .nues-container {
            display: flex;
            justify-content: flex-end;
            justify-items: center;
            align-items: center;
            height: auto;
            margin-right: 99px;

            .nues-text {
                margin-right: 80px;
                transform: translateY(-75px);

                h3 {
                    font-weight: 400;
                    font-size: 35px;
                }

                .link-nues {
                    font-size: 16px;
                    letter-spacing: 1px;
                    margin-top: 3px;
                    
                }
            }
          
            .link-img-nues {
                position: relative;
                margin: 0px 20px;
                transform: translateY(-180px);
                
                .img-nues {
                    max-width: 100%;
                    height: auto;
                }
                .overlay-card-nues {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }

        }

        a {            
            text-decoration: underline 1px;
            color: white;
            font-size: 17px;
            transition: all 0.3s ease-out;

            &:link {
            color: white;
            }

            &:visited {
            color:whitesmoke;
            }

            &:hover {
            color: rgb(169, 189, 250);
            }

            &:active {
            color: rgb(148, 173, 247);
            }
        }
    }
}


// // Extra small devices (portrait phones, tablet, desktop less than 1220px)
@media screen and (min-width: 100px) and (max-width: 1220px) { 
    .lino-section {
        padding: 50px 0px 50px 0px;

        .section-container {   
            min-height: 700px;

            h1 {
                font-size: 44px;
                margin: 30px 0px 10px 0px;
            }

            // BAINGEUSE CARD
            .baigneuse-container{
                flex-direction: column;
                margin-left: 0px;
                margin-right: 0px;

                .baigneuse-text {
                    margin-left: 0px;
                    transform: translateY(0px);
                    margin-top: 20px;
                }
            }
            
            // NUES CARD
            .nues-top {
                transform: translateY(0px);
            }

            .nues-container { 
                flex-direction: column;
                margin-left: 0px;
                margin-right: 0px;

                .nues-text {
                    margin-top: 20px;
                    margin-right: 0px;
                    transform: translateY(0px);
                    order: 2;
                }

                .link-img-nues {
                    order: 1;
                    transform: translateY(0px);
                }

            }
        }
    }
}
</style>