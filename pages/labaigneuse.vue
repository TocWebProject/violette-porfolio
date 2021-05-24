<template>
    <section class="baigneuse-section">
        <div class="section-container">
            <div class="picture-01"></div>
            <div class="title">
                <h1>La baigneuse</h1>
            </div>
            <div class="group-picture-01">
                <div class="picture-02"></div>
                <div class="picture-03"></div>
            </div>
            <div class="info-card">
                <h2>Informations:</h2>
                <ul>    
                    <li>Format: a4</li>
                    <li>Prix: 15€</li>
                    <li>Linogravure sur papier aquarelle</li>
                    <li>Pour commander contacer moi par mail ou sur instagram</li>
                </ul>
            </div>
            <div class="picture-04">
            </div>
            <NuxtLink class="back-to-index" to="/#baigneuse">Retour</NuxtLink>
        </div>
    </section>
</template>

<script>
export default {
    name:'labaigneuse',
}
</script>

<style lang="scss">
.baigneuse-section {
    padding: 80px 0px 80px 0px;
  
    .section-container {
        display: flex;
        flex-direction: column;
        width: 100%;
        max-width: 1400px;
        height: auto;
        margin: auto;
        padding: 0px 40px;

        .picture-01 {
            margin-left: auto;
            background-color: gray;
            width: 75%;
            height: 300px;
        }
        
        .title {
            width: 75%;
            height: auto;
            margin: 30px 0 30px auto;

            h1{
                font-size: 70px;
                color:#21409a;
            }
        }

        .group-picture-01{
            display: flex;
            justify-content: space-between;
            width: 100%;

            .picture-02{
                margin-right: 20px;
                width: 50%;
                height: 350px;
                background-color: rgb(168, 162, 162);
            }

            .picture-03{
                margin-left: 20px;
                width: 50%;
                height: 750px;
                background-color: rgb(126, 123, 123);
            }
        }

        .info-card {
            width: 45%;
            height: 40px;
            margin-left: 40px;
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

        .picture-04 {
            width: 500px;
            height: 500px;
            margin: auto;
            background-color: rgb(219, 219, 219);
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
    .baigneuse-section {
    
        .section-container {
            padding: 0px 0px;

            .picture-01 {
                margin-left: 0px;
                width: 90%;
                height: 300px;
            }
            
            .title {
                margin: 25px 0 25px 20px;

                h1{
                    font-size: 40px;
                }
            }

            .group-picture-01{
                display: flex;
                flex-direction: column;
                width: 100%;

                .picture-02{
                    margin-left: auto;
                    margin-right: 0px;
                    width: 90%;
                    height: 350px;
                    background-color: rgb(168, 162, 162);
                }

                .picture-03{
                    margin-top: 40px;
                    margin-left: auto;
                    margin-right: auto;
                    width: 95%;
                    height: 600px;
                    background-color: rgb(126, 123, 123);
                }
            }

            .info-card {
                width: 90%;
                height: auto;
                margin: 65px 20px;
                transform: translateY(0px);
                
            }

            .picture-04 {
                width: 75%;
                height: 300px;
            }

        }
    }
}
</style>