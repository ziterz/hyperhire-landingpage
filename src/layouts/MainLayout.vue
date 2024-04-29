<template>
  <q-layout view="hHh LpR fFf">
    <HeaderSection />
    <q-page-container style="padding-top: 0px">
      <q-page
        class="bg-gradient text-white"
        style="overflow: hidden"
        :style="{
          padding: $q.screen.lt.sm ? '60px 0px' : '122px 0px',
        }"
      >
        <div class="container" :class="{ 'q-pa-md': $q.screen.lt.sm }">
          <div
            :class="{ 'grid-cols-2 grid': $q.screen.gt.xs }"
            style="gap: 36px"
          >
            <div class="column" style="gap: 60px">
              <div class="column" style="gap: 24px">
                <div class="column" style="gap: 16px">
                  <transition
                    appear
                    enter-active-class="animated fadeIn slower delay-3s"
                  >
                    <div style="position: relative">
                      <div
                        :class="{ 'text-color-8': $q.screen.gt.xs }"
                        style="
                          font-size: 18px;
                          width: fit-content;
                          padding: 6px 12px;
                          border-radius: 8px;
                        "
                        :style="{
                          backgroundColor: $q.screen.lt.sm
                            ? 'rgb(139, 196, 255)'
                            : 'rgb(255, 255, 255)',
                        }"
                      >
                        풀타임, 파트타임
                      </div>
                      <svg
                        width="12"
                        height="11"
                        viewBox="0 0 12 11"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                        style="position: absolute; bottom: -9px; left: 9px"
                        :style="{
                          color: $q.screen.lt.sm
                            ? 'rgb(139, 196, 255)'
                            : 'rgb(255, 255, 255)',
                        }"
                      >
                        <path
                          d="M6.43301 10.25C6.24056 10.5833 5.75944 10.5833 5.56699 10.25L0.370835 1.25C0.178386 0.916665 0.418948 0.499999 0.803848 0.499999L11.1962 0.5C11.5811 0.5 11.8216 0.916667 11.6292 1.25L6.43301 10.25Z"
                          fill="currentColor"
                        ></path>
                      </svg>
                    </div>
                  </transition>
                  <transition
                    appear
                    enter-active-class="animated fadeInUp slow"
                  >
                    <div
                      :style="{
                        fontSize: $q.screen.gt.xs ? '48px' : '36px',
                      }"
                    >
                      최고의 실력을 가진<br />
                      외국인 인재를 찾고 계신가요?
                    </div>
                  </transition>

                  <transition appear enter-active-class="animated fadeInUp slow"
                    ><div
                      :style="{
                        fontSize: $q.screen.gt.xs ? '24px' : '18px',
                      }"
                    >
                      법률 및 인사관리 부담없이<br />
                      1주일 이내에 원격으로 채용해보세요.
                    </div>
                  </transition>
                </div>
                <transition
                  appear
                  enter-active-class="animated fadeInUp slow"
                  v-if="$q.screen.gt.xs"
                >
                  <div style="font-size: 18px">개발자가 필요하신가요?</div>
                </transition>
              </div>
              <transition
                appear
                enter-active-class="animated fadeIn slow"
                v-if="$q.screen.gt.xs"
              >
                <div class="grid grid-cols-3" style="gap: 48px">
                  <div
                    class="column q-pt-sm"
                    style="
                      gap: 8px;
                      border-top: 1px solid white;
                      border-right-color: white;
                      border-bottom-color: white;
                      border-left-color: white;
                    "
                  >
                    <div style="font-size: 18px">평균 월 120만원</div>
                    <div style="font-size: 16px">
                      임금을 해당 국가를 기준으로 계산합니다.
                    </div>
                  </div>
                  <div
                    class="column q-pt-sm"
                    style="
                      gap: 8px;
                      border-top: 1px solid white;
                      border-right-color: white;
                      border-bottom-color: white;
                      border-left-color: white;
                    "
                  >
                    <div style="font-size: 18px">평균 월 120만원</div>
                    <div style="font-size: 16px">
                      임금을 해당 국가를 기준으로 계산합니다.
                    </div>
                  </div>
                  <div
                    class="column q-pt-sm"
                    style="
                      gap: 8px;
                      border-top: 1px solid white;
                      border-right-color: white;
                      border-bottom-color: white;
                      border-left-color: white;
                    "
                  >
                    <div style="font-size: 18px">평균 월 120만원</div>
                    <div style="font-size: 16px">
                      임금을 해당 국가를 기준으로 계산합니다.
                    </div>
                  </div>
                </div>
              </transition>
            </div>
            <div
              :style="{
                paddingTop: $q.screen.gt.xs ? '0px' : '36px',
              }"
            >
              <div
                style="position: relative; width: fit-content; margin: 0px auto"
              >
                <div
                  class="text-color-8 bg-white flex items-center"
                  style="
                    font-size: 18px;
                    width: fit-content;
                    padding: 6px 12px;
                    border-radius: 8px;
                    gap: 8px;
                  "
                >
                  <svg
                    width="27"
                    height="27"
                    viewBox="0 0 27 27"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <circle
                      cx="13.7607"
                      cy="13.5"
                      r="13"
                      fill="#BBF3D2"
                    ></circle>
                    <path
                      d="M17.9441 9.60332C17.3592 9.60332 16.9024 9.13165 16.5905 8.63687C16.5455 8.56539 16.496 8.49643 16.442 8.42998C16.1812 8.10063 15.8279 7.85361 15.3819 7.68893C14.9358 7.52426 14.4281 7.44192 13.8586 7.44192C13.2616 7.44192 12.7367 7.53455 12.2838 7.71981C11.831 7.90507 11.481 8.16581 11.234 8.50203C10.987 8.83139 10.8635 9.20877 10.8635 9.63419C10.8635 10.2655 11.1208 10.7526 11.6354 11.0957C12.1569 11.4319 12.8053 11.6927 13.5807 11.8779L15.0113 12.2587C16.2533 12.5675 17.2791 13.041 18.0887 13.6791C18.9053 14.3172 19.3135 15.247 19.3135 16.4683C19.3135 17.3123 19.094 18.0671 18.6548 18.7326C18.2225 19.3914 17.5878 19.906 16.7507 20.2765C15.9205 20.647 14.9324 20.8323 13.7865 20.8323C12.675 20.8323 11.7109 20.6539 10.8944 20.2971C10.0847 19.9403 9.44658 19.436 8.98 18.7841C8.7372 18.4398 8.55086 18.0611 8.42099 17.648C8.22397 17.0212 8.76291 16.458 9.41988 16.458C10.0143 16.458 10.4742 16.9427 10.7681 17.4593C10.8313 17.5704 10.9042 17.6757 10.987 17.7755C11.2889 18.1323 11.68 18.3999 12.1603 18.5783C12.6475 18.7567 13.1861 18.8424 13.7762 18.8356C14.4075 18.8356 14.9736 18.7361 15.4745 18.5371C15.9754 18.3381 16.3665 18.0568 16.6478 17.6931C16.9291 17.3295 17.0698 16.9075 17.0698 16.4272C17.0698 16.0155 16.9532 15.6655 16.7199 15.3773C16.4866 15.0891 16.1675 14.8559 15.7627 14.6775C15.3578 14.4991 14.8569 14.3309 14.26 14.1731L12.4897 13.71C11.2409 13.3669 10.2803 12.8763 9.60783 12.2382C8.94226 11.5932 8.6129 10.7664 8.61976 9.7577C8.61976 8.91373 8.8462 8.16581 9.29906 7.51396C9.75879 6.86211 10.3901 6.36122 11.1929 6.01128C12.0025 5.65448 12.9083 5.47607 13.91 5.47607C14.905 5.47607 15.7935 5.65448 16.5758 6.01128C17.3648 6.36122 17.979 6.85182 18.4181 7.48309C18.6365 7.78891 18.8031 8.11449 18.9179 8.45983C19.1195 9.06655 18.5834 9.60332 17.9441 9.60332Z"
                      fill="#00C696"
                    ></path>
                    <path
                      d="M13.9512 4.5L13.9512 6.3291"
                      stroke="#00C696"
                      stroke-width="2"
                      stroke-linecap="round"
                    ></path>
                    <path
                      d="M13.9512 19.918L13.9512 21.7471"
                      stroke="#00C696"
                      stroke-width="2"
                      stroke-linecap="round"
                    ></path>
                  </svg>
                  월 100만원
                </div>
                <svg
                  width="12"
                  height="11"
                  viewBox="0 0 12 11"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  style="position: absolute; bottom: -9px; left: 50%"
                >
                  <path
                    d="M6.43301 10.25C6.24056 10.5833 5.75944 10.5833 5.56699 10.25L0.370835 1.25C0.178386 0.916665 0.418948 0.499999 0.803848 0.499999L11.1962 0.5C11.5811 0.5 11.8216 0.916667 11.6292 1.25L6.43301 10.25Z"
                    fill="currentColor"
                  ></path>
                </svg>
              </div>
              <div style="position: relative">
                <BigSwiper />
              </div>
              <div
                class="column"
                style="gap: 8px; margin-top: 24px; font-size: 16px"
                v-if="$q.screen.lt.sm"
              >
                <div class="flex" style="gap: 8px">
                  <div class="flex" style="gap: 12px">
                    <svg
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <rect width="20" height="20" rx="6" fill="#E8ECFF"></rect>
                      <path
                        d="M14.6666 6.5L8.24992 12.9167L5.33325 10"
                        stroke="#2C599B"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                    한국어 능력
                  </div>
                  <div class="flex" style="gap: 12px">
                    <svg
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <rect width="20" height="20" rx="6" fill="#E8ECFF"></rect>
                      <path
                        d="M14.6666 6.5L8.24992 12.9167L5.33325 10"
                        stroke="#2C599B"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                    업무 수행 능력
                  </div>
                </div>
                <div class="flex" style="gap: 8px">
                  <div class="flex" style="gap: 12px">
                    <svg
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <rect width="20" height="20" rx="6" fill="#E8ECFF"></rect>
                      <path
                        d="M14.6666 6.5L8.24992 12.9167L5.33325 10"
                        stroke="#2C599B"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                    겸업 여부
                  </div>
                  <div class="flex" style="gap: 12px">
                    <svg
                      width="20"
                      height="20"
                      viewBox="0 0 20 20"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <rect width="20" height="20" rx="6" fill="#E8ECFF"></rect>
                      <path
                        d="M14.6666 6.5L8.24992 12.9167L5.33325 10"
                        stroke="#2C599B"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      ></path>
                    </svg>
                    평판 조회
                  </div>
                </div>
              </div>
              <div
                style="font-size: 18px; margin-top: 16px"
                v-if="$q.screen.lt.sm"
              >
                개발자가 필요하신가요?
              </div>
            </div>
          </div>
        </div>
        <MiniSwiper v-if="$q.screen.gt.xs" />
      </q-page>
    </q-page-container>
    <FooterSection />
  </q-layout>
</template>
<script setup lang="ts">
import { useQuasar } from 'quasar';
import HeaderSection from 'src/components/HeaderSection.vue';
import BigSwiper from 'src/components/BigSwiper.vue';
import MiniSwiper from 'src/components/MiniSwiper.vue';
import FooterSection from 'src/components/FooterSection.vue';

const $q = useQuasar();

defineOptions({
  name: 'MainLayout',
});
</script>
