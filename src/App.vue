<template>
  <div class="app">
    <h1 v-for="(item, index) in repeat" v-bind:key="item" v-bind:data-index="index">{{ msg }}</h1>
    <span class="wtf"><a href="https://www.reiner.io">wtf?</a></span>
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

html
  background-color: #f78c58
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #1a1a1a

$big: 64px
$smol: 24px

.app
  margin: $big
  transition: margin .2s ease-out

  @media only screen and (max-width: 600px)
    margin: $smol

.wtf
  position: fixed
  right: 0
  top: 0
  margin: $big

  a
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
  line-height: responsive ($smol * .88) ($big * .88)

  text-transform: uppercase
  font-weight: bold
  letter-spacing: responsive ($smol / 4) ($big / 4)
  white-space: nowrap

</style>
