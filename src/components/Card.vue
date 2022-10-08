<template>
    <div class="card p-4 my-card" style="width: 22rem;">
        <img :src="starIcon" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">How did we do?</h5>
            <p class="card-text py-3">Please let us know how we did with your support request. All feedback is appreciated to
                help us improve our offering!</p>
            <table class="container gap-3 mt-3">
                <tr class="">
                    <td :class="clicked==1 && 'td-clicked'"><button class="btn rating" @click="clicked=1"  :class="clicked==1 && 'td-rating'" >1</button></td>
                    <td :class="clicked==2 && 'td-clicked'"><button class="btn rating" @click="clicked=2" :class="clicked==2 && 'td-rating'">2</button></td>
                    <td :class="clicked==3 && 'td-clicked'" ><button class="btn rating" @click="clicked=3" :class="clicked==3 && 'td-rating'" >3</button></td>
                    <td :class="clicked==4 && 'td-clicked'" ><button class="btn rating" @click="clicked=4" :class="clicked==4 && 'td-rating'">4</button></td>
                    <td :class="clicked==5 && 'td-clicked'"><button class="btn rating" @click="clicked=5" :class="clicked==5 && 'td-rating'">5</button></td>
                </tr>
            </table>
            clicked:0
            <a href="#" class="btn d-block mt-4 py-3 submit" @click="submitClicked">SUBMIT</a>
        </div>
    </div>
</template>

<script>
import starIcon from '../assets/images/icon-star.svg'
export default {
    name: 'Card',
    data() {
        return {
            starIcon: starIcon,
            clicked:0
        }
    },
    methods:{
        submitClicked(){
            if(this.clicked>0){
            this.$emit('submitted',this.clicked)}
        }
    }
}
</script>

<style  scoped>
.card-img-top {
    padding: .8rem;
    width: 2.5rem;
    background-color: hsl(218, 14%, 22%);
    overflow: hidden;
    border-radius: 50%;
}

.card-body {
    padding: 1rem 0;
}.card-title{
    font-family: 'Overpass', sans-serif;
}td{
    padding: .8rem .8rem;
    border-radius: 50%;
    background-color: hsl(218, 14%, 22%);
    text-align: center;
    color: var(--Medium-Grey);
    font-weight: 700;
}p{
    color: var(--Medium-Grey);
}

.submit{
    color: white;
    background-color: var(--Orange);
    letter-spacing: 3px;
    border-radius: 5rem;
}
a{
    font-size: 15px;
}td:hover{
    color: white;
    background-color: var(--Orange);
}.td-clicked{
    background-color: var(--Light-pGrey);
}
.td-rating{
   color: white;
}
.submit:hover{
    background-color: white;
    color: var(--Orange);
}.rating{
    color: var(--Light-pGrey);
}.rating:hover{
    color: white;
}
</style>