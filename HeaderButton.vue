<script>
export default {
  props: ['icon', 'title', 'limit'],
};
</script>

<template>
  <div class="header-bar__button" @click="$emit('click')">
    <span class="header-bar__title" :class="{ limit }" v-if="title">
      {{title}}
    </span>
    <i class="material-icons" v-if="icon">
      {{icon}}
    </i>
  </div>
</template>

<style lang="less">
.header-bar {  
  &__button {
    font-size: 0;
    display: flex;
    align-items: center;
    padding: 0px 5px;
    overflow: hidden;
    white-space: nowrap;
    border-radius: 3px;
    cursor: pointer;
    text-decoration: none;
    position: relative;

    &.caption {
      padding-left: 0px;
    }

    a {
      color: #ffffff;
      &:hover {
        text-decoration: none;
      }
    }
  }

  &__title {
    font-size: 16px;
    padding-top: 2px;
    margin: 0px 5px;
    position: relative; 
    overflow: hidden;
    white-space: nowrap; 

    &.limit {
      max-width: 150px;
    }
  } 
}
</style>
