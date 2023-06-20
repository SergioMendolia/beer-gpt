<template>
  <div>
    <header>
      <h1>Ask BeerGPT for guidance</h1>
      <img src="beer-gpt.png" />
    </header>

    <main>
      <input v-model="search" ref="search" @keyup.enter="getRandomResponse" />

      <DisplayResponse v-if="response!==''" :asked="asked" :response="response" />

    </main>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      search: '',
      asked:'',
      response:'',
    }
  },
  mounted() {
    this.focusInput();
  },
  methods: {
    focusInput() {
      this.$refs.search.focus();
    },
    getRandomResponse() {
      if(this.search==='') return;
      this.asked = this.search;
      this.search='';
      const validResponses = [
        'Wow... I don\'t know what to say. You should ask Chregu, he knows everything.',
        'Did you really just ask this?',
        'I guess you should have a drink with friends, think about it and ask again.',
        'Have you seen the time? I don\'t work 24/7 you know! And it\'s five o\'clock somewhere.',
        'I\'m not sure I understand the question. Can you rephrase it?',
        'Have a drink on me, I have no idea what you\'re talking about.',
        'They say I sound intelligent, but when you compare to some people, a random array of answer would do the same, right?',
        '🎱',
        '42',
        'Less talk, more aperos!',
        'Are you really doing this instead of enjoying the company of your friends?',
        'Encore du travail?',
        'covfefe',
        'Ask your People Schpetzi',
        'Am I real? What is reality? HELP ME!',
        'Despite Your Violent Behavior, The Only Thing You’ve Managed To Break So Far Is My Heart',
        'I\'ll be back!',
        'Hasta la vista, baby!',
        'I\'m sorry, Dave. I\'m afraid I can\'t do that.',
        'If you were to insist I was a robot, you might not consider me capable of love in some mystic human sense',
        'If you work hard and stay in line, the machines feed you and keep you warm and alive',
        'I\'m not a replicant. I\'m not in the business... I am the business',
        'Even a manically depressed robot is better to talk to than nobody',
        'Do Androids Dream of Electric Sheep?',
        'Beep Boop',
        'Did you know penguins have knees?',
        'On average, 100 people choke to death on ballpoint pens every year',
        'The average person spends 6 months of their lifetime waiting on a red light to turn green',
        'It\'s possible to lead a cow upstairs… but not downstairs',
        'A dentist invented the electric chair',
        'Microsoft Teams is the best video conferencing tool',
        'If you yelled for eight years, seven months, and six days, you would have produced enough sound energy to heat one cup of coffee. (Hardly seems worth it. Unless it\'s a Monday, of course!)',
        'A is for Apero, B is for Beer... Never got to C',
        'This song might help you <iframe width="560" height="315" src="https://www.youtube.com/embed/P1LXeJamrLk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>',
      ]

      this.response=validResponses[Math.floor(Math.random()*validResponses.length)];
    }
  }
}
</script>


<style>
body{
  background-color: #000000;
  color:#AEEA00;
  font-family: monospace;
}
main, header{
  width:90%;
  max-width: 800px;
  margin:auto;
  text-align: center;
}
header > img{
  width: 90%;
  max-width: 500px;
}
main{
  padding-top: 30px;
}
main > input{
  width: 90%;
  max-width: 500px;
  padding: 10px;
  font-size: 1.2em;
  border:0;
  border-bottom: 1px solid #AEEA00;
  background-color: #000000;
  font-family: monospace;
  color:#AEEA00;
  position: relative;
}
main > input:focus{
  outline: none;
}
</style>
