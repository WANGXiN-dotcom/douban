<template>
    <div>
        <div v-for="(v,i) in arr" :key="i">
            <ul class="mui-table-view">
                <li class="mui-table-view-cell mui-media">
                    <a href="javascript:;">
                        <img class="mui-media-object mui-pull-left" :src="v.images.small">
                        <div class="mui-media-body">
                            <span>{{v.title}}</span>
                            <span>20005人</span>
                        </div>
                        <p>
                            <span>{{v.group_topic.time}}</span>
                            <span>{{v.group_topic.title}}</span>
                        </p>
                    </a>
                    
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            arr:[]
        }
    },
    created() {
        this.axios({
            method:"get",
            url:"/group1"
        }).then((data)=>{
            console.log(data.data);
            this.arr=data.data;
        })
    },
}
</script>
<style scoped>
.mui-media-body{
    font-size: 0.2rem;
    line-height: 0.4rem;
}
.mui-table-view .mui-pull-left{
    margin-right: 0.15rem;
}
.mui-media p{
    margin-top: 0.1rem;
    font-size: 0.16rem;
}
.mui-media-body span:nth-child(1){
    width: 1.9rem;
    margin-right: 0.2rem;
}
.mui-media-body span:nth-child(2){
    color: #ccc;
}
.mui-media-body span{
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
.mui-media p span:nth-child(2){
    width: 2.4rem;
}
.mui-media p span{
    display: inline-block;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    color:#aaa;
}
</style>