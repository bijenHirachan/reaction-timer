<template>
    <div>
        <h3>Your tier : {{ tier }}</h3>
        <h5>Your speed : {{ points }} ms</h5>
    </div>
</template>

<script>
export default {
    props: ['points'],
    data(){
        return{
            tier: null,
        }
    },
    mounted(){
        if(this.points < 300){
            this.tier = "Ace";
        }else if(this.points < 700){
            this.tier = "Diamond";
        }else if(this.points < 1000){
            this.tier = "Gold";
        }else{
            this.tier = "Bronze";
        }
    }
}
</script>