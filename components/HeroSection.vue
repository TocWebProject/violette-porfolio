<template>
    <section id="home" class="hero-section">
        <div class="section-container">
            <h1>Violette Violette</h1>
        </div>
    </section>
</template>

<script>
export default {
    name:'HeroSection',
}
</script>

<style lang="scss">
.hero-section {
    background-color:beige;

    .section-container {
        height: 100vh;
        margin: 0 auto;
        max-width: 1400px;
        display: flex;
        justify-content: center;
        align-items: center;
    
        h1{
            text-align: center;
            font-size: 90px;
            color: tan;
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
</style>