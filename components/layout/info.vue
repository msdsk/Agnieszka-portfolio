<template>
  <header class="header">
    <div class="header__name">
      <div>
        <h1>{{ contact.name }}</h1>
      </div>
      <div>{{ contact.title }}</div>
    </div>
    <div class="header__email">{{ contact.email }}</div>
    <div class="header__phone">{{ contact.phone }}</div>
  </header>
</template>

<script lang="ts" setup>
const { data: contact } = reactive(await useAsyncData("contact", () =>
  queryContent("/main/contact").findOne())
)
</script>


<style lang="scss">
.header {
  @include grid;
  padding: 1rem 0;
  font-size: .8rem;

  @media screen and (max-width: $breakpoint-md) {
    display: block;
  }
}

.header__phone {
  grid-row: 1;
  grid-column: 1 / span 2;
}

.header__email {
  grid-row: 1;
  grid-column: 3 / span 3;
}

.header__name {
  grid-row: 1;
  grid-column: 6 / span 4;

  h1 {
    font-size: inherit;
  }
}
</style>