<template>
  <div>
    <font-awesome-icon
      @click="goHome"
      class="mt-3 ml-3 back"
      icon="fa-solid fa-arrow-left"
    />
    <transition name="slide-fade">
      <div gallery_header v-show="showTitle">
        <p class="gallery_header__text">
          Best Memories
          <font-awesome-icon icon="fa-solid fa-heart" />
        </p>
        <hr />
      </div>
    </transition>

    <transition name="slide-fade">
      <div class="card-container" v-show="showContents">
        <div class="card card__border card__shadow" v-for="item in contents">
          <div class="card__img-container card__border">
            <img
              class="card__img card__border"
              :src="item.path"
              alt="Flowers"
              rel="preload"
            />
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
          type: "img",
          path: require("../assets/img/1st_anv.jpg"),
          title: "1st ANNIVERSARY!",
          desc:
            "This is our very first trip to Sarangani ever na nag motor lang kita. Maski kapoy go lang. One of the best best experience nga upod ka.",
        },
        {
          type: "img",
          path: require("../assets/img/lake_agco.jpg"),
          title: "ONE OF THE MOST UNFORGETTABLE MOMENTS",
          desc:
            "This is my first time na makakadto sa Kidapawan Haha! One of the most unforgettable kay gin motor lang naton then upod pa ang pamilya mo. Reunion ni sang family mo. I'm so grateful kay grabe ko ka open sa pamilya mo. Thankyou so much! Iloveyou <3",
        },
        {
          type: "img",
          path: require("../assets/img/with_nanay.jpg"),
          title: "WITH NANAY <3",
          desc:
            "Best memories and precious moments! Bago nag pahuway si nanay nakilala nya paka then naka bonding pa kita saiya.",
        },
        {
          type: "img",
          path: require("../assets/img/1st_bday_handa.jpg"),
          title: "1st BIRTHDAY CELEBRATION",
          desc:
            "This is my very first birthday celebration nga gin ganap sa balay. Thankyou sa pag surprise kag pag prepare sang pagkaon sini na time. Usually mag birthday ko gakaon lang kami sa gawas or gina kwarta ko lang. Hahaha! Thankyou so much. Hindi ko ni malimtan <3",
        },
        {
          type: "img",
          path: require("../assets/img/1st_ramen.jpg"),
          title: "1st RAMEN!",
          desc:
            "Our first ramen! Hahaha hindi sya authentic ramen pero okay na best experience gyapon kay upod ka. Busy man sini na time sa work hindi lang busy stress pa! Hahaha pero we manage to have a quality time together. Always the best!",
        },
        {
          type: "img",
          path: require("../assets/img/3rd_anniv.jpg"),
          title: "2nd RAMEN HAHA",
          desc:
            "Our 2nd Ramen! HAHAHA Hindi ko lang sure kung authentic ramen ni sya pero the best ramen ni sya nga natilawan ko. Btw sa Ichiban ta sini nag kaon then 3rd anniversary ta sini na time <3 Best moments as always basta upod ka. ILVOEYOUUUU <3",
        },
        {
          type: "img",
          path: require("../assets/img/lakesebu.jpg"),
          title: "LAKE SEBUSOG",
          desc:
            "One of the best memories! Sa Punta Isla lake resort. Monthsary ta ni na time then one of the best feeling kay naka unwind ta diri padula stress sa work, school and sa life. Hahaha! Hindi ko gid ni malimtan kay busog2 gud ko diri na time damo order ta diri may dala pata sa balay. Hahaha!",
        },
        {
          type: "img",
          path: require("../assets/img/1ofthebestlakesebu.jpg"),
          title: "ONE OF MY FAVOURITE PHOTO!",
          desc:
            "Isa ni sa mga paborito ko gid na picture ta. Sa lake sebu ni sya pakadto tasiman ba to? Best view ni diri na part kay overview makita mo gid ang poblacion sang Lake Sebu. Always the best gid kay upod ka. THANKS MIA SA PAG PICTURE! HAHA",
        },
        {
          type: "img",
          path: require("../assets/img/1stbikesatubig.jpg"),
          title: "1st WATER BIKING",
          desc:
            "One of best experience with you! First ko naka water biking sini na time then upod tapaka. Damo gid ko na enjoy and na experience since nag abot ka sa life ko. Salamat! ILOVEYOU SO MUCH!!!!",
        },
        {
          type: "img",
          path: require("../assets/img/flowers.png"),
          title: "FLOWERS FOR YOU!",
          desc:
            "Hello Mang! I hope na magustohan mo ang simple website na gin ubra ko. Ang mga pictures gali na gin pili ko is ''ONE'' of the best memories lang we know naman nga damo-damo nagid ta mga best memories, moments and experiences. Daw maubos na storage ko sa GDrive ka save. Ang mga photos nga gin pili ko mapansin mo dugay na. Since this is our 5th Anniversary murag recap nalang sa mga best memories together. Be ready kay hindi pa diri matapos ang adventure ta. More adventures to come. HAPPY ANNIVERSARY! ILOVEYOUUUU <3",
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

  methods: {
    goHome() {
      setTimeout(() => {
        this.showContents = false;
        this.showTitle = false;
      }, 500);
      setTimeout(() => {
        this.$router.push({ path: "/home" });
      }, 1000);
    },
  },
};
</script>
<style></style>
