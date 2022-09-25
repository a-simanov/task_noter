<template>
    <input type="text" id="inputValue" v-model='inputValue'>
    <div class="error" v-if="!this.inputValue">Введите задачу</div>
    <button @click="inputText">Добавить задачу</button>
</template>

<script>
export default {
    data () {
        return {
            inputValue: ''
        }        
    },
    emits: ['addNote'],
    methods: {
        inputText () {
            this.$emit('addNote', this.inputValue)
            this.inputValue = ''
        }
    }
}
</script>