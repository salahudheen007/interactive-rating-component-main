<template>
    <div>
        <div class="card p-4 pt-5 my-card " style="width: 22rem;">
            <img :src="thankImage" class="card-img-top" alt="...">
            <div class="card-body text-center">
                <div class="alert" role="alert">
                    You selected {{rating}} out of 5
                </div>
                <h5 class="card-title my-3">Thank you!</h5>
                <p class="card-text my-3">We appreciate you taking the time to give a rating. If you ever need more
                    support, don’t hesitate to get in touch!</p>
            </div>
        </div>
    </div>
</template>

<script>
import thankImage from '../assets/images/illustration-thank-you.svg'
export default {
    name: 'Thank',
    props:['rating'],
    data() {
        return {
            thankImage: thankImage
        }
    }
}
</script>

<style  scoped>
.card-img-top {
    width: 60%;
    margin: auto;
}.alert{
    background-color: hsl(218, 14%, 22%);
    color: var(--Orange);
    width: fit-content;
    margin: auto;
    border-radius: 10rem;
}
</style>