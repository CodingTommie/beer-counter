<template>
<h1>Hoeveel rookt Mars? </h1>

<div id="counterApp">
  <div class="sentenceBeforeStart"></div>
  <div class="sentenceAfterStart">
    <h2> {{firstName}} heeft {{count}} {{peukie}} gerookt</h2>
    </div>
  <div class="messageDiv">
    <h3>{{message}}</h3>
  </div>
  <div id="buttons">
      <button class="btnLeft" v-on:click="incrementCounter">Peukie erbij</button>
      <button class="btnRight" v-on:click="resetCounter">Gestopt met roken</button>
  </div>
</div>

</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      count: 0,
      firstName: 'Mars',
      message: 'Je gaat toch niet klikken he? ',
      peukie: 'peukies'
    }
  },
  methods: {
    incrementCounter: function () {
      this.count += 1
      if (this.count <= 10) {
        this.message = 'Ben je weer begonnen?'
        if (this.count === 1) {
          this.peukie = 'peukie'
        } else {
          this.peukie = 'peukies'
        }
      } else if (this.count <= 20) {
        this.message = 'Weet je het zeker?'
      } else if (this.count <= 30) {
        this.message = 'Dit gaat niet goed..'
      } else if (this.count <= 40) {
        this.message = 'Je zit al op 30 gulden..'
      } else {
        this.message = 'Dit wordt niks meer lul'
      }
    },
    resetCounter: function () {
      this.count = 0
      this.firstName = 'Mars'
      this.message = 'En weer gestopt. Erg mooi. '
      this.peukie = 'peukies'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#buttons {
  margin: 0px;
  padding: 0px;
}

.btnLeft {
  margin-right: 5px;
}

.btnRight {
  margin-left: 5px;
}
</style>
