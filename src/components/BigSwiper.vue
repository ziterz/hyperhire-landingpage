<template>
  <transition appear enter-active-class="animated fadeIn slow">
    <div>
      <swiper
        :effect="'cards'"
        :grabCursor="true"
        :modules="modules"
        :centered-slides="true"
        :cards-effect="{
          slideShadows: false,
          rotate: false,
          perSlideOffset: $q.screen.gt.xs ? 21 : 12.5,
        }"
        @swiper="onSwiper"
        :initialSlide="1"
      >
        <swiper-slide
          v-for="(testimoni, index) in testimonials"
          :key="index"
          :virtualIndex="index"
        >
          <BigCard :testimoni="testimoni" />
        </swiper-slide>
      </swiper>
      <q-btn
        flat
        round
        style="position: absolute; left: -8px; top: 50%; z-index: 1"
        @click="prevSlide()"
      >
        <svg
          data-v-5a8cb0cd=""
          width="32"
          height="32"
          viewBox="0 0 32 32"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_2_8352)">
            <path
              d="M20.0943 26.6665C20.3583 26.6607 20.6105 26.5561 20.801 26.3732C20.9882 26.1857 21.0934 25.9315 21.0934 25.6665C21.0934 25.4015 20.9882 25.1473 20.801 24.9598L12.001 16.1598L20.8143 7.01316C21.0016 6.82566 21.1068 6.57149 21.1068 6.30649C21.1068 6.04149 21.0016 5.78733 20.8143 5.59983C20.6268 5.41256 20.3726 5.30737 20.1076 5.30737C19.8426 5.30737 19.5885 5.41256 19.401 5.59983L9.90763 15.4665C9.81531 15.5582 9.74205 15.6673 9.69205 15.7874C9.64205 15.9075 9.61631 16.0364 9.61631 16.1665C9.61631 16.2966 9.64205 16.4255 9.69205 16.5456C9.74205 16.6657 9.81531 16.7748 9.90763 16.8665L19.3876 26.3865C19.5787 26.5668 19.8316 26.667 20.0943 26.6665V26.6665Z"
              fill="white"
            ></path>
          </g>
          <defs>
            <clipPath id="clip0_2_8352">
              <rect
                width="32"
                height="32"
                fill="white"
                transform="matrix(-1 0 0 1 32 0)"
              ></rect>
            </clipPath>
          </defs>
        </svg>
      </q-btn>
      <q-btn
        flat
        round
        style="position: absolute; right: -8px; top: 50%; z-index: 1"
        @click="nextSlide()"
      >
        <svg
          data-v-5a8cb0cd=""
          width="32"
          height="32"
          viewBox="0 0 32 32"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_2_8351)">
            <path
              d="M11.9057 26.6665C11.6417 26.6607 11.3895 26.5561 11.199 26.3732C11.0117 26.1857 10.9066 25.9315 10.9066 25.6665C10.9066 25.4015 11.0117 25.1473 11.199 24.9598L19.999 16.1598L11.1857 7.01316C10.9984 6.82566 10.8932 6.57149 10.8932 6.30649C10.8932 6.04149 10.9984 5.78733 11.1857 5.59983C11.3732 5.41256 11.6273 5.30737 11.8924 5.30737C12.1574 5.30737 12.4115 5.41256 12.599 5.59983L22.0923 15.4665C22.1847 15.5582 22.2579 15.6673 22.3079 15.7874C22.3579 15.9075 22.3837 16.0364 22.3837 16.1665C22.3837 16.2966 22.3579 16.4255 22.3079 16.5456C22.2579 16.6657 22.1847 16.7748 22.0923 16.8665L12.6124 26.3865C12.4213 26.5668 12.1684 26.667 11.9057 26.6665Z"
              fill="white"
            ></path>
          </g>
          <defs>
            <clipPath id="clip0_2_8351">
              <rect width="32" height="32" fill="white"></rect>
            </clipPath>
          </defs>
        </svg>
      </q-btn>
    </div>
  </transition>
</template>
<script setup lang="ts">
import { ref } from 'vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/effect-cards';
import { EffectCards } from 'swiper/modules';
import BigCard from './BigCard.vue';
import { Testimoni } from './models';

const $s = ref(Swiper);
const modules = ref([EffectCards]);
const testimonials = ref<Testimoni[]>([
  {
    avatar: 'https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png',
    name: 'Abhishek Gupta',
    role: '마케팅 · 2y+',
    skills: [
      '마케팅 콘텐츠 제작',
      '인스타그램 관리',
      '트위터 관리',
      '블로그 글 작성',
    ],
  },
  {
    avatar: 'https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png',
    name: 'Abhishek Gupta',
    role: '마케팅 · 2y+',
    skills: [
      '마케팅 콘텐츠 제작',
      '인스타그램 관리',
      '트위터 관리',
      '블로그 글 작성',
    ],
  },
  {
    avatar: 'https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png',
    name: 'Abhishek Gupta',
    role: '마케팅 · 2y+',
    skills: [
      '마케팅 콘텐츠 제작',
      '인스타그램 관리',
      '트위터 관리',
      '블로그 글 작성',
    ],
  },
]);

// eslint-disable-next-line @typescript-eslint/no-explicit-any
const onSwiper = (swiper: any) => {
  $s.value = swiper;
};

const nextSlide = () => {
  $s.value.slideNext();
};

const prevSlide = () => {
  $s.value.slidePrev();
};

defineOptions({
  name: 'BigSwiper',
});
</script>

<style scoped>
.swiper {
  width: 100%;
  height: auto;
  margin-top: 24px;
}

.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
}

.swiper-slide {
  opacity: 0;
}

.swiper-slide-prev,
.swiper-slide-active,
.swiper-slide-next {
  opacity: 1;
}

.swiper-button-next:after,
.swiper-button-prev:after {
  font-size: 32px !important;
  color: #fff !important;
}
</style>
