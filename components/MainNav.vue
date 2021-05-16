<template>
    <div class="">   
        <header>
            <div class="header-container">
                <div class="logo">
                    <div class="svg-container">
                        <svg id="Calque_1" data-name="Calque 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 30 49">
                            <defs><style>.cls-1{fill:#1a00a5;}</style></defs>
                            <rect x="15" width="8" height="49"/><rect class="cls-1" x="16" y="26" width="3"/>
                            <circle cx="4.5" cy="23.5" r="4.5"/>
                            <circle cx="33.5" cy="23.5" r="4.5"/>
                            <path d="M29.52,32.84c0-.42,0-.85,0-1.27,0-.2,0-.39,0-.59l0-.34c0-.05.06-.38,0-.15s0-.12,0-.14l.06-.27q.07-.3.18-.6c0-.05.15-.33,0-.13s0-.09.07-.13a4.28,4.28,0,0,1,.37-.57l-2.8-.75c.11,1.2.05,2.4.22,3.59a5.92,5.92,0,0,0,1.36,3.06,1.52,1.52,0,0,0,2.56-1.06,9.31,9.31,0,0,0-1.13-4,1.53,1.53,0,0,0-1.69-.69,2,2,0,0,0-1.37,1.49,8,8,0,0,0-.08,1.62,23.49,23.49,0,0,0,.28,3.25l2.9-.79c0-.18-.07-.37-.1-.55,0,.27,0-.06,0-.15q0-.45-.06-.9c0-.63,0-1.25,0-1.88h-3L27.55,35a1.5,1.5,0,0,0,3,0L30.5,29.8a1.5,1.5,0,1,0-3,0,25,25,0,0,0,.36,5.74,1.5,1.5,0,0,0,2.94-.39l-.1-1.56a1.5,1.5,0,0,0-3,0l.1,1.56,2.95-.4c-.05-.23-.09-.45-.13-.68s0-.16,0,0c0-.11,0-.22,0-.34,0-.43-.07-.86-.09-1.3,0-.87,0-1.74,0-2.62h-3L27.55,35h3l-.21-4.12a1.5,1.5,0,0,0-3,0,20.32,20.32,0,0,0,.3,4.27,1.51,1.51,0,0,0,1.85,1,1.55,1.55,0,0,0,1.05-1.84c0-.18,0-.19,0,0l0-.28-.06-.55c0-.35-.05-.7-.07-1.05s0-.7,0-1c0-.18,0-.37,0-.55s0-.12,0,.13a1.09,1.09,0,0,1-.75.69L27.91,31l.18.34s.18.43.06.12a6.49,6.49,0,0,1,.26.74c.07.25.12.5.17.76s0-.13,0,.05,0,.31,0,.46l2.56-1.06c-.24-.29.14.25-.05-.07L31,32.12a1.58,1.58,0,0,1-.13-.26c.07.33,0,0,0-.08a3.58,3.58,0,0,1-.16-.56l-.06-.35c-.05-.29,0,.18,0,0-.05-1-.05-2-.14-3a1.53,1.53,0,0,0-1.1-1.45,1.58,1.58,0,0,0-1.69.69c-1.2,1.62-1.29,3.77-1.18,5.7a1.53,1.53,0,0,0,1.5,1.5,1.51,1.51,0,0,0,1.5-1.5Z" transform="translate(-11 -6)"/></svg>
                    </div>
                    <p>Violette</p>
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
        </header>         
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
    </div>
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
    z-index: 150;
     
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
            display: flex;
            justify-content: center;
            align-items: center;

            .svg-container {
                display: flex;
                justify-content: center;
                align-items: center;
                
                svg {
                   width: 28px;
                   height: 28px; 
                }
            }

            p {
                margin-left: 10px;
                font-size: 33px;
                font-weight: 600;
            }
        }

        .menu-button {
            margin-top: 8px;
            height: 60px;
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

    
}

.menu-overlay {
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        overflow: hidden;
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

// // Extra small devices (portrait phones, less than 600px)
@media screen and (min-width: 100px) and (max-width: 600px) { 
    header {
        .header-container {
            padding: 0px 20px;
            height: 60px;

            .logo {
                .svg-container {
                    svg {
                        width: 24px;
                        height: 24px;
                        margin-bottom: 2px; 
                    }
                }

                p {
                    margin-left: 8px;
                    font-size: 28px;
                    font-weight: 600;
                }
            }
        }

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
</style>