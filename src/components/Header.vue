<template>
  <div>
    <div id="nav">
      <div class="nav__top">
        <div class="nav__logo">
          <router-link to="/"><img alt="Juniper logo" src="@/assets/img/logo.png"></router-link>
        </div>
        <LanguageSwitcher></LanguageSwitcher>
      </div>
      <ul class="nav__menu">
        <router-link to="/" tag="li">{{ $t('home') }}</router-link>
        <router-link to="/about" tag="li">{{ $t('about') }}</router-link>
        <li>{{ $t('services') }}
          <ul class="dropdown"> 
            <router-link to="/activities" tag="li">{{ $t('activities') }}</router-link>
            <router-link to="/tickets" tag="li">{{ $t('tickets') }}</router-link>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import LanguageSwitcher from '@/components/LanguageSwitcher.vue';

export default {
  name: 'Header',
  components: {
    LanguageSwitcher
  }
};
</script>

<style lang="scss" scoped>
#nav {
  box-sizing: border-box;
  position: relative;
  padding: 15px 40px;
  width: 100%;
  .nav__top {
    width: 100%;
    display: inline-flex;
    justify-content: space-between;
    align-items: center;
    .nav__logo {
      height: 50px;
      width: auto;
    }
  }
  li {
    font-weight: 400;
    color: #2c3e50;
    text-decoration: none;
    cursor: pointer;
    &.router-link-exact-active {
      font-weight: bold;
      text-decoration: underline;
    }
    &:first-child {
      margin-right: 5px;
    }
    &:not(:first-child) {
      margin-left: 5px;
    }
  }
  .nav__menu {
    margin: 0px;
    padding: 0px;
    margin-top: 10px;
    list-style: none;
    display: inline-flex;
    ul.dropdown {
      margin: 0px;
      padding: 0px;
      cursor: pointer;
      list-style: none;
      visibility: hidden;
      opacity: 0;
      position: absolute;
      transition: all 1.5s ease;
      padding-top: 0.3rem;
      left: auto;
      display: none;
      background-color: white;
      li {
        display: block;
        transition-duration: 1.5s;
        margin: 0px;
        padding: 5px 0px;
        cursor: pointer;
        clear: both;
        width: 100%;
      }
    }
    > li {
      margin: 0px;
      &:not(:first-child) {
        margin-left: 10px;
      }
      &:hover > ul, & ul.dropdown:hover {
        visibility: visible;
        opacity: 1;
        display: block;
      }
    }
  }
}
</style>
