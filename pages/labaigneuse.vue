<template>
    <section id="baigneuse" class="baigneuse-section">
        <div class="section-container">
            <h1>La baigneuse</h1>
            <NuxtLink to="/#linogravures">Retour</NuxtLink>
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
    .baigneuse-section {
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