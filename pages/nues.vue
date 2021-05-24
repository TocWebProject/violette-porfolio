<template>
    <section class="nues-section">
        <div class="section-container">
            <h1>Nues</h1>
            <div class="group-picture-01">
                <div class="picture-01"></div>
                <div class="picture-02"></div>
            </div>
            <div class="info-card">
                <h2>Informations:</h2>
                <ul>    
                    <li>Format: a5</li>
                    <li>Prix: 10€</li>
                    <li>Linogravure sur papier aquarelle</li>
                    <li>Pour commander contacer moi par mail ou sur instagram</li>
                </ul>
            </div>
            <div class="group-picture-02">
                <div class="picture-03"></div>
                <div class="picture-04"></div>
            </div>
            <NuxtLink class="back-to-index" to="/#nues">Retour</NuxtLink>
        </div>
    </section>
</template>

<script>
export default {
    name:'nues',
}
</script>

<style lang="scss">
.nues-section {
     padding: 80px 0px 80px 0px;
  
    .section-container {
        display: flex;
        flex-direction: column;
        width: 100%;
        max-width: 1400px;
        height: auto;
        margin: auto;
        padding: 0px 40px;

        h1{
            text-align: center;
            font-size: 90px;
            color:#21409a;
            margin-bottom: 30px;
        }

        .group-picture-01{
            display: flex;
            justify-content: space-between;
            width: 100%;

            .picture-01{
                margin-right: 20px;
                width: 50%;
                height: 750px;
                background-color: rgb(168, 162, 162);
            }

            .picture-02{
                margin-left: 20px;
                width: 50%;
                height: 350px;
                background-color: rgb(150, 150, 150);
            }
        }

        .info-card {
            width: 45%;
            height: 40px;
            margin-left: auto;
            transform: translateY(-250px);
            
            h2 {
                font-size: 21px;
                font-weight: 400;
                text-decoration: underline 1px;
                margin-bottom: 5px;
            }

            ul {
                list-style: none;
             
                padding: 0;

                li {
                    font-size: 18px;
                }
            }

        }

        .group-picture-02{
            display: flex;
            justify-content: space-between;
            width: 100%;

            .picture-03{
                margin: auto;
                width: 350px;
                height: 350px;
                background-color: rgb(240, 234, 234);
            }

            .picture-04{
                margin-left: 20px;
                width: 50%;
                height: 750px;
                background-color: rgb(126, 123, 123);
            }
        }

        .back-to-index {
            font-size: 20px;
            margin-top: 40px
        }

        a {     
            margin: auto;
            font-size: 25px;       
            text-decoration: underline 1px;
            color: black;
            transition: all 0.3s ease-out;

            &:link {
            color: black;
            }

            &:hover {
            color: #21409a;
            }

            &:active {
            color: #163388;
            }
        }
    }
}


// // Extra small devices (portrait phones, tablet less than 1024px)
@media screen and (min-width: 100px) and (max-width: 1024px) { 
    .nues-section {
        .section-container { 
            padding: 0px 0px;  
            
            h1 {
                font-size: 40px;
            }

            .group-picture-01{
                display: flex;
                flex-direction: column;
                width: 100%;

                .picture-01{
                    margin: 20px auto;
                    width: 90%;
                    height: 350px;
                    background-color: rgb(168, 162, 162);
                }

                .picture-02{
                    margin-top: 20px;
                    margin-left: auto;
                    margin-right: auto;
                    width: 70%;
                    height: 400px;
                    background-color: rgb(126, 123, 123);
                }
            }

            .info-card {
                width: 90%;
                height: auto;
                margin: 65px 35px;
                transform: translateY(0px);
                
            }

            .group-picture-02{
                display: flex;
                flex-direction: column;
                width: 100%;

                .picture-03{
                    margin-left: auto;
                    margin-right: 0px;
                    width: 90%;
                    height: 200px;
                    background-color: rgb(168, 162, 162);
                }

                .picture-04{
                    margin-top: 40px;
                    margin-left: auto;
                    margin-right: auto;
                    width: 75%;
                    height: 200px;
                    background-color: rgb(126, 123, 123);
                }
            }

            
        }
    }
}
</style>