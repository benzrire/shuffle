<template>
  <section>
    <div id="home-carousel" class="carousel slide carousel-fade" data-ride="carousel">
      <ol class="carousel-indicators">
        <li data-target="#home-carousel" data-slide-to="0" class="active"></li>
        <li data-target="#home-carousel" data-slide-to="1"></li>
        <li data-target="#home-carousel" data-slide-to="2"></li>
      </ol>
      <div class="carousel-inner">
        <div v-for="(image, index) in images" :key="index" :class="{ active: image.active }" class="carousel-item">
          <img :src="image.src" class="d-block w-100" alt="" />
          <div class="carousel-caption d-flex flex-column justify-content-center align-items-center">
            <h2 class="animated fadeInDown">{{ image.title }}</h2>
            <p class="animated fadeInUp">{{ image.content }}</p>
            <button type="button" class="btn btn-outline-primary mt-3 animated fadeInUp">Get started</button>
          </div>
        </div>
      </div>
      <a class="carousel-control-prev" href="#home-carousel" role="button" data-slide="prev">
        <span class="fa fa-angle-double-left fa-3x" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
      </a>
      <a class="carousel-control-next" href="#home-carousel" role="button" data-slide="next">
        <span class="fa fa-angle-double-right fa-3x" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
      </a>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "@/main.scss";

#home-carousel {
  position: relative;
  height: auto;

  .carousel-inner .carousel-caption {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;

    background: rgba(0, 0, 0, 0.7);

    h2 {
      font-size: 54px;
      line-height: 84px;
      animation-delay: 0.2s;
    }

    p {
      width: 70%;
      font-size: 16px;
      font-weight: lighter;
      animation-delay: 0.6s;
    }

    button.btn.btn-outline-primary {
      border: solid 2px $primary-color;
      border-radius: 50px;
      padding: 0.4rem 2.5rem;
      color: white;

      transition: 0.3s;
      animation-delay: 0.9s;

      &:hover {
        background: $primary-color;
      }
    }
  }

  .carousel-indicators .active {
    background-color: $primary-color;
  }
}
</style>

<script type="text/javascript">
export default {
  data() {
    const images = [
      {
        src: "./photo-of-people-sitting-near-table-3182777.jpg",
        title: "First slider title",
        active: true,
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam ipsum risus, rutrum vitae velit ut, scelerisque iaculis mauris. Duis feugiat eros orci, sed cursus augue auctor quis. Duis ipsum risus, ornare nec iaculis eget, rhoncus vitae justo. Mauris id venenatis.",
      },
      {
        src: "./photo-of-people-sitting-near-wooden-table-3184670.jpg",
        title: "Second slider title",
        active: false,
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean id est at augue blandit vehicula quis non ante. Cras auctor dapibus neque in consequat. Vestibulum ut odio a tellus efficitur efficitur. Donec interdum tellus nec auctor vestibulum. Nam eu semper.",
      },
      {
        src: "./photo-of-people-walking-on-hallway-3182787.jpg",
        title: "Third slider title",
        active: false,
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas eget elementum lorem. Donec elit nulla, euismod quis lectus non, molestie vehicula nunc. Sed malesuada purus vel odio placerat tristique. Suspendisse non venenatis justo. Mauris iaculis nibh lectus, vel dignissim lacus.",
      }
    ];

    return {
      images
    }
  }
};
</script>
