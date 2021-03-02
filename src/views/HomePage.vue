<template>
    <div class="homePage">
        <Appbar/>
        <div >
            <h1 class="name">I'm Brandon</h1>
            <p>A programmer for funsies</p>
            <!-- <img src="../assets/editone.png"/> -->
        </div>
        <!-- <Card :title="'i am a title'" :content="'i am some description that explains i really dont knowi am some description that explains i really dont knowi am some description that explains i really dont knowi am some description that explains i really dont knowi am some description that explains i really dont knowi am some description that explains i really dont knowi am some description that explains '"></Card> -->

    </div>
</template>
<script>
import Appbar from '@/components/Appbar.vue'
// import Card from '@/components/Card.vue'
export default {
    name: 'HomePage',
    components: {
        Appbar,
        // Card
    }
}
</script>
<style scoped>
.name {
    font-family: 'Cormorant Infant', serif;
    margin: 50px 20px 20px 20px;
}
.homePage {
    min-height: 50vh;
    background: #fff9ef;
}
</style>