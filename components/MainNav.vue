<template>
    <header>
        <div class="header-container">
            <div class="logo">
                <p>•|• Violette</p>
            </div>
            <div class="menu-button" @click="toggleMenu()">
                <svg class="burger-svg" xmlns="http://www.w3.org/2000/svg" width="60" height="12" viewBox="0 0 60 12">
                    <g class="burger-lines">
                        <g>
                            <path class="burger-first-line" d="M0 0h60v2H0z"></path>
                        </g>
                        <g >
                            <path class="burger-second-line" d="M0 10h60v2H0z"></path>
                        </g>
                    </g>
                </svg>
            </div>
        </div>
        <div class="menu-overlay">
            <div class="main-nav">
                <nav>
                    <ul>
                        <li><a @click="toggleMenu()" href="#home">Accueil</a></li>
                        <li><a @click="toggleMenu()" href="#linogravures">Linogravure</a></li>
                        <li><a @click="toggleMenu()" href="#contact">Contact</a></li>
                    </ul>     
                </nav>       
                <div class="social-share">
                    <p>violette@violette.com</p>
                    <p>instagram</p>
                </div>
            </div>
        </div>
    </header>         
</template>

<script>
export default {
    name: 'MainNav',
    data() {
        return {
            isOpen: false,
        }
    },
    methods: {
        toggleMenu(){
            if(this.isOpen === false) {
                this.openMenuSlide()
                this.isOpen = true
            } else if (this.isOpen === true) {
                this.closeMenuSlide()
                this.isOpen = false
            }
        },

        openTheMenu() {
            this.openMenuSlide();
        },
        closeTheMenu() {
            this.closeMenuSlide();
        },   
        
        openMenuSlide() {
            const gsap = this.$gsap
            const openMenuSlide = new gsap.timeline()
            
            openMenuSlide.to(".menu-overlay", {
                height: '100vh',
                duration: 0.6,
            })

            openMenuSlide.to(".main-nav", {
                opacity: '1',
                duration: 0.5,
            },"-=0.3")

            openMenuSlide.to(".burger-svg", {
                transform: 'scaleX(0.5)',
            },"-=0.7")

            openMenuSlide.to(".burger-first-line", {
                rotation: 20,
                translateY: '-5px'
            },"-=0.7")

            openMenuSlide.to(".burger-second-line", {
                rotation: -20,
                translateY: '5px'
            },"-=0.7")

            // Prevent from scrolling the page when Menu is open.
            document.body.style.overflow = "hidden";
        },

        closeMenuSlide(){
            const gsap = this.$gsap
            const closeMenuSlide = new gsap.timeline()
            
            closeMenuSlide.to(".menu-overlay", {
                height: '0vh',
                duration: 0.4,
            })

            closeMenuSlide.to(".main-nav", {
                opacity: '0',
                duration: 0.4,
            },"-=0.6")
            

            closeMenuSlide.to(".burger-svg", {
                transform: 'scaleX(1)',
            },"-=0.4")

            closeMenuSlide.to(".burger-first-line", {
                rotation: 0,
               translateY: '0px'
            },"-=0.5")

            closeMenuSlide.to(".burger-second-line", {
                rotation: 0,
                translateY: '0px'
            },"-=0.5")

            // Back to overflow Auto 
            document.body.style.overflow = "auto";
        }
    }

}
</script>

<style lang="scss">
header {
    position: fixed;
    width: 100%;
     
    .header-container {
        margin: 0 auto;
        max-width: 1400px;
        width: 100%;
        height: 90px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 40px;

        .logo {
            z-index: 150;

            p {
                font-size: 30px;
                font-weight: 600;
            }
        }

        .menu-button {
            margin-top: 8px;
            height: 60px;
            z-index: 150;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;

            .burger-svg {
                width: 60px;
                height: 60px;
            }
        }
    }

    .menu-overlay {
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        overflow: hidden !important;
        width: 100vw;
        height: 0vh;
        position: fixed;
        background-color: white;
        z-index: 100;
      
        .main-nav {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            text-align: center;
            height: 100%;
            overflow: hidden !important;

            nav{
                padding-bottom: 20px;
    
                ul {
                    margin: 0;
                    padding: 0;
                    list-style: none;
                }

                li {
                    padding: 6px 12px;
                }

                a {     
                    font-size: 60px;         
                    text-decoration: none;
                
                    &:link {
                    color: black;
                    }

                    &:visited {
                    color:rgb(34, 31, 31);
                    }

                    &:hover {
                    color: royalblue;
                    }

                    &:active {
                    color: rgb(31, 79, 223);
                    }
                }
            }
        }

        .social-share {
            font-size: 30px;
            letter-spacing: 3px;
        }
    }
}

// // Extra small devices (portrait phones, less than 600px)
@media screen and (min-width: 100px) and (max-width: 600px) { 
    header {
        .header-container {
            padding: 0px 20px;
            height: 60px;
        }

        .menu-overlay {
            
            .social-share {
                font-size: 26px;
            }

            .main-nav {
                nav{
                    a {
                        font-size: 52px;
                    }
                }
            }
        }
    }

}
</style>