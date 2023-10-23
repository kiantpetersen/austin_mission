<template>
    <p>Reaction time: {{ score }}ms</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props:['score'],
data(){
    return{
        rank:null
    }
},mounted(){
    if (this.score<250){
        this.rank='Ninja fingers'
    }else if ( this.score<300){
        this.rank='Rapid Reflexes'
        
    }else{
        this.rank='Snail Pace...'
    }
}
}
</script>

<style>
.rank{
    color:#fff;
    width:200px;
    height:50px;
    display:flex;
    align-items:center;
    justify-content: center;
    border-radius:10px;
    background: #344eff;

}

</style>