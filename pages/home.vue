<template>
  <div class="root__home">
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
            <p v-show="showFirstParag">Lorem, ipsum dolor.</p>
          </transition>
          <transition name="slide-fade">
            <p v-show="showSecondParag">Lorem, ipsum.</p>
          </transition>
        </div>

        <div class="header__sub-text">
          <transition name="slide-fade">
            <p v-show="showSecondParag">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat,
              aspernatur!
            </p>
          </transition>
        </div>

        <transition name="slide-fade">
          <b-button @click="onNextPage()" class="mt-1" variant="info" v-show="showButton"
            >GO TO GALLERY <font-awesome-icon class="ml-2" icon="fa-solid fa-arrow-right"
          /></b-button>
        </transition>
      </div>
    </transition>
    <transition name="slide-fade">
      <img
        v-show="showFlowers"
        class="main-img"
        src="../assets/img/flowers.png"
        alt="Flowers"
      />
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
    };
  },

  methods: {
    onNextPage() {
      this.$router.push({ path: "/gallery" });
    },
  },

  mounted() {
    setTimeout(() => {
      this.showFirstParag = true;
      this.showEllipse = true;
      this.showFlowers = true;
    }, 1000);

    setTimeout(() => {
      this.showSecondParag = true;
    }, 1050);

    setTimeout(() => {
      this.showButton = true;
    }, 1100);

    setTimeout(() => {
      this.showHearts = true;
    }, 2000);
  },
};
</script>