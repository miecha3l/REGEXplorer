<template>
    <div>
        <textarea v-model="input" v-on:keyup="process" placeholder="Your text"></textarea> 
        <input v-model="regex" v-on:keyup="process" placeholder="RegExp">
    </div>
</template>

<script>
export default {
    name: 'RegexInput',
    props: [
        'update',
        'eval'
    ],
    data() {
        return {
            input: '',
            regex: '',
        }
    },
    methods: {
        'process': function() {
            this.update(this.input, this.regex);
            this.eval();
        }
    }
}
</script>

<style scoped>
    div{
        width: 40%;
        height: 400px;
        margin-right: 5px;
        display: inline-block;
    }

    textarea{
        padding: 0;
        margin: 0;
        background-color: #232323;
        outline: none;
        resize: none;
        color: #fefefe;
        width: 100%;
        height: 100%;
        border: 2px solid #111;
    }

    textarea:focus{
        border: 2px solid #d1b70a;
    }

    input {
        width: 95%;
        outline: none;
        border: 2px solid #111;
        background-color: #232323;
        color: #fefefe;
        padding-top: 20px;
        padding-bottom: 20px;
        padding-left: 20px;
    }

    input:focus{
        border: 2px solid #d1b70a;
    }
</style>