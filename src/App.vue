<template>
  <div class="app">
    <h1 v-for="(item, index) in repeat" v-bind:key="item" v-bind:data-index="index">{{ msg }}</h1>
    <a href="https://www.reiner.io" class="wtf"><span>wtf?</span></a>
  </div>
</template>

<script>
  import VueLoop from 'vue-loop'

  export default {
    name: 'app',
    components: {
      'vue-loop': VueLoop
    },
    data () {
      return {
        msg: 'mirshko means courage',
        repeat: 100
      }
    }
  }
</script>

<style lang="sass">
// Reset a bitch
@import "~minireset.css/minireset.sass"

// Style a bitch
$pablo: #f78c58

html
  background-color: $pablo
  font-family: Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #1a1a1a

$big: 64px
$smol: 32px

.app
  margin: $big
  transition: margin .2s ease-out

  @media only screen and (max-width: 600px)
    margin: $smol

.wtf
  position: fixed
  display: block
  right: 0
  top: 0
  padding: $big

  span
    font-size: responsive 48px 72px
    font-weight: bold
    display: block

    @keyframes rotate
      from
        transform: rotate(0deg)
      to
        transform: rotate(360deg)

    animation-name: rotate
    animation-duration: 2400ms
    animation-iteration-count: infinite
    animation-timing-function: linear

h1
  transition: font-size .2s ease-out, line-height .2s ease-out
  font-size: responsive $smol $big
  line-height: responsive ($smol * .96) ($big * .96)
  text-transform: uppercase
  font-weight: 900
  letter-spacing: responsive ($smol / 8) ($big / 8)
  white-space: nowrap

</style>
