<script>
export default {
  props: ['fixed', 'close', 'glass'],
};
</script>

<template>
  <div class="header-bar" :class="{glass, 'top-fixed': fixed}" >
    <slot></slot>
  </div>
</template>

<style lang="less">
.header-bar {
  width: 100%;
  color: @dark;
  background-color: @white;
  box-shadow: 0 -0px 2px 0 rgba(0, 0, 0, 0.3);

  &.glass {
    color: @dark;
    background-color: rgba(255, 255, 255, 0.2);
  }

  &.top-fixed {
    position: fixed;
    z-index: 1;
    top: 0;
  }

  &__container {
    padding: 0 @indent-xs;
    min-height: @menu-bar-height;
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    white-space: nowrap;
  }

  &__wrapper {
    max-width: @document-width;
    margin: 0 auto;

    &.centred {
      text-align: center;
    }
  }

  &__navbar {
    display: flex;
    align-items: stretch;
    overflow: hidden;
  }

  &__icon {
    flex: 0 auto;
    font-size: 0px;
    position: relative;
  }

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
