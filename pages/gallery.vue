<template>
  <div>
    <transition name="slide-fade">
      <div gallery_header v-show="showTitle">
        <p class="gallery_header__text">My favourite photo together!</p>
        <hr />
      </div>
    </transition>

    <transition name="slide-fade">
      <div class="card-container" v-show="showContents">
        <div class="card" v-for="item in contents">
          <div class="card__img-container">
            <img class="card__img" :src="item.path" alt="Flowers" />
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
          <div class="card__title mt-3">
            <p>{{ item.title }}</p>
          </div>
          <div class="card__content">
            <p>
              {{ item.desc }}
            </p>
          </div>
        </div>
      </div>
    </transition>
    <br />
  </div>
</template>
<script>
export default {
  data() {
    return {
      showContents: false,
      showRoot: false,
      showTitle: false,
      contents: [
        {
          path: "https://placekitten.com/300/300",
          title: "Lorem ipsum dolor sit.",
          desc:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusantium amet  voluptatem obcaecati quo natus dolores similique beatae fugit magni saepe!",
        },
        {
          path: "https://placekitten.com/300/300",
          title: "Lorem ipsum dolor sit.",
          desc:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Accusantium amet  voluptatem obcaecati quo natus dolores similique beatae fugit magni saepe!",
        },
      ],
    };
  },

  mounted() {
    setTimeout(() => {
      this.showContents = true;
      this.showTitle = true;
    }, 1);
  },
};
</script>
<style></style>
