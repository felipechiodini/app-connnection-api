<template>
    <div>
        <div class="row bg-danger" v-for="(cidade, key) in cidades" :key="key">
            <div class="col-12 bg-info">
                <label><b>Nome:</b> {{ cidade.name }}</label>
                <label><b>Sigla:</b> {{ cidade.uf }}</label>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {

    mounted() {
        axios.get('http://localhost:3000/cidades')
        .then((response) => {
            this.cidades = response.data
        })
    },

    data: () => {
        return {
            cidades: []
        }
    },

    methods: {


    }
}
</script>

<style scoped>


</style>