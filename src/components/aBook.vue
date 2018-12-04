<template>
    <div>
        <modalButton v-if="show" @close="show = false" :coverArtDetail="bookFromShelf.detalle"> </modalButton>
        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front"><img :src="bookFromShelf.portada" alt="cover art"></div>
                <div class="flip-card-back">
                    <h3 class="italy"> {{bookFromShelf.titulo}}" </h3>
                    <p> {{bookFromShelf.descripcion}} </p>
                    <button id="show-modal" :value="this.show" @click="this.changeShow"> DETAILS </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import modalButton from '@/components/modalButton.vue'
    export default {
        props: ['bookFromShelf'],
        components: {
            modalButton
        },
    data(){
        return{
            show: false
        }
    },
    methods:{
        changeShow(){
            this.show = !this.show
        }
    }
}
</script>


<style scoped>
.italy{
    font-style: italic;
}
    .nope {
        width: 500px;
    }

    img {
        width: 200px;
        height: 300px;
        background-color: black;
        border-radius: 10px;
        margin: auto;
    }

    .flip-card {
        background-color: transparent;
        width: 220px;
        height: 320px;
        perspective: 1500px;
        margin: 20px auto;
    }

    .flip-card-inner {
        position: relative;
        width: 100%;
        height: 100%;
        text-align: center;


        transition: transform 0.6s;
        transform-style: preserve-3d;
    }

    .flip-card:hover .flip-card-inner {
        transform: rotateY(180deg);
    }

    .flip-card-front,
    .flip-card-back {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
    }

    .flip-card-front {
        background-color: black;
        color: black;
        border-radius: 10px;
        display: flex;
        z-index: 2;
    }

    .flip-card-back {
        background-color: black;
        padding: 0px 10px;
        color: white;
        border-radius: 10px;
        transform: rotateY(180deg);
        z-index: 1;
        font-family: Product Sans;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    button{
        border-radius: 10px;
    }
</style>