<template>
  <div>
   <input type="text" v-model="title">
    <h1>{{ title }}</h1>
    <ul>
        <li v-for="(item, index) in items" v-bind:key="index">{{ item.title }}</li>
    </ul>
    <button v-on:click="greet('Greetings')">Test nupp</button>
    <br>
    <br>
    <label for="">Eesnimi</label>
    <br>
    <input type="text" v-model="users.firstname">
    <br>
    <br>
    <label for="">Perekonnanimi</label>
    <br>
    <input type="text" v-model="users.lastname">
    <h3>{{ fullName }}</h3>
    <input type="text" @keyup="pressKey" @keyup.enter="enterHit">
  </div>
</template>

<script>
export default {
  name: 'Test',
  data () {
    return {
        title: 'Vue on lahe',
        users: {
              firstname: 'Mari',
              lastname: 'Sauna'  
          },
          items: [
              {title: 'Üks'},
              {title: 'Kaks'},
              {title: 'Kolm'}
      ]
    }
  },
    
  methods: {
     greet (greeting) {
         alert (greeting)
     },
      pressKey (event) {
          console.log('Vajutasid ' + event.target.value)
      },
        enterHit () {
            console.log('Vajutasid enterit')
        },
  },
    
    computed: {
        fullName () {
            return this.users.firstname + ' ' + this.users.lastname
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    div {
        margin: 20px;
    }
</style>
