<template>
  <q-layout view="hHh LpR fFf">
    <q-header class="absolute-top bg-transparent text-white container">
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
                  <q-item-section>채용</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section>해외 개발자 원격 채용</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section
                    >외국인 원격 채용 (비개발 직군)</q-item-section
                  >
                </q-item>
                <q-separator />
                <q-item clickable v-close-popup>
                  <q-item-section>한국어 가능 외국인 채용</q-item-section>
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
            background-color: white;
            color: rgb(74, 119, 255);
            border-radius: 8px;
            padding: 6px 24px;
          "
        />
      </q-toolbar>
    </q-header>
    <q-page-container style="padding-top: 0px">
      <q-page class="bg-gradient"></q-page>
    </q-page-container>
  </q-layout>
</template>
<script setup lang="ts"></script>
