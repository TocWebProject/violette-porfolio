<template>
    <section id="contact" class="contact-section">
        <div class="section-container">
            <h1>Contact</h1>
        </div>
    </section>
</template>

<script>
export default {
    name:'ContactSection',
}
</script>

<style lang="scss">
.contact-section {
    background-color:#be1e2d;

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
            color: white;
        }
    }
}


// // Extra small devices (portrait phones, tablet less than 1024px)
@media screen and (min-width: 100px) and (max-width: 1024px) { 
    .contact-section {
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