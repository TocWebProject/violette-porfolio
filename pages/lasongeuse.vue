<template>      
  <article class="article-songeuse" style="transform: inherit !important">
      <!-- 2 div to escape pin-spacer -->
      <div>
        <div  class="container-songeuse" ref="containerSongeuse">
            <section class="description panel blue">
              LANDING
            </section>
            <section class="panel red">
              ONE
            </section>
            <section class="panel orange">
              TWO
            </section>
            <section class="panel purple">
              THREE
            </section>
            <section class="panel green">
              FOUR
            </section>
            <section class="panel gray">
              FIVE
            </section>
        </div>
      </div>
  </article>   
</template>

<script>
export default {
  name: 'lasongeuse',
  data() {
    return {
      songeuseScroll: '',
    }
  },
  methods: {
    horizontaleScrolling() {
      const gsap = this.$gsap
      const { containerSongeuse, articleSongeuse } = this.$refs
      let sections = gsap.utils.toArray(".panel");

      this.songeuseScroll = gsap.timeline({
        scrollTrigger: {
          id: 'horizontaleSongeuse',
          trigger: containerSongeuse,
          pin: true,
          scrub: 1,
          // snap: 1 / (sections.length - 1),
          // base vertical scrolling on how wide the container is so it feels more natural.
          end: this.$refs.containerSongeuse.clientWidth
        }
      }).to(sections, {
        xPercent: -100 * (sections.length - 1),
        ease: "none"
      });
    }
  },
  mounted() {
    this.$ScrollTrigger.refresh();
    this.horizontaleScrolling(); 
  }
}
</script>

<style lang="scss">
  body {
    article.article-songeuse {
      transform: inherit !important;
      overflow-x: hidden;

      .container-songeuse {
        width: 600%;
        height: 100%;
        display: flex;
        flex-wrap: nowrap;
  
        section {
          max-width: 100%;
          width: 100vw;
          height: 100vh;
          
          &.red{
            background-color: rgb(133, 7, 7);
          }
          &.blue{
            background-color: royalblue;
          }
           &.orange{
            background-color: orange;
          }
          &.purple {
            background-color: rgb(136, 69, 136);
          }
          &.green{
            background-color: rgb(72, 146, 72);
          }
          &.gray {
            background-color: rgb(143, 139, 139);
          }
        }
      }
    }
  }
</style>