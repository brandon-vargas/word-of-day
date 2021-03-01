<template>
    <div>
        <h1>Word of the day</h1>
        <Card class="myCard1" :title="title" :content="content"/>
        <div class="button-wrapper">
            <Button >Refresh</Button>
        </div>
        <!-- <Button>New word</Button> -->
    </div>
</template>
<script>
import axios from 'axios'
import Card from '@/components/Card.vue'
import Button from '@/components/Button.vue'

export default {
    name: 'WordOfDay',
    components: {
        Card,
        Button
    },
    data () {
      return {
        titleUno: 'Abate',
        contentUno: 'I am the body of uno',
        info: '',
        title: '',
        content: ''
      }
    },
    mounted () {
        axios
        .get('https://word-of-day-backend.herokuapp.com/wordofday')
        .then(response => {
            console.log(response)
            this.info = response.data.bpi
            this.title = response.data.data.name
            this.content = response.data.data.description
        })
        .catch(error => {
            console.log(error)
            this.errored = true
            this.title = 'Abate'
            this.content = 'I am the body of uno'
        })
        .finally(() => this.loading = false)
    }
}
</script>
<style scoped>
.myCard1{
    height: 300px;
    margin: 20px;
}
.button-wrapper{
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr;
    justify-items: center;
}
</style>