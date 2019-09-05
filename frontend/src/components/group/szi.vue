<template>
    <div>
        <img :src="ziimgurl">
        <br>
        <p>{{zititle}}</p>
    </div>
</template>
<script>
export default {
    components:{

    },
    props:["zititle","ziimgurl"]
}
</script>
<style scoped>
    div{
        font-size:0px;
        margin-right: 0.05rem;
    }
    img{
        width:1rem;
        height:1.2rem;
    }
    p{
        font-size:0.14rem;
        width: 1rem;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        text-align: center;
        color: #111;
    }
</style>