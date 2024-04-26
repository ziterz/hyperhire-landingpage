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
          src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKsAAAAgCAYAAABtn4gCAAAACXBIWXMAABCcAAAQnAEmzTo0AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAboSURBVHgB7ZvNbiNFEIArYbWcEEbwAJ1LbgiveIHZO2izT5DJE8QRD5DkCeIcOdm5IyUB7vaKB4hzg9PMHkBC/KwFJ1awRVemOi63u+enZ/yzm/mkkme6u/q3uqe6ZwxQEUTsaDnWkmDGKy0DLaqkvuL0CeuOtMTQ0tIkbGg36IYMb69Av8vpXFC+HWhpqQsbaoLF7Hv093IMtTXYlmaoYKhOg8X8FXXpBovtBHgYYOaj3mB1uqxfxVAbM1itH1l5Kmi5R/dHLPomgQBe/oX7yRRvklerWQy28yLZYEZaulCdkdb/ivWrNqbL+u2KuKFoA+2+eQNDoLHagktYAV5jrWmoxK9adrX8AWG0BrvZdDzXS8NprA0Y6k9aXvD1D1p+hzBag91Qdj7aGgPCqb5M9e9zWAGP7ICGDZV4reV7LV9o+QSqYwz26dbW1hRqwG2LtXzGQZTfC53vlZXmvu06bpyTl+yjVKdN2Vc3k2tCdeawyCr32pe3oyzSfSbyzdW36jbV6SYij1t9P/ToKf1Dm2PFQS+1DKldnjLGr/+DyeP37tKnIm6uD/g3hqz9R/Y4Otp3q+XKVe5cBTBsM2X4UcvXHhlo+Q3DqbTpwsUNFh2dJZ68RyZvzDaEkp4n/9hKpzh8LkzLGfpJMGfjx3UZ5ejfuPStupH+sbgfONIkWg7RvxE+dpRxIvWtuETExda9ssYoQT8DmX5bKDa9otqYFXZdLgENkvLERRxPKymtBGMR98yjcyiux55V4ExLD/woyNqk7AjMXrDccN18mD7JG7NIywnkQ33aB7/vSYbZgzCc/c4TYAT+MSFiEP2zzYrLNlTDOg2WdOjxc66FfK0rK35P5HshwiPbmPhe9tUFuNnjX1kupU1FGgU8Uaz8ZRilP9LyRMtTLQciD0p7WbJPaCLeOsKN7ljUM7XSHEM9ppw/uUURzE8gCqc27UDWPtmfCmRfYL1H/8/of/QvyyUYQAG46AYkaA0ozj/KiJjDyR2Sj8QTS68v87XibPqOcl2vrSMRP8irt8gjcdURF10USqcsfTvNwFHGpZVGefouzw2Yq5sj3nnshYvuWLSN2QCFrqhEmRXVhlbYbyGcGKt//HJqO/b6/gSyGW/ocjiFydl9aOUlXYMx+KFNV89RbgrZCiLD79764WwTaDhwbSw5j3Nb38Pz3M1KxmmJsBA7ueZ+voMnpRLxRy4ldsdk+cd0GnAI4fyi5W8I41/I3IGQEwKCBmdYIf3EE57CbBA+FOHkJpi+oZU2ot23o7NPwY83jk8JLkQZEf/aBnGMjg2OqZe4ppVWuYySBz6PqU9P5+krryx22ZEsV8vAKkOixHWXjLXOqhp64G/4E8KNVUE1plXC2TDHMOtc8j/pXq5gk4IVKy/uTl9cG0NQVpoIls8UVof9MiGCcnTIWKcQ/gbifajHYwhnFR18DbPO3GffKxLx5wX6nZrxRArlWaXRNUVaNiEZK83uCMJQUI+PIZyiR1sTDCHbBXdY6ChKifirAv2oII30fSfWr+FJ3ZchG4ZsH7kfO2UV6ejqCMKhlfFTCONzLR9AGCnk+4qN4NhoxeJ6WMKI6KDd6WbpcPJVIxF0y2XSYKYi3HtkhNmpgZE9eDugyWv6jfYCvu+fld2+be6cAwiHjK7qCrnLeqEclNjdNoVvZbyAcox0R/dw9oZL8Yapb6WT93Ii9uwNFmZHa7TKx0JW8aSpDU9w6T717ZMd7is60opZIi2Tbc5gCOEGS6vrl1DeYHeh3qbhoOw79SbgsmxDSCvUwbgPCWbbXjqTPLHSnMrJx+MhJwOdaZr/q91wHj2f/lsATcyUr6l/Bnz2Ktsnn0j0PUF6/7p1RQbbhKEOYfVcW/dlXRA5KD5O5TmkQYfFML8CmZ2z/EjEq7/J8OpK58ypCFYwa5+B0h2YD40eWZkM+VD6DKpjDPY7cB9prdpQzes9ee/i1nMtSa37MZSD8iODO4HFr6buDr3zVmh6oaDHg9KRXxeJKNKnAbzw6Mu25x3ZmTQp+BmL69S69ulLv9vpnvCTYIddAPLfbSOlJ0u/8ImBi68hq/CPlm9w/vXqCOsRwxqx6n9VkNZbb8z8VQXh9ailv8lg5oeHtQ+bM9gR1iOGNcIdKNkrSL8xdX9QYDMGW4cY1gxaH5WUSL9R9X9QYLjBXrL+EMOIYc3g4qpa5muvjWrDu8SjogS008TsQ4Mq3zPen93Srpb190vqknN9tKZdvw1tiIbivswpgEyfQsvqwfIrrPPvJxVW2C60tNSlhMGOMOeLdSzebMXQ0tIUuPgHMEO/hG7Hs8JSfhG0tOSwBQHw6hlBdpB7d8Bd5RUozv7DRL8T1n+XvixqWQL/A7/HP9FRq6w2AAAAAElFTkSuQmCC"
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
          src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKsAAAAgCAYAAABtn4gCAAAACXBIWXMAABCcAAAQnAEmzTo0AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAboSURBVHgB7ZvNbiNFEIArYbWcEEbwAJ1LbgiveIHZO2izT5DJE8QRD5DkCeIcOdm5IyUB7vaKB4hzg9PMHkBC/KwFJ1awRVemOi63u+enZ/yzm/mkkme6u/q3uqe6ZwxQEUTsaDnWkmDGKy0DLaqkvuL0CeuOtMTQ0tIkbGg36IYMb69Av8vpXFC+HWhpqQsbaoLF7Hv093IMtTXYlmaoYKhOg8X8FXXpBovtBHgYYOaj3mB1uqxfxVAbM1itH1l5Kmi5R/dHLPomgQBe/oX7yRRvklerWQy28yLZYEZaulCdkdb/ivWrNqbL+u2KuKFoA+2+eQNDoLHagktYAV5jrWmoxK9adrX8AWG0BrvZdDzXS8NprA0Y6k9aXvD1D1p+hzBag91Qdj7aGgPCqb5M9e9zWAGP7ICGDZV4reV7LV9o+QSqYwz26dbW1hRqwG2LtXzGQZTfC53vlZXmvu06bpyTl+yjVKdN2Vc3k2tCdeawyCr32pe3oyzSfSbyzdW36jbV6SYij1t9P/ToKf1Dm2PFQS+1DKldnjLGr/+DyeP37tKnIm6uD/g3hqz9R/Y4Otp3q+XKVe5cBTBsM2X4UcvXHhlo+Q3DqbTpwsUNFh2dJZ68RyZvzDaEkp4n/9hKpzh8LkzLGfpJMGfjx3UZ5ejfuPStupH+sbgfONIkWg7RvxE+dpRxIvWtuETExda9ssYoQT8DmX5bKDa9otqYFXZdLgENkvLERRxPKymtBGMR98yjcyiux55V4ExLD/woyNqk7AjMXrDccN18mD7JG7NIywnkQ33aB7/vSYbZgzCc/c4TYAT+MSFiEP2zzYrLNlTDOg2WdOjxc66FfK0rK35P5HshwiPbmPhe9tUFuNnjX1kupU1FGgU8Uaz8ZRilP9LyRMtTLQciD0p7WbJPaCLeOsKN7ljUM7XSHEM9ppw/uUURzE8gCqc27UDWPtmfCmRfYL1H/8/of/QvyyUYQAG46AYkaA0ozj/KiJjDyR2Sj8QTS68v87XibPqOcl2vrSMRP8irt8gjcdURF10USqcsfTvNwFHGpZVGefouzw2Yq5sj3nnshYvuWLSN2QCFrqhEmRXVhlbYbyGcGKt//HJqO/b6/gSyGW/ocjiFydl9aOUlXYMx+KFNV89RbgrZCiLD79764WwTaDhwbSw5j3Nb38Pz3M1KxmmJsBA7ueZ+voMnpRLxRy4ldsdk+cd0GnAI4fyi5W8I41/I3IGQEwKCBmdYIf3EE57CbBA+FOHkJpi+oZU2ot23o7NPwY83jk8JLkQZEf/aBnGMjg2OqZe4ppVWuYySBz6PqU9P5+krryx22ZEsV8vAKkOixHWXjLXOqhp64G/4E8KNVUE1plXC2TDHMOtc8j/pXq5gk4IVKy/uTl9cG0NQVpoIls8UVof9MiGCcnTIWKcQ/gbifajHYwhnFR18DbPO3GffKxLx5wX6nZrxRArlWaXRNUVaNiEZK83uCMJQUI+PIZyiR1sTDCHbBXdY6ChKifirAv2oII30fSfWr+FJ3ZchG4ZsH7kfO2UV6ejqCMKhlfFTCONzLR9AGCnk+4qN4NhoxeJ6WMKI6KDd6WbpcPJVIxF0y2XSYKYi3HtkhNmpgZE9eDugyWv6jfYCvu+fld2+be6cAwiHjK7qCrnLeqEclNjdNoVvZbyAcox0R/dw9oZL8Yapb6WT93Ii9uwNFmZHa7TKx0JW8aSpDU9w6T717ZMd7is60opZIi2Tbc5gCOEGS6vrl1DeYHeh3qbhoOw79SbgsmxDSCvUwbgPCWbbXjqTPLHSnMrJx+MhJwOdaZr/q91wHj2f/lsATcyUr6l/Bnz2Ktsnn0j0PUF6/7p1RQbbhKEOYfVcW/dlXRA5KD5O5TmkQYfFML8CmZ2z/EjEq7/J8OpK58ypCFYwa5+B0h2YD40eWZkM+VD6DKpjDPY7cB9prdpQzes9ee/i1nMtSa37MZSD8iODO4HFr6buDr3zVmh6oaDHg9KRXxeJKNKnAbzw6Mu25x3ZmTQp+BmL69S69ulLv9vpnvCTYIddAPLfbSOlJ0u/8ImBi68hq/CPlm9w/vXqCOsRwxqx6n9VkNZbb8z8VQXh9ailv8lg5oeHtQ+bM9gR1iOGNcIdKNkrSL8xdX9QYDMGW4cY1gxaH5WUSL9R9X9QYLjBXrL+EMOIYc3g4qpa5muvjWrDu8SjogS008TsQ4Mq3zPen93Srpb190vqknN9tKZdvw1tiIbivswpgEyfQsvqwfIrrPPvJxVW2C60tNSlhMGOMOeLdSzebMXQ0tIUuPgHMEO/hG7Hs8JSfhG0tOSwBQHw6hlBdpB7d8Bd5RUozv7DRL8T1n+XvixqWQL/A7/HP9FRq6w2AAAAAElFTkSuQmCC"
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
                <BigSwiper />
              </div>
            </div>
          </div>
        </div>
        <MiniSwiper />
      </q-page>
    </q-page-container>
    <footer>
      <div class="column container" style="gap: 48px">
        <div class="grid grid-cols-12" style="gap: 14px">
          <div class="column col-span-4" style="gap: 16px">
            <img
              alt="Hyperhire Logo"
              src="https://hyperhire-lp.vercel.app/assets/dark.9554a17b.png"
              style="width: 187px; height: 34px"
            />
            <div class="text-weight-bolder text-color-1">
              우리는 국가의 장벽을 넘어 최고의 인재를 매칭해드립니다.
            </div>
            <div class="text-color-f">
              <div>010-0000-0000</div>
              <div>aaaaa@naver.com</div>
            </div>
          </div>
          <div
            class="bg-white q-pa-md column col-span-2"
            style="border-radius: 12px; gap: 16px"
          >
            <div class="column" style="gap: 12px">
              <div
                class="flex items-center justify-center"
                style="
                  width: 40px;
                  height: 40px;
                  background-color: rgb(239, 241, 246);
                  border-radius: 8px;
                "
              >
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <g clip-path="url(#clip0_2001_331)">
                    <path
                      d="M4.45575 17.1767C4.6234 17.3386 4.84794 17.4282 5.081 17.4262C5.31407 17.4242 5.53702 17.3307 5.70183 17.1659C5.86664 17.0011 5.96013 16.7781 5.96215 16.5451C5.96418 16.312 5.87458 16.0875 5.71266 15.9198L1.89669 12.1037L5.71266 8.28769C5.87458 8.12004 5.96418 7.8955 5.96215 7.66243C5.96013 7.42936 5.86664 7.20641 5.70183 7.0416C5.53702 6.87679 5.31407 6.78331 5.081 6.78128C4.84794 6.77926 4.6234 6.86885 4.45575 7.03078L0.0112346 11.4753C-0.155409 11.642 -0.249023 11.868 -0.249023 12.1037C-0.249023 12.3394 -0.155409 12.5655 0.0112346 12.7322L4.45575 17.1767Z"
                      fill="#7388A9"
                    ></path>
                    <path
                      d="M17.7893 17.1767C17.956 17.3434 18.1821 17.437 18.4178 17.437C18.6535 17.437 18.8795 17.3434 19.0462 17.1767L23.4907 12.7322C23.6574 12.5655 23.751 12.3395 23.751 12.1037C23.751 11.868 23.6574 11.642 23.4907 11.4753L19.0462 7.03078C18.8786 6.86885 18.654 6.77926 18.421 6.78128C18.1879 6.78331 17.9649 6.87679 17.8001 7.0416C17.6353 7.20641 17.5418 7.42936 17.5398 7.66243C17.5378 7.8955 17.6274 8.12004 17.7893 8.28769L21.6053 12.1037L17.7893 15.9198C17.6227 16.0865 17.5291 16.3126 17.5291 16.5483C17.5291 16.784 17.6227 17.01 17.7893 17.1767Z"
                      fill="#7388A9"
                    ></path>
                    <path
                      d="M8.73406 19.1432C8.84138 19.1892 8.95671 19.2137 9.07347 19.2151C9.19024 19.2166 9.30614 19.195 9.41456 19.1516C9.52298 19.1082 9.62179 19.0439 9.70535 18.9623C9.78891 18.8808 9.85557 18.7835 9.90154 18.6762L15.235 6.23155C15.3278 6.0148 15.3308 5.77003 15.2432 5.55109C15.1557 5.33214 14.9847 5.15696 14.7679 5.06407C14.5512 4.97118 14.3064 4.9682 14.0875 5.05579C13.8685 5.14337 13.6933 5.31435 13.6004 5.5311L8.26703 17.9757C8.221 18.0831 8.19657 18.1984 8.19514 18.3152C8.1937 18.4319 8.21528 18.5478 8.25866 18.6562C8.30203 18.7647 8.36633 18.8635 8.4479 18.947C8.52948 19.0306 8.62671 19.0973 8.73406 19.1432Z"
                      fill="#7388A9"
                    ></path>
                  </g>
                  <defs>
                    <clipPath id="clip0_2001_331">
                      <rect width="24" height="24" fill="white"></rect>
                    </clipPath>
                  </defs>
                </svg>
              </div>
              <div class="text-color-1">해외 개발자 원격 채용</div>
            </div>
            <div class="text-color-f flex items-center" style="gap: 8px">
              바로가기
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M6.59663 2.91675C4.36079 2.91675 2.91663 4.27925 2.91663 6.38758V13.6117C2.91663 15.7201 4.36079 17.0834 6.59663 17.0834H13.4033C15.6391 17.0834 17.0833 15.7201 17.0833 13.6117V6.38758C17.0833 4.27925 15.6391 2.91675 13.4033 2.91675H6.59663ZM13.4033 18.3334H6.59663C3.64829 18.3334 1.66663 16.4359 1.66663 13.6117V6.38758C1.66663 3.56341 3.64829 1.66675 6.59663 1.66675H13.4033C16.3516 1.66675 18.3333 3.56341 18.3333 6.38758V13.6117C18.3333 16.4359 16.3516 18.3334 13.4033 18.3334Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M13.4048 10.625H6.59485C6.24985 10.625 5.96985 10.345 5.96985 10C5.96985 9.655 6.24985 9.375 6.59485 9.375H13.4048C13.7498 9.375 14.0298 9.655 14.0298 10C14.0298 10.345 13.7498 10.625 13.4048 10.625Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M10.2685 13.7484C10.1085 13.7484 9.94769 13.6876 9.82602 13.5642C9.58269 13.3192 9.58352 12.9242 9.82769 12.6809L12.5194 10.0001L9.82769 7.31925C9.58352 7.07591 9.58269 6.68091 9.82602 6.43591C10.0694 6.19091 10.4644 6.19091 10.7094 6.43425L13.846 9.55758C13.9644 9.67425 14.0302 9.83425 14.0302 10.0001C14.0302 10.1659 13.9644 10.3259 13.846 10.4426L10.7094 13.5659C10.5877 13.6876 10.4277 13.7484 10.2685 13.7484Z"
                  fill="#5E626F"
                ></path>
              </svg>
            </div>
          </div>
          <div
            class="bg-white q-pa-md column col-span-2"
            style="border-radius: 12px; gap: 16px"
          >
            <div class="column" style="gap: 12px">
              <div
                class="flex items-center justify-center"
                style="
                  width: 40px;
                  height: 40px;
                  background-color: rgb(239, 241, 246);
                  border-radius: 8px;
                "
              >
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M11.9142 12.0336C13.0384 12.0336 13.9751 11.6609 14.8182 10.9154C15.7549 10.1697 16.2233 8.95812 16.2233 7.74654C16.2233 6.81455 15.9423 5.88257 15.3803 5.23018C14.6308 4.1118 13.413 3.36621 11.9142 3.36621C9.57231 3.36621 7.6051 5.32338 7.6051 7.65334C7.6051 10.0765 9.57231 12.0336 11.9142 12.0336Z"
                    fill="#7A8FAD"
                  ></path>
                  <path
                    d="M14.3965 14.271C14.1155 14.271 13.9281 14.1777 13.6471 14.1777H10.0874C7.37079 14.1777 5.12256 16.4146 5.12256 19.1173C5.12256 19.7697 5.40359 20.2357 5.87197 20.6085C6.62138 21.0745 8.40123 21.6335 11.8673 21.6335C15.3333 21.6335 17.0194 21.0745 17.8625 20.6085C17.8625 20.6085 17.9562 20.5153 18.0499 20.5153C18.4246 20.2357 18.7056 19.7697 18.7056 19.1173C18.6119 16.6942 16.8321 14.6438 14.3965 14.271Z"
                    fill="#7A8FAD"
                  ></path>
                </svg>
              </div>
              <div class="text-color-1">외국인 원격 채용 (비개발)</div>
            </div>
            <div class="text-color-f flex items-center" style="gap: 8px">
              바로가기
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M6.59663 2.91675C4.36079 2.91675 2.91663 4.27925 2.91663 6.38758V13.6117C2.91663 15.7201 4.36079 17.0834 6.59663 17.0834H13.4033C15.6391 17.0834 17.0833 15.7201 17.0833 13.6117V6.38758C17.0833 4.27925 15.6391 2.91675 13.4033 2.91675H6.59663ZM13.4033 18.3334H6.59663C3.64829 18.3334 1.66663 16.4359 1.66663 13.6117V6.38758C1.66663 3.56341 3.64829 1.66675 6.59663 1.66675H13.4033C16.3516 1.66675 18.3333 3.56341 18.3333 6.38758V13.6117C18.3333 16.4359 16.3516 18.3334 13.4033 18.3334Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M13.4048 10.625H6.59485C6.24985 10.625 5.96985 10.345 5.96985 10C5.96985 9.655 6.24985 9.375 6.59485 9.375H13.4048C13.7498 9.375 14.0298 9.655 14.0298 10C14.0298 10.345 13.7498 10.625 13.4048 10.625Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M10.2685 13.7484C10.1085 13.7484 9.94769 13.6876 9.82602 13.5642C9.58269 13.3192 9.58352 12.9242 9.82769 12.6809L12.5194 10.0001L9.82769 7.31925C9.58352 7.07591 9.58269 6.68091 9.82602 6.43591C10.0694 6.19091 10.4644 6.19091 10.7094 6.43425L13.846 9.55758C13.9644 9.67425 14.0302 9.83425 14.0302 10.0001C14.0302 10.1659 13.9644 10.3259 13.846 10.4426L10.7094 13.5659C10.5877 13.6876 10.4277 13.7484 10.2685 13.7484Z"
                  fill="#5E626F"
                ></path>
              </svg>
            </div>
          </div>
          <div
            class="bg-white q-pa-md column col-span-2"
            style="border-radius: 12px; gap: 16px"
          >
            <div class="column" style="gap: 12px">
              <div
                class="flex items-center justify-center"
                style="
                  width: 40px;
                  height: 40px;
                  background-color: rgb(239, 241, 246);
                  border-radius: 8px;
                "
              >
                <svg
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M21.0836 9.24894C20.6824 9.19298 20.2994 9.05084 19.9633 8.83309C19.6272 8.61535 19.3466 8.32761 19.1424 7.99131C18.9382 7.65501 18.8156 7.27882 18.7839 6.89073C18.7521 6.50265 18.8119 6.11268 18.9588 5.74987C19.0522 5.51267 19.066 5.25336 18.9982 5.00828C18.9303 4.7632 18.7843 4.54464 18.5806 4.38325C17.6812 3.65813 16.6575 3.08849 15.5551 2.69974C15.304 2.6102 15.0299 2.59901 14.7719 2.66777C14.5139 2.73652 14.285 2.88171 14.1179 3.08265C13.8664 3.3914 13.545 3.64111 13.1781 3.81284C12.8111 3.98458 12.4082 4.07383 12 4.07383C11.5918 4.07383 11.1889 3.98458 10.822 3.81284C10.455 3.64111 10.1336 3.3914 9.88211 3.08265C9.71503 2.88171 9.48616 2.73652 9.22811 2.66777C8.97007 2.59901 8.696 2.6102 8.44496 2.69974C7.42704 3.05865 6.47531 3.57125 5.62568 4.2182C5.41151 4.38098 5.25725 4.60532 5.18549 4.85836C5.11372 5.11141 5.12822 5.37987 5.22685 5.62443C5.38553 5.99684 5.45109 6.39978 5.41827 6.80091C5.38546 7.20204 5.25518 7.59021 5.03789 7.93427C4.82061 8.27833 4.52236 8.56871 4.16707 8.78211C3.81179 8.99552 3.40936 9.12601 2.99206 9.16311C2.72114 9.19092 2.46668 9.30151 2.26614 9.4786C2.0656 9.65569 1.92957 9.88993 1.8781 10.1468C1.75006 10.7553 1.68556 11.3746 1.68556 11.9954C1.68462 12.5151 1.72832 13.034 1.81621 13.5469C1.85995 13.812 1.99345 14.0559 2.19604 14.2408C2.39864 14.4258 2.65907 14.5415 2.93705 14.5702C3.36351 14.6086 3.77419 14.7445 4.1347 14.9666C4.49521 15.1887 4.79506 15.4905 5.00917 15.8467C5.22328 16.2028 5.34541 16.6031 5.36534 17.0139C5.38526 17.4247 5.30241 17.8341 5.12371 18.2079C5.00676 18.451 4.97775 18.7246 5.04129 18.9854C5.10483 19.2461 5.25726 19.479 5.4744 19.6471C6.3684 20.3591 7.38228 20.9195 8.47247 21.3042C8.61188 21.3506 8.75815 21.3751 8.90567 21.3768C9.10795 21.3764 9.30718 21.3294 9.48665 21.2398C9.66611 21.1502 9.82059 21.0206 9.93712 20.8619C10.1822 20.5191 10.5107 20.2388 10.8942 20.0455C11.2776 19.8523 11.7044 19.7518 12.1375 19.7527C12.5572 19.7533 12.9709 19.8478 13.3457 20.0289C13.7206 20.21 14.0462 20.4726 14.2967 20.7959C14.4633 21.0109 14.6993 21.167 14.968 21.2398C15.2366 21.3127 15.5228 21.2982 15.782 21.1986C16.7788 20.8134 17.7069 20.281 18.5325 19.6207C18.7399 19.4561 18.8876 19.2325 18.9543 18.9822C19.021 18.7319 19.0033 18.4677 18.9038 18.2277C18.7421 17.8601 18.6716 17.4614 18.6978 17.0631C18.7241 16.6649 18.8464 16.2779 19.0551 15.9328C19.2638 15.5877 19.5533 15.2939 19.9005 15.0746C20.2478 14.8553 20.6434 14.7165 21.0561 14.6692C21.3237 14.6337 21.5726 14.5173 21.7667 14.3368C21.9608 14.1564 22.09 13.9213 22.1357 13.6657C22.2461 13.115 22.3059 12.5561 22.3145 11.9954C22.3146 11.4039 22.257 10.8138 22.1425 10.2326C22.0961 9.98262 21.9688 9.75301 21.7787 9.57642C21.5886 9.39983 21.3454 9.28524 21.0836 9.24894ZM15.4382 11.9954C15.4382 12.6483 15.2365 13.2865 14.8587 13.8293C14.4809 14.3722 13.944 14.7953 13.3157 15.0451C12.6875 15.295 11.9962 15.3603 11.3293 15.233C10.6623 15.1056 10.0497 14.7912 9.56887 14.3295C9.08804 13.8679 8.76058 13.2797 8.62792 12.6394C8.49526 11.999 8.56335 11.3353 8.82357 10.7321C9.0838 10.129 9.52447 9.61341 10.0899 9.25069C10.6553 8.88797 11.32 8.69437 12 8.69437C12.9119 8.69437 13.7864 9.04215 14.4311 9.66121C15.0759 10.2803 15.4382 11.1199 15.4382 11.9954Z"
                    fill="#7A8FAD"
                  ></path>
                </svg>
              </div>
              <div class="text-color-1">한국어 가능 외국인 채용</div>
            </div>
            <div class="text-color-f flex items-center" style="gap: 8px">
              바로가기
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M6.59663 2.91675C4.36079 2.91675 2.91663 4.27925 2.91663 6.38758V13.6117C2.91663 15.7201 4.36079 17.0834 6.59663 17.0834H13.4033C15.6391 17.0834 17.0833 15.7201 17.0833 13.6117V6.38758C17.0833 4.27925 15.6391 2.91675 13.4033 2.91675H6.59663ZM13.4033 18.3334H6.59663C3.64829 18.3334 1.66663 16.4359 1.66663 13.6117V6.38758C1.66663 3.56341 3.64829 1.66675 6.59663 1.66675H13.4033C16.3516 1.66675 18.3333 3.56341 18.3333 6.38758V13.6117C18.3333 16.4359 16.3516 18.3334 13.4033 18.3334Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M13.4048 10.625H6.59485C6.24985 10.625 5.96985 10.345 5.96985 10C5.96985 9.655 6.24985 9.375 6.59485 9.375H13.4048C13.7498 9.375 14.0298 9.655 14.0298 10C14.0298 10.345 13.7498 10.625 13.4048 10.625Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M10.2685 13.7484C10.1085 13.7484 9.94769 13.6876 9.82602 13.5642C9.58269 13.3192 9.58352 12.9242 9.82769 12.6809L12.5194 10.0001L9.82769 7.31925C9.58352 7.07591 9.58269 6.68091 9.82602 6.43591C10.0694 6.19091 10.4644 6.19091 10.7094 6.43425L13.846 9.55758C13.9644 9.67425 14.0302 9.83425 14.0302 10.0001C14.0302 10.1659 13.9644 10.3259 13.846 10.4426L10.7094 13.5659C10.5877 13.6876 10.4277 13.7484 10.2685 13.7484Z"
                  fill="#5E626F"
                ></path>
              </svg>
            </div>
          </div>
          <div
            class="bg-white q-pa-md column col-span-2"
            style="border-radius: 12px; gap: 16px"
          >
            <div class="column" style="gap: 12px">
              <div
                class="flex items-center justify-center"
                style="
                  width: 40px;
                  height: 40px;
                  background-color: rgb(239, 241, 246);
                  border-radius: 8px;
                "
              >
                <svg
                  width="23"
                  height="9"
                  viewBox="0 0 23 9"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M0.813539 8.08929C0.582885 8.08929 0.404315 8.02604 0.277827 7.89955C0.15878 7.76563 0.0992567 7.58334 0.0992567 7.35268V0.767889C0.0992567 0.529794 0.15878 0.351224 0.277827 0.232176C0.404315 0.105689 0.582885 0.0424448 0.813539 0.0424448C1.04419 0.0424448 1.21904 0.105689 1.33809 0.232176C1.46458 0.351224 1.52782 0.529794 1.52782 0.767889V3.61386H1.55014L4.75325 0.399586C4.8723 0.280539 4.99135 0.191254 5.1104 0.13173C5.22944 0.0722067 5.36337 0.0424448 5.51218 0.0424448C5.72795 0.0424448 5.88048 0.0982483 5.96977 0.209855C6.06649 0.321462 6.1037 0.45167 6.08137 0.600478C6.06649 0.749287 5.99581 0.886936 5.86932 1.01342L2.61041 4.23886L2.62157 3.59154L6.02557 7.05134C6.18182 7.20015 6.26366 7.3564 6.27111 7.52009C6.27855 7.68378 6.22646 7.82143 6.11486 7.93304C6.01069 8.0372 5.85444 8.08929 5.64611 8.08929C5.46754 8.08929 5.32245 8.05208 5.21084 7.97768C5.10668 7.90327 4.98391 7.79539 4.84254 7.65402L1.55014 4.36162H1.52782V7.35268C1.52782 7.58334 1.4683 7.76563 1.34925 7.89955C1.2302 8.02604 1.05163 8.08929 0.813539 8.08929ZM10.7322 8.11161C9.97331 8.11161 9.30739 7.9442 8.73447 7.60938C8.169 7.27456 7.73001 6.80581 7.41751 6.20313C7.10502 5.59302 6.94877 4.87873 6.94877 4.06028C6.94877 3.44273 7.03805 2.88841 7.21662 2.39735C7.39519 1.89884 7.64817 1.47473 7.97555 1.12503C8.31037 0.767888 8.70843 0.496312 9.16974 0.310301C9.63849 0.11685 10.1593 0.0201238 10.7322 0.0201238C11.4986 0.0201238 12.1645 0.187534 12.73 0.522354C13.2955 0.849733 13.7345 1.31476 14.047 1.91744C14.3594 2.52011 14.5157 3.23068 14.5157 4.04912C14.5157 4.66668 14.4264 5.22471 14.2478 5.72322C14.0693 6.22173 13.8126 6.64956 13.4778 7.0067C13.1504 7.36384 12.7523 7.63914 12.2836 7.83259C11.8223 8.0186 11.3051 8.11161 10.7322 8.11161ZM10.7322 6.88393C11.2159 6.88393 11.6251 6.77233 11.9599 6.54911C12.3022 6.3259 12.5626 6.00224 12.7412 5.57814C12.9272 5.15403 13.0202 4.64808 13.0202 4.06028C13.0202 3.16743 12.8193 2.47547 12.4175 1.9844C12.0231 1.49333 11.4614 1.2478 10.7322 1.2478C10.256 1.2478 9.84682 1.3594 9.50456 1.58262C9.1623 1.79839 8.89816 2.11833 8.71215 2.54243C8.53358 2.9591 8.4443 3.46505 8.4443 4.06028C8.4443 4.9457 8.64519 5.63766 9.04697 6.13617C9.44876 6.63468 10.0105 6.88393 10.7322 6.88393ZM16.6826 8.08929C16.452 8.08929 16.2734 8.02604 16.1469 7.89955C16.0279 7.76563 15.9683 7.58334 15.9683 7.35268V0.857174C15.9683 0.619079 16.0316 0.440509 16.1581 0.321462C16.2845 0.194974 16.4631 0.13173 16.6938 0.13173H19.3835C20.2466 0.13173 20.9125 0.340063 21.3812 0.756728C21.85 1.16595 22.0844 1.74259 22.0844 2.48663C22.0844 2.97026 21.9765 3.38692 21.7607 3.73663C21.5524 4.08633 21.2473 4.35418 20.8455 4.54019C20.4438 4.7262 19.9564 4.81921 19.3835 4.81921L19.4839 4.6518H19.8522C20.1573 4.6518 20.4214 4.7262 20.6446 4.87501C20.8753 5.02382 21.0762 5.2582 21.2473 5.57814L22.0844 7.12947C22.1737 7.28572 22.2146 7.43825 22.2071 7.58706C22.1997 7.73586 22.1439 7.85863 22.0397 7.95536C21.9356 8.04464 21.783 8.08929 21.5821 8.08929C21.3812 8.08929 21.2176 8.04836 21.0911 7.96652C20.9646 7.87723 20.853 7.7433 20.7563 7.56473L19.629 5.48885C19.4951 5.23588 19.3351 5.06847 19.1491 4.98662C18.9705 4.89733 18.7399 4.85269 18.4572 4.85269H17.3969V7.35268C17.3969 7.58334 17.3374 7.76563 17.2183 7.89955C17.0993 8.02604 16.9207 8.08929 16.6826 8.08929ZM17.3969 3.79243H19.138C19.6513 3.79243 20.0382 3.68826 20.2987 3.47993C20.5665 3.26416 20.7004 2.94422 20.7004 2.52011C20.7004 2.10345 20.5665 1.79095 20.2987 1.58262C20.0382 1.36684 19.6513 1.25896 19.138 1.25896H17.3969V3.79243Z"
                    fill="#7A8FAD"
                  ></path>
                </svg>
              </div>
              <div class="text-color-1">해외 개발자 활용 서비스</div>
            </div>
            <div class="text-color-f flex items-center" style="gap: 8px">
              바로가기
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M6.59663 2.91675C4.36079 2.91675 2.91663 4.27925 2.91663 6.38758V13.6117C2.91663 15.7201 4.36079 17.0834 6.59663 17.0834H13.4033C15.6391 17.0834 17.0833 15.7201 17.0833 13.6117V6.38758C17.0833 4.27925 15.6391 2.91675 13.4033 2.91675H6.59663ZM13.4033 18.3334H6.59663C3.64829 18.3334 1.66663 16.4359 1.66663 13.6117V6.38758C1.66663 3.56341 3.64829 1.66675 6.59663 1.66675H13.4033C16.3516 1.66675 18.3333 3.56341 18.3333 6.38758V13.6117C18.3333 16.4359 16.3516 18.3334 13.4033 18.3334Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M13.4048 10.625H6.59485C6.24985 10.625 5.96985 10.345 5.96985 10C5.96985 9.655 6.24985 9.375 6.59485 9.375H13.4048C13.7498 9.375 14.0298 9.655 14.0298 10C14.0298 10.345 13.7498 10.625 13.4048 10.625Z"
                  fill="#5E626F"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M10.2685 13.7484C10.1085 13.7484 9.94769 13.6876 9.82602 13.5642C9.58269 13.3192 9.58352 12.9242 9.82769 12.6809L12.5194 10.0001L9.82769 7.31925C9.58352 7.07591 9.58269 6.68091 9.82602 6.43591C10.0694 6.19091 10.4644 6.19091 10.7094 6.43425L13.846 9.55758C13.9644 9.67425 14.0302 9.83425 14.0302 10.0001C14.0302 10.1659 13.9644 10.3259 13.846 10.4426L10.7094 13.5659C10.5877 13.6876 10.4277 13.7484 10.2685 13.7484Z"
                  fill="#5E626F"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <div class="grid grid-cols-12" style="gap: 14px">
          <div class="row col-span-4" style="gap: 16px">
            <div class="column" style="gap: 8px">
              <div class="text-color-1" style="font-size: 12px">상호명</div>
              <div class="column" style="gap: 4px">
                <div class="text-color-f" style="font-size: 13px">
                  하이퍼하이어
                </div>
                <div class="text-color-f" style="font-size: 13px">
                  Hyperhire India Private Limited
                </div>
              </div>
            </div>
            <div class="column" style="gap: 8px">
              <div class="text-color-1" style="font-size: 12px">대표 CEO</div>
              <div class="column" style="gap: 4px">
                <div class="text-color-f" style="font-size: 13px">김주현</div>
                <div class="text-color-f" style="font-size: 13px">
                  Juhyun Kim
                </div>
              </div>
            </div>
          </div>
          <div class="column col-span-2" style="gap: 8px">
            <div class="text-color-1" style="font-size: 12px">
              사업자등록번호 CIN
            </div>
            <div class="column" style="gap: 4px">
              <div class="text-color-f" style="font-size: 13px">
                427-86-01187
              </div>
              <div class="text-color-f" style="font-size: 13px">
                U74110DL2016PTC290812
              </div>
            </div>
          </div>
          <div class="column col-span-6" style="gap: 8px">
            <div class="text-color-1" style="font-size: 12px">주소 ADDRESS</div>
            <div class="column" style="gap: 4px">
              <div class="text-color-f" style="font-size: 13px">
                서울특별시 강남대로 479, 지하 1층 238호
              </div>
              <div class="text-color-f" style="font-size: 13px">
                D-138, Street number 11, Jagjeet Nagar, North East Delhi, New
                Delhi, 110053 India
              </div>
            </div>
          </div>
        </div>
        <div class="text-color-f" style="font-size: 13px">ⓒ 2024 Hyperhire</div>
      </div>
    </footer>
  </q-layout>
</template>
<script setup lang="ts">
import { ref } from 'vue';
import { useQuasar } from 'quasar';
import BigSwiper from 'src/components/BigSwiper.vue';
import MiniSwiper from 'src/components/MiniSwiper.vue';

const $q = useQuasar();
const drawerRight = ref(false);
</script>
