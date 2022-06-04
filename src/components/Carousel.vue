<template>

  <div class="carousel">
    <div class="carousel__head">
      <h1 class="carousel__head__title">Актуальное</h1>
      <div class="carousel__head__navigation">
        <div class="carousel__head__navigation-line">
              <span
                  :style="{ width: getActiveLine + '%'}"
                  class="carousel__head__navigation-line--active">
              </span>
        </div>
        <div class="carousel__head__navigation-buttons">
          <button
              @click="$refs.carousel.goToPrev()"
              class="carousel__head__navigation-buttons--arrow">
            <img src="../assets/icons/arrow-left.svg" alt="arrow"/>
          </button>
          <button
              @click="$refs.carousel.goToNext()"
              class="carousel__head__navigation-buttons--arrow">
            <img src="../assets/icons/arrow-right.svg" alt="arrow"/>
          </button>
        </div>
      </div>
    </div>

    <carousel__agile @after-change="getCurrentSlide($event)" ref="carousel" :options="myOptions">
      <div
          class="carousel__agile__slides"
          v-for="slide in slides"
          :key="slide.id"
      >
        <div class="carousel__agile__slides-card">
          <div class="carousel__agile__slides-card--image">
            <img v-bind:src="slide.img" alt="Photo"/>
          </div>
          <div class="carousel__agile__slides-card--date">{{ slide.date }}</div>

          <h2 class="carousel__agile__slides-card--title">
            {{ slide.title }}
          </h2>
          <h3 class="carousel__agile__slides-card--text">{{ slide.text }}</h3>
        </div>
      </div>
    </carousel__agile>


  </div>
</template>

<script>
import {VueAgile} from 'vue-agile'

export default {
  name: 'App',
  components: {carousel__agile: VueAgile},
  data() {
    return {
      slides: [
        {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась б наднад книгойась более пяти лет, и "
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        }, {
          id: 1,
          title: "Ким и Валерия Брейтбурги написали книгу про искусство",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Работа над книгой велась более пяти лет, и действенные методики, описанные в ней, созданные в результате анализа и синтеза идей…",
        },
        {
          id: 2,
          title:
              "Юрий Колокольников пытается спасти Землю в клипе «Космические силы»",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "Премьера клипа «Космические силы» группы «Мумий Тролль» состоялась 6 ноября 2020 года.",
        },
        {
          id: 3,
          title: "BTS получили четыре награды MTV EMA",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "BTS получили четыре награды MTV EMA 27-я ежегодная церемония награждения MTV Europe Music Awards состоялась 8 ноября 2020 г.",
        },
        {
          id: 3,
          title: "BTS получили четыре награды MTV EMA",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "BTS получили четыре награды MTV EMA 27-я ежегодная церемония награждения MTV Europe Music Awards состоялась 8 ноября 2020 г.",
        },
        {
          id: 3,
          title: "BTS получили четыре награды MTV EMA",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "BTS получили четыре награды MTV EMA 27-я ежегодная церемония награждения MTV Europe Music Awards состоялась 8 ноября 2020 г.",
        },
        {
          id: 3,
          title: "BTS получили четыре награды MTV EMA",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "BTS получили четыре награды MTV EMA 27-я ежегодная церемония награждения MTV Europe Music Awards состоялась 8 ноября 2020 г.",
        },

        {
          id: 4,
          title: "Открытие сезона «Ла Скала» отменено",
          date: "10.11.2020 г.",
          img: require("@/assets/images/PhotoNews.png"),
          text: "BTS получили четыре награды MTV EMA 27-я ежегодная церемония награждения MTV Europe Music Awards состоялась 8 ноября 2020 г.",
        },
      ],
      currentSlide: 0,
      myOptions: {
        slidesToShow: 4,
        autoplay: true,
        navButtons: false,
        responsive: [
          {
            breakpoint: 1200,
            settings: {
              dots: false,
              slidesToShow: 4,
            }
          },
          {
            breakpoint: 900,
            settings: {
              dots: false,
              slidesToShow: 3,
            }
          },
          {
            breakpoint: 600,
            settings: {
              dots: false,
              slidesToShow: 2,
            }
          },
          {
            breakpoint: 100,
            settings: {
              dots: false,
              slidesToShow: 1,
            }
          },

        ]
      }
    }
  },
  methods: {
    getCurrentSlide(event) {
      this.currentSlide = event['currentSlide']
    },
  },
  computed: {
    getActiveLine() {
      return ((this.currentSlide + 1) * (100 / this.slides.length))
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../styles/_variables.scss";
@import "../styles/_mixins.scss";

.carousel {
  &__head {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;

    &__title {
      @include text;
      width: 400px;
      font-weight: bold;
      font-size: 50px;
      line-height: 60px;
      align-items: center;
    }

    &__navigation {
      display: flex;
      align-items: center;
      justify-content: space-between;

      &-line {
        width: 360px;
        height: 0;
        border: 1px solid $standart;
        background: $standart;
        display: flex;
        align-items: center;

        &--active {
          width: 60px;
          border: 1px solid $active;
          background: $active;
          transition: 0.6s;
        }
      }

      &-buttons {
        display: flex;
        justify-content: space-between;


        &--arrow {
          background: white;
          display: flex;
          width: 60px;
          height: 60px;
          border: 1px solid $standart;
          box-sizing: border-box;
          align-items: center;
          justify-content: center;
          margin-left: 40px;
          transition: 0.6s;

          &:hover {
            background: $standart;
            transition: 0.6s;
          }
        }
      }
    }
  }

  &__agile {
    display: flex;
    max-width: 100%;
    overflow: hidden;
    justify-content: space-between;

    &__slides {
      display: flex;
      max-width: 100%;
      overflow: hidden;
      justify-content: space-between;
      align-items: stretch;

      &-card {
        height: 400px;
        border: 1px solid $standart;
        box-sizing: border-box;
        display: block;
        padding: 20px;
        transition: 0.6s;
        margin: 20px 40px 20px 40px;

        &:hover {
          border: 1px solid $active;
          transition: 0.6s;
        }

        &--image {
          display: flex;
          align-items: center;
          justify-content: center;
        }

        &--date {
          @include text;
          font-size: 12px;
          line-height: 22px;
          opacity: 0.6;
          margin: 10px 0 10px 0;
        }

        &--title {
          @include text;
          font-size: 16px;
          line-height: 26px;
        }

        &--text {
          @include text;
          font-size: 12px;
          line-height: 22px;
        }
      }
    }
  }
}

@media (max-width: 1272px) {
  .carousel__agile__slides-card {
    margin: 10px 10px 10px 10px
  }
  .carousel__agile__slides {
    flex-wrap: wrap;
  }
}

@media (max-width: 857px) {
  .carousel__head__navigation {
    flex-wrap: wrap;
    justify-content: center;
    align-content: space-between;
    height: 90px;
  }
  .carousel__head {
    justify-content: center;
    text-align: center;
  }
}

@media (max-width: 836px) {
  .carousel__agile__slides {
    width: 100%;
  }
  .carousel__agile__slides--image {
    display: flex;
    justify-content: center;
    width: 100%;
  }
}

@media (max-width: 376px) {
  .carousel__head__navigation-line {
    width: 260px;
  }
  .slider__head__navigation-buttons--arrow {
    margin-left: 0;
  }
  .slider__head__navigation-buttons {
    width: 140px;
  }
}
</style>

