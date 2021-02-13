<template>
    <div>
        <div class="row bg-danger" v-for="(cidade, key) in cidades" :key="key">
            <div class="col-12 bg-info">
                <p>{{ cidade.name }}</p>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {

    mounted() {
        axios.get('localhost:3000/cidades').then((response) => {
            console.log(response)
        })
    },

    data: () => {
        return {
            cidades: [
                {name: "teste"},
                {name: "teste"},
                {name: "teste"},
                {name: "teste"},
                {name: "teste"},
            ]
        }
    }
}
</script>

<style scoped>


</style>