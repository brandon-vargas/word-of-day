<template>
    <div id="work-container">
        <router-link class="routerLink" to='/WordOfDay'>
            <Card class="myCardTitle" :title="'Word of the Day'" :content="''" :topLine="true"></Card>
        </router-link>
    </div>
</template>
<script>
import Card from '@/components/Card.vue'

export default {
    name: 'Work',
    components: {
        Card
    },
    methods: {
        clickMe () {
            console.log('asdfasdfasfasdfs')
        }
    }
}
</script>
<style>
#work-container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
    margin-top: 20px;
    justify-items: center;
}
.myCardTitle {
    width: 150px;

}
</style>