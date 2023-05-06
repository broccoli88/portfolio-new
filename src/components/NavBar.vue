<script setup>
import { RouterLink } from 'vue-router'
import { ref } from 'vue'

const isMobileNavOpen = ref(false)
const toggleMobileMenu = () => {
      isMobileNavOpen.value = !isMobileNavOpen.value
}
</script>
<template>
      <nav class="nav">
            <router-link to="#">
                  <img class="nav__logo" src="../assets/images/Moon.svg" alt="" />
            </router-link>
            <figure class="nav__burger" @click="toggleMobileMenu">
                  <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36"
                        height="36"
                        viewBox="0 0 24 24"
                        class="open-nav"
                        v-if="!isMobileNavOpen"
                  >
                        <path
                              fill="none"
                              stroke="var(--base-font)"
                              stroke-linecap="round"
                              stroke-width="1.5"
                              d="M4 7h3m13 0h-9m9 10h-3M4 17h9m-9-5h16"
                        />
                  </svg>

                  <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36"
                        height="36"
                        viewBox="0 0 24 24"
                        class="close-nav"
                        v-else
                  >
                        <path
                              fill="var(--base-font)"
                              d="M19 6.41L17.59 5L12 10.59L6.41 5L5 6.41L10.59 12L5 17.59L6.41 19L12 13.41L17.59 19L19 17.59L13.41 12L19 6.41z"
                        />
                  </svg>
            </figure>
            <ul class="nav__list" :class="isMobileNavOpen ? 'open' : ''">
                  <li class="nav__item">
                        <router-link class="nav__link" to="#">about me</router-link>
                  </li>
                  <li class="nav__item">
                        <router-link class="nav__link" to="#">projects</router-link>
                  </li>
                  <li class="nav__item">
                        <router-link class="nav__link" to="#">contact</router-link>
                  </li>
                  <li class="nav__item">
                        <router-link class="nav__link" to="#">resume</router-link>
                  </li>
                  <li class="nav__item">
                        <router-link class="nav__media" to="#">
                              <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="28"
                                    height="28"
                                    viewBox="0 0 24 24"
                              >
                                    <path
                                          fill="var(--base-font)"
                                          d="M18.336 18.339h-2.665v-4.177c0-.996-.02-2.278-1.39-2.278c-1.389 0-1.601 1.084-1.601 2.205v4.25h-2.666V9.75h2.56v1.17h.035c.358-.674 1.228-1.387 2.528-1.387c2.7 0 3.2 1.778 3.2 4.091v4.715ZM7.004 8.575a1.546 1.546 0 0 1-1.548-1.549a1.548 1.548 0 1 1 1.547 1.549Zm1.336 9.764H5.667V9.75H8.34v8.589ZM19.67 3H4.33C3.594 3 3 3.58 3 4.297v15.406C3 20.42 3.594 21 4.328 21h15.339C20.4 21 21 20.42 21 19.703V4.297C21 3.581 20.4 3 19.666 3h.003Z"
                                    />
                              </svg>
                        </router-link>
                        <router-link class="nav__media" to="#">
                              <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="28"
                                    height="28"
                                    viewBox="0 0 24 24"
                              >
                                    <path
                                          fill="var(--base-font)"
                                          d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33c.85 0 1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2Z"
                                    />
                              </svg>
                        </router-link>
                  </li>
            </ul>
      </nav>
</template>

<style scoped>
.nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      padding: var(--padding-sm);
}

.nav__burger {
      cursor: pointer;
      opacity: 0.6;
      transition: opacity var(--transition-20) ease;
      display: flex;
}

.nav__burger:hover {
      opacity: 1;
}

.nav__burger:hover .open-nav path {
      stroke: var(--color-primary-light);
}
.nav__burger:hover .close-nav path {
      fill: var(--color-primary-light);
}

.nav__logo {
      width: 64px;
      aspect-ratio: 1;
      object-fit: cover;
}

.nav__list {
      width: 100%;
      max-height: 0;
      overflow: hidden;
      transition: all var(--transition-40) ease;
      padding-inline: var(--padding-md);
}

.open {
      max-height: 100vh;
      padding-block: var(--padding-md) 0;
}

.nav__item {
      display: grid;
      transition: box-shadow var(--transition-20);
}

.nav__link {
      text-transform: uppercase;
      font-weight: 600;
      font-size: 2rem;
      opacity: var(--opacity-60);
      transition: all var(--transition-20);
      padding: var(--padding-md) var(--padding-lg);
}

.nav__link:hover {
      opacity: var(--opacity-100);
      color: var(--color-primary-light);
      scale: 1.02;
      box-shadow: 2px 2px 0 3px var(--shadow-black);
}

.nav__list .nav__item:last-of-type {
      display: grid;
      grid-auto-flow: column;
      justify-content: center;
      gap: var(--gap-lg);

      margin-top: calc(var(--margin-md) * 2);
}

.nav__media > svg path {
      transition: all var(--transition-40);
      opacity: var(--opacity-60);
}

.nav__media:first-child:hover path,
.nav__media:last-child:hover path {
      fill: var(--color-primary-light);
      opacity: 1;
}
</style>
