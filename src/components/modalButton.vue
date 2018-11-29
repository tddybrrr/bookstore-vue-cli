<template>
<div>
        <transition name="modal">
            <div class="modal-mask">
                <div class="modal-wrapper">
                    <div class="modal-container">
                        <div class="modal-body">
                            <slot name="body">
                                <img id="shmeow" :src="coverArtDetail" alt="cover art detail">
                            </slot>
                        </div>

                        <div class="modal-footer">
                            <slot name="footer">
                            <button class="modal-default-button" @click="$emit('close')"> CLOSE </button>
                            </slot>
                        </div>
                    </div>
                </div>
            </div>
        </transition>
  
</div>
</template>

<script>
    export default {
        name: 'modalButton',
        props: ['coverArtDetail'],
        data() {
            return {}
        }
    }
</script>

<style>
#shmeow{
    height: 550px;
}
    .modal-mask {
        position: fixed;
        z-index: 9998;
        top: 10px;
        left: 15%;
        width: 70%;
        height: 70%;
        background-color: rgba(0, 0, 0, .5);
        display: table;
        transition: opacity .3s ease;
    }

    .modal-wrapper {
        display: block;
        vertical-align: middle;
        width: 100%;
        margin: 20px 20px;
        
    }

    .modal-container {
        width: 80%;
        height: 80%;
        margin: 0px auto;
        padding: 20px 30px;
        background-color: #fff;
        border-radius: 2px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
        transition: all .3s ease;
        font-family: Helvetica, Arial, sans-serif;
    }

    .modal-header h3 {
        margin-top: 0;
        color: #42b983;
    }

    .modal-default-button {
        float: right;
    }
    .modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
.modal-body {
  background-color: black;
  display: flex;
  justify-content: center;
}
</style>