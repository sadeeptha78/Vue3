<template>

    <div class="card-overlay">
        <div class="card position">
            <div class="card-header">
                <button class="btn btn-success btn-sm ms-auto" @click="Confirmed">Confirmed</button>
            </div>
            <div class="card-body">
                <div class="py-3">
                    <h1>{{info}}</h1>
                </div>
            </div>
        </div>
    </div>

</template>

<script setup>
import {defineEmits} from 'vue'
defineProps(['info'])

const emit = defineEmits(['SendRespondBack'])

let Confirmed = () => {
    //Can pass any value
    let data =["a",1,"b",4]
    emit('SendRespondBack',data)
}


</script>

<style scoped>
.card-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1040;
}

.position {
    position: fixed;
    width: 85%;
    top: 20%;
    left: 5%;
    z-index: 1050;
}
</style>
