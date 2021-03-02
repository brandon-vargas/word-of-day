<template>
    <div>
        <Appbar/>
        <div class="name">
            <h1>I'm Brandon</h1>
        </div>
    </div>
</template>
<script>
import Appbar from '@/components/Appbar.vue'
export default {
    name: 'HomePage',
    components: {
        Appbar
    }
}
</script>
<style scoped>
.name {
    font-family: 'Cormorant Infant', serif;
    margin: 50px 20px 20px 20px;
}
</style>