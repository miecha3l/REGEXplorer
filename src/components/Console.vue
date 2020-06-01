<template>
    <div>
        <p>{{prefix}} > {{errMsg}}</p>
    </div>
</template>

<script>
export default {
    name: 'Console',
    props: {
        errMsg: String
    },
    data(){
        return {
            prefix: `[${new Date().toLocaleTimeString()}] REGEXplorer`
        }
    }
}
</script>

<style scoped>
    div{
        width: 100%;
        left: 0;
        margin-top: 5%;
        border-top: 1px solid #d1b70a;
    }

    p{
        padding: 10px;
        padding-top: 10px;
        padding-left: 200px;
        text-align: left;
        color: #fefefe;
    }

</style>