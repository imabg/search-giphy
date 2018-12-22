<template>
    <div class="container">
    <input type="text" placeholder="Enter keyword..." v-model="search_giphy" id="search" value="merry chrismas"><br>
    <button class="btn btn-primary" @click="getGiphy">Search</button> <br><br>
    <giphy :giphy_url="giphy_url" :giphy_send = "giphy_send"/>
    </div>
</template>

<script>
import axios from 'axios';
import giphy from '../components/giphy.vue';

const api_key = 'MMDwk0fpcAzUKZ0MThhXCSNDx97sBL7c';

export default {
    name: 'search-bar',
    components: {
        giphy
    },
    data() {
        return {
            search_giphy: 'merry chrismas',
            giphy_url: '',
            giphy_send: false
        }
    },
    created () {
            axios.get(`https://api.giphy.com/v1/gifs/search?q=${this.search_giphy}&api_key=${api_key}`)
            .then(res => {
                let rndm = Math.floor(Math.random() * 25);
                this.giphy_send = true;
                this.giphy_url = res.data.data[rndm].images.original.url;
            })
            .catch(err => console.log(err)
            );
        },
        methods: {
            getGiphy() {
                axios.get(`https://api.giphy.com/v1/gifs/search?q=${this.search_giphy}&api_key=${api_key}`)
                .then(res => {
                let rndm = Math.floor(Math.random() * 25);
                this.giphy_send = true;
                this.giphy_url = res.data.data[rndm].images.original.url;
            })
            .catch(err => console.log(err)
            );
            }
        }
}
</script>

<style scoped>
    input {
        font-size: 25px;
        width: 80%;
    }
    button {
        margin: 0;
        padding: 5px;
        font-size: 25px;
    }
</style>

