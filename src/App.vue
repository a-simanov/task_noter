<template>
  <div class="container">
    <app-input @addNote="addNote"></app-input>
    <div class="notes">
      <div 
      class="note"
      v-for="note, ind in notes"
      :key="ind"
      >
        <div class="text">
          <p>{{getDate}}</p>
          <p>{{note}}</p>
        </div>        
        <button class="btn btn_remove" @click="notes.splice(ind, 1)">
          <img class="img img_remove" src="./assets/delete.png" alt="Удалить">
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import AppInput from './components/AppInput.vue'
export default {
  data () {
    return {
      notes: []
    }
  },
  methods: {
    addNote (text) {
      this.notes.push(text)
    }
  },
  computed: {
    getDate () {
      return new Date().toLocaleDateString()
    }
  },
  components: {
    AppInput
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
</style>
