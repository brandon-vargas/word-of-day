<template>
    <div>
        <h1>Word of the day</h1>
        <Card class="myCard1" :title="title" :content="content"/>
        <p>{{info}}</p>
    </div>
</template>
<script>
import axios from 'axios'
import Card from '@/components/Card.vue'
export default {
    name: 'WordOfDay',
    components: {
        Card
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
    height: 400px;
    margin: 20px;
}
</style>