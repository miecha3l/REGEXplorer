<template>
    <div>
        <p v-html="data"></p>
    </div>
</template>

<script>
export default {
    name: 'Output',
    props: [
        'data',
    ],
}
</script>

<style scoped>
    div{
        margin-left: 5px;
        width: 40%;
        height: 438px;
        display: inline-block;
        background: #232323;
        text-align: left;
        padding: 0;
        border: 2px solid #111;
    }

    p{
        padding: 0;
        margin: 0;
        position: absolute;
        color: #fefefe;
    }
</style>