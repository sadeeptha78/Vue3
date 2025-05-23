<template>
    <div class="container my-5">
        <h1 class="text-center"> Card With Header </h1>
        <div class="row row-cols-1 row-cols-md-3 g-4">
            <div class="col">
                <div class="card h-100">
                    <div class="card-header">
                        This is card header
                    </div>
                    <div class="card-body">
                        <p class="card-text"> this is card text</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="container my-5">
        <h2 class="text-center mb-4">Our Services</h2>

        <div class="row row-cols-1 row-cols-md-3 g-4">
            <div class="col">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">Development</h5>
                        <p class="card-text">Test Page </p>
                        <button class="btn btn-primary" @click="openModal()"> Learn More</button>
                    </div>
                </div>
            </div>

            <div class="col">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">App Development</h5>
                        <p class="card-text">Good work</p>
                        <a href="#" class="btn btn-primary">Discover More</a>
                    </div>
                </div>
            </div>
        </div>

        <div class="row row-cols-1 mt-5" v-if="modalShow" >
            <div class="d-flex justify-content-end">
                <child @SendRespondBack="GetRespondFromChild" :info="infoToChild"/>
            </div>
        </div>
    </div>

    <!--Pass value to child and get the return data back form child-->
</template>

<script setup>
import {ref} from 'vue'
import Child from "@/Pages/TestEnv/child.vue";

let test = ref("True value")
let modalShow = ref(false)

let openModal = () => {
    modalShow.value = true
}

let infoToChild = "data from parent"

function GetRespondFromChild(val){
    console.log(val)
    modalShow.value =false
}

</script>

<style scoped>

</style>
