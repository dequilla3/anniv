<template>
  <div class="home">
    <div class="polygon"></div>
    <transition name="slide-fade">
      <div class="ellipse" v-show="showEllipse">
        <div class="ellipse__1"></div>
        <div class="ellipse__2"></div>
        <div class="ellipse__3"></div>
      </div>
    </transition>

    <transition name="slide-fade">
      <div class="header">
        <div class="header__text">
          <transition name="slide-fade">
            <p v-show="showFirstParag">Happy 5<sup>th</sup></p>
          </transition>
          <transition name="slide-fade">
            <p v-show="showSecondParag">Anniversary!</p>
          </transition>
        </div>

        <div class="header__sub-text">
          <transition name="slide-fade">
            <p v-show="showSecondParag">
              <sup><font-awesome-icon class="ml-1" icon="fa-solid fa-quote-left" /></sup>
              I’m so excited about the future because I can’t wait to make all of our
              dreams come true. Happy anniversary and cheers to many more.
              <sup><font-awesome-icon class="ml-1" icon="fa-solid fa-quote-right" /></sup>
              <br />
              <sub class="ml-2">- Kim Dequilla</sub>
            </p>
          </transition>
        </div>

        <transition name="slide-fade">
          <b-button @click="onNextPage()" class="mt-3" variant="info" v-show="showButton"
            >CLICK HERE<font-awesome-icon class="ml-2" icon="fa-solid fa-arrow-right"
          /></b-button>
        </transition>
      </div>
    </transition>

    <transition
      name="custom-classes-transition"
      enter-active-class="animated tada"
      leave-active-class="animated bounceOutRight"
    >
      <div v-if="showChat" class="chat chat__text">
        <p>Flowers for you <font-awesome-icon icon="fa-solid fa-heart" /></p>
      </div>
    </transition>

    <transition name="bounce">
      <div v-show="showFlowers" class="img-container">
        <img class="main-img" src="../assets/img/flowers.png" alt="Flowers" />
      </div>
    </transition>

    <div v-show="showHearts">
      <div class="heart__1"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__2"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__3"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__4"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__5"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__6"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__7"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__8"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__9"><font-awesome-icon icon="fa-solid fa-heart" /></div>
      <div class="heart__10"><font-awesome-icon icon="fa-solid fa-heart" /></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showFirstParag: false,
      showSecondParag: false,
      showButton: false,
      showEllipse: false,
      showFlowers: false,
      showHearts: false,
      showChat: false,
    };
  },

  methods: {
    onNextPage() {
      this.showFirstParag = false;
      this.showEllipse = false;
      this.showFlowers = false;
      this.showSecondParag = false;
      this.showButton = false;
      this.showHearts = false;
      this.showChat = false;
      setTimeout(() => {
        this.$router.push({ path: "/gallery" });
      }, 800);
    },
  },

  mounted() {
    setTimeout(() => {
      this.showFirstParag = true;
      this.showEllipse = true;
      this.showFlowers = true;
    }, 1500);

    setTimeout(() => {
      this.showSecondParag = true;
    }, 1550);

    setTimeout(() => {
      this.showButton = true;
    }, 1600);

    setTimeout(() => {
      this.showHearts = true;
    }, 2000);

    setTimeout(() => {
      this.showChat = true;
    }, 4000);
  },
};
</script>
