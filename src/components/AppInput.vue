<template>
    <textarea class="textarea" type="text" id="inputValue" v-model='inputValue' placeholder="Введите заметку"></textarea>
    <button class="btn" @click="inputText" :disabled="!this.inputValue">Добавить задачу</button>
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