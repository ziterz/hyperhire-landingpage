<template>
  <q-layout view="hHh LpR fFf">
    <q-header
      class="absolute-top bg-transparent text-white container"
      v-if="$q.screen.gt.xs"
    >
      <q-toolbar
        class="row no-wrap items-center flex items-center justify-between"
        style="gap: 36px; padding: 13px 0px"
      >
        <img
          alt="Hyperhire Logo"
          src="data:image/png;base64,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"
          style="width: 114px; height: 21px"
        />
        <div class="flex" style="gap: 60px">
          <div
            class="cursor-pointer non-selectable flex items-center"
            style="gap: 8px"
          >
            채용
            <svg
              width="16"
              height="16"
              viewBox="0 0 16 16"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <g clip-path="url(#clip0_387_34)">
                <path
                  d="M7.90629 11.3334C7.77494 11.3336 7.64849 11.2835 7.55296 11.1934L2.80629 6.44002C2.75717 6.39425 2.71777 6.33905 2.69044 6.27772C2.66311 6.21638 2.64842 6.15017 2.64723 6.08304C2.64605 6.0159 2.6584 5.94922 2.68355 5.88696C2.70869 5.8247 2.74612 5.76814 2.7936 5.72067C2.84108 5.67319 2.89764 5.63576 2.9599 5.61061C3.02216 5.58546 3.08884 5.57311 3.15598 5.5743C3.22311 5.57548 3.28932 5.59018 3.35065 5.6175C3.41199 5.64483 3.46719 5.68423 3.51296 5.73336L7.91296 10.1334L12.493 5.72669C12.5876 5.63466 12.7143 5.58316 12.8463 5.58316C12.9783 5.58316 13.105 5.63466 13.1996 5.72669C13.2933 5.82044 13.3459 5.94752 13.3459 6.08002C13.3459 6.21252 13.2933 6.33961 13.1996 6.43336L8.26629 11.1867C8.21983 11.2349 8.16381 11.2728 8.10181 11.2981C8.03981 11.3234 7.97321 11.3354 7.90629 11.3334Z"
                  fill="currentColor"
                ></path>
              </g>
              <defs>
                <clipPath id="clip0_387_34">
                  <rect width="16" height="16" fill="currentColor"></rect>
                </clipPath>
              </defs>
            </svg>
            <q-menu>
              <q-list style="min-width: 100px">
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu-bold">채용</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu"
                    >해외 개발자 원격 채용</q-item-section
                  >
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu"
                    >외국인 원격 채용 (비개발 직군)</q-item-section
                  >
                </q-item>
                <q-separator />
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu"
                    >한국어 가능 외국인 채용</q-item-section
                  >
                </q-item>
              </q-list>
            </q-menu>
          </div>
          <div class="cursor-pointer non-selectable">
            해외 개발자 활용 서비스
          </div>
        </div>
        <q-btn
          flat
          label="문의하기"
          style="
            font-weight: 900;
            background-color: white;
            color: rgb(74, 119, 255);
            border-radius: 8px;
            padding: 6px 24px;
          "
        />
      </q-toolbar>
    </q-header>
    <q-header
      class="absolute-top bg-transparent text-white container q-px-md"
      v-else
    >
      <q-toolbar
        class="row no-wrap items-center flex items-center justify-between"
        style="gap: 36px; padding: 13px 0px"
      >
        <img
          alt="Hyperhire Logo"
          src="data:image/png;base64,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"
          style="width: 114px; height: 21px"
        />
        <q-drawer
          v-model="drawerRight"
          show-if-above
          :width="300"
          side="right"
          overlay
          class="bg-white"
        >
          <q-scroll-area class="fit">
            <div class="q-pa-lg text-color-1">
              <q-list style="min-width: 100px; margin-bottom: 32px">
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu-bold">채용</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu q-pl-md"
                    >해외 개발자 원격 채용</q-item-section
                  >
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu q-pl-md"
                    >외국인 원격 채용 (비개발 직군)</q-item-section
                  >
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu q-pl-md"
                    >한국어 가능 외국인 채용</q-item-section
                  >
                </q-item>
                <q-separator />
                <q-item clickable v-close-popup>
                  <q-item-section class="text-menu-bold">
                    해외 개발자 활용 서비스
                  </q-item-section>
                </q-item>
              </q-list>
              <q-btn
                flat
                label="문의하기"
                style="
                  background-color: rgb(38, 194, 185);
                  color: rgb(255, 255, 255);
                  border-radius: 8px;
                  padding: 6px 24px;
                  width: 100%;
                "
              />
            </div>
          </q-scroll-area>
        </q-drawer>
        <q-btn flat round dense
          ><q-icon name="menu" @click="drawerRight = !drawerRight" />
        </q-btn>
      </q-toolbar>
    </q-header>
    <q-page-container style="padding-top: 0px">
      <q-page
        class="bg-gradient text-white"
        style="padding: 122px 0px; overflow: hidden"
      >
        <div class="container">
          <div class="grid-cols-2 grid" style="gap: 36px">
            <div class="column" style="gap: 60px">
              <div class="column" style="gap: 24px">
                <div class="column" style="gap: 16px">
                  <div style="position: relative">
                    <div
                      class="text-color-8"
                      style="
                        font-size: 18px;
                        width: fit-content;
                        padding: 6px 12px;
                        border-radius: 8px;
                        background-color: rgb(255, 255, 255);
                      "
                    >
                      풀타임, 파트타임
                    </div>
                    <svg
                      width="12"
                      height="11"
                      viewBox="0 0 12 11"
                      fill="none"
                      xmlns="http://www.w3.org/2000/svg"
                      style="
                        position: absolute;
                        bottom: -9px;
                        left: 9px;
                        color: rgb(255, 255, 255);
                      "
                    >
                      <path
                        d="M6.43301 10.25C6.24056 10.5833 5.75944 10.5833 5.56699 10.25L0.370835 1.25C0.178386 0.916665 0.418948 0.499999 0.803848 0.499999L11.1962 0.5C11.5811 0.5 11.8216 0.916667 11.6292 1.25L6.43301 10.25Z"
                        fill="currentColor"
                      ></path>
                    </svg>
                  </div>
                  <div style="font-size: 48px">
                    최고의 실력을 가진<br />
                    외국인 인재를 찾고 계신가요?
                  </div>
                  <div style="font-size: 24px">
                    법률 및 인사관리 부담없이<br />
                    1주일 이내에 원격으로 채용해보세요.
                  </div>
                </div>
                <div style="font-size: 18px">개발자가 필요하신가요?</div>
              </div>
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
            </div>
            <div style="padding-top: 0px">
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
                <swiper
                  :effect="'cards'"
                  :grabCursor="true"
                  :modules="modules"
                  :centered-slides="true"
                  :cards-effect="{
                    slideShadows: false,
                    rotate: false,
                    perSlideOffset: 21,
                  }"
                >
                  <swiper-slide>
                    <div
                      class="bg-white q-pa-lg column"
                      style="
                        border-radius: 12px;
                        gap: 36px;
                        box-shadow: rgba(0, 0, 0, 0.12) 0px 15px 24px 0px;
                      "
                    >
                      <div class="column items-center" style="gap: 16px">
                        <div style="position: relative">
                          <q-avatar style="font-size: 120px">
                            <img
                              src="https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png"
                            />
                          </q-avatar>
                          <img
                            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAASCAYAAACuLnWgAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAACPSURBVHgB7ZUxCsJgDIW/hB6gIt0d6nW8gmfwBOoNPJnoLthdkH8W6tMiVBHEpSki/aaEPHghb4hpX8xrsRGe0zGOKjetrN4VR8GEOJIHGzTkTg8MJr9nkoHaxnh2r/W3GW+6K4/tW305W37Sd0Z2OI2J5o+CLy9norHtaBoefG+ZJGJpfgqL+9UqYkgS6xt2UiXTpL5DFAAAAABJRU5ErkJggg=="
                            style="position: absolute; bottom: 0px; right: 14px"
                          />
                        </div>
                        <div class="column items-center">
                          <div class="text-color-2f" style="font-size: 24px">
                            Abhishek Gupta
                          </div>
                          <div class="text-color-ff" style="font-size: 16px">
                            마케팅 · 2y+
                          </div>
                        </div>
                      </div>
                      <div
                        class="text-color-f column"
                        style="gap: 4px; font-size: 16px"
                      >
                        <div class="column items-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            마케팅 콘텐츠 제작
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            인스타그램 관리
                          </div>
                        </div>
                        <div class="row justify-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            트위터 관리
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            블로그 글 작성
                          </div>
                        </div>
                      </div>
                    </div>
                  </swiper-slide>
                  <swiper-slide
                    ><div
                      class="bg-white q-pa-lg column"
                      style="
                        border-radius: 12px;
                        gap: 36px;
                        box-shadow: rgba(0, 0, 0, 0.12) 0px 15px 24px 0px;
                      "
                    >
                      <div class="column items-center" style="gap: 16px">
                        <div style="position: relative">
                          <q-avatar style="font-size: 120px">
                            <img
                              src="https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png"
                            />
                          </q-avatar>
                          <img
                            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAASCAYAAACuLnWgAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAACPSURBVHgB7ZUxCsJgDIW/hB6gIt0d6nW8gmfwBOoNPJnoLthdkH8W6tMiVBHEpSki/aaEPHghb4hpX8xrsRGe0zGOKjetrN4VR8GEOJIHGzTkTg8MJr9nkoHaxnh2r/W3GW+6K4/tW305W37Sd0Z2OI2J5o+CLy9norHtaBoefG+ZJGJpfgqL+9UqYkgS6xt2UiXTpL5DFAAAAABJRU5ErkJggg=="
                            style="position: absolute; bottom: 0px; right: 14px"
                          />
                        </div>
                        <div class="column items-center">
                          <div class="text-color-2f" style="font-size: 24px">
                            Abhishek Gupta
                          </div>
                          <div class="text-color-ff" style="font-size: 16px">
                            마케팅 · 2y+
                          </div>
                        </div>
                      </div>
                      <div
                        class="text-color-f column"
                        style="gap: 4px; font-size: 16px"
                      >
                        <div class="column items-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            마케팅 콘텐츠 제작
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            인스타그램 관리
                          </div>
                        </div>
                        <div class="row justify-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            트위터 관리
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            블로그 글 작성
                          </div>
                        </div>
                      </div>
                    </div></swiper-slide
                  ><swiper-slide
                    ><div
                      class="bg-white q-pa-lg column"
                      style="
                        border-radius: 12px;
                        gap: 36px;
                        box-shadow: rgba(0, 0, 0, 0.12) 0px 15px 24px 0px;
                      "
                    >
                      <div class="column items-center" style="gap: 16px">
                        <div style="position: relative">
                          <q-avatar style="font-size: 120px">
                            <img
                              src="https://hyperhire-lp.vercel.app/assets/avatar.f5767347.png"
                            />
                          </q-avatar>
                          <img
                            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAASCAYAAACuLnWgAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAACPSURBVHgB7ZUxCsJgDIW/hB6gIt0d6nW8gmfwBOoNPJnoLthdkH8W6tMiVBHEpSki/aaEPHghb4hpX8xrsRGe0zGOKjetrN4VR8GEOJIHGzTkTg8MJr9nkoHaxnh2r/W3GW+6K4/tW305W37Sd0Z2OI2J5o+CLy9norHtaBoefG+ZJGJpfgqL+9UqYkgS6xt2UiXTpL5DFAAAAABJRU5ErkJggg=="
                            style="position: absolute; bottom: 0px; right: 14px"
                          />
                        </div>
                        <div class="column items-center">
                          <div class="text-color-2f" style="font-size: 24px">
                            Abhishek Gupta
                          </div>
                          <div class="text-color-ff" style="font-size: 16px">
                            마케팅 · 2y+
                          </div>
                        </div>
                      </div>
                      <div
                        class="text-color-f column"
                        style="gap: 4px; font-size: 16px"
                      >
                        <div class="column items-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            마케팅 콘텐츠 제작
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            인스타그램 관리
                          </div>
                        </div>
                        <div class="row justify-center" style="gap: 4px">
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            트위터 관리
                          </div>
                          <div
                            class="q-py-xs q-px-sm"
                            style="
                              border: solid;
                              width: fit-content;
                              border-radius: 6px;
                              border-color: #c1c5cf;
                            "
                          >
                            블로그 글 작성
                          </div>
                        </div>
                      </div>
                    </div></swiper-slide
                  >
                </swiper>
                <q-btn
                  flat
                  round
                  style="position: absolute; left: -8px; top: 50%; z-index: 1"
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
            </div>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>
<script setup lang="ts">
import { ref } from 'vue';
import { useQuasar } from 'quasar';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/effect-cards';
import { EffectCards } from 'swiper/modules';

const $q = useQuasar();
const drawerRight = ref(false);
const modules = ref([EffectCards]);
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
