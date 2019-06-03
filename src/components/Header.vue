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
        <li>
          <ul class="dropdown"> {{ $t('services') }}
            <router-link to="#" tag="li">{{ $t('services') }}</router-link>
            <router-link to="#" tag="li">{{ $t('services') }}</router-link>
            <router-link to="#" tag="li">{{ $t('services') }}</router-link>
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
      li {
        display: block;
        transition-duration: 0.5s;
        cursor: pointer;
        ul {
          visibility: hidden;
          opacity: 0;
          position: absolute;
          transition: all 0.5s ease;
          margin-top: 1rem;
          left: 0;
          display: none;
          li {
            clear: both;
            width: 100%;
          }
        }
      }
      &:hover > ul, & ul:hover {
        visibility: visible;
        opacity: 1;
        display: block;
      }
      &:not(:first-child) {
        margin-left: 10px;
      }
    }
    li {
      margin: 0px;
      &:not(:first-child) {
        margin-left: 10px;
      }
    }
  }
}
</style>
