<template>
    <section class="nues-section">
        <div class="section-container">
            <h1>Nues</h1>
            <NuxtLink to="/#nues">Retour</NuxtLink>
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
  
    .section-container {
        height: 100vh;
        margin: 0 auto;
        max-width: 1400px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        h1{
            text-align: center;
            font-size: 90px;
            color:#21409a;
            margin-bottom: 30px;
        }

        a {     
            font-size: 25px;       
            text-decoration: none;
            color: black;

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
            height: 100vh;
            min-height: 700px;

            h1 {
                font-size: 60px;
            }
        }
    }
}
</style>