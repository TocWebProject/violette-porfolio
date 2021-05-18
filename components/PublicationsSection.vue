<template>
    <section id="publications" class="publications-section">
        <div class="section-container">
            <h1>Publications</h1>
        </div>
    </section>
</template>

<script>
export default {
    name:'PublicationsSection',
}
</script>

<style lang="scss">
.publications-section {
    background-color: #ffde17;
     color: #ffffff;
  
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
            color: #ffffff;
            margin-bottom: 30px;
        }
    }
}


// // Extra small devices (portrait phones, tablet less than 1024px)
@media screen and (min-width: 100px) and (max-width: 1024px) { 
    .publications-section {
        .section-container {   
            height: 100vh;
            min-height: 700px;

            h1 {
                font-size: 55px;
            }
        }
    }
}
</style>