<template>
  <div class="fightclub">
    <img :src="status()" height="300" width="300">
    <h2>The first rule of Fight Club is: You do not talk about Fight Club</h2>
    <h3><span class="textWeight">YOU</span> decide your own level of involvement!</h3>
    <h1>{{target.name}}</h1>
    <h1>{{target.health}}</h1>
    <button @click="slap">Slap</button>
    <button @click="punch">punch</button>
    <button @click="kick">Kick</button>

  </div>
</template>

<script>
  export default {
    name: 'fightclub',
    data() {
      return {

        target: {
          name: "Tyler Durden",
          health: 100
        },
        attacks: {
          slap: 1,
          punch: 5,
          kick: 10
        }
      }
    },
    methods: {

      status() {
        let imageSrc = "../assets/363519925.png"
        if (this.target.health == 0) {
          imageSrc = "../assets/363519925.png"
        } else if (this.target.health <= 45) {
          imageSrc = "../assets/363519925.png"
        } else if (this.target.health <= 75) {
          imageSrc = "../assets/363519925.png"
        }
        return imageSrc

      },

      slap() {
        this.target.health -= this.attacks.slap
        this.checkHealth()
      },
      punch() {
        this.target.health -= this.attacks.punch
        this.checkHealth()
      },
      kick() {
        this.target.health -= this.attacks.kick
        this.checkHealth()
      },
      checkHealth() {
        if (this.target.health < 0) {
          this.target.health = 0
        }
      }

    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .textWeight {
    font-weight: bold;
    text-decoration: underline;
  }

  h1,
  h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

  button {
    height: 3.5rem;
    width: 10rem;
    margin-right: .5rem;
    font-size: 2rem;
    border-radius: 1.5rem;

  }

  button:hover {
    background-color: blue;
    color: white;

  }

  button:focus {
    outline: 0;
  }
</style>