<template>
    <div class="b-button"  v-on:click="refreshClicked()" >
        <slot/>
    </div>
</template>
<script>
export default {
    name: 'Button',
    methods: {
        refreshClicked() {
            location.reload()
        }
    },
}
</script>
<style scoped>
.b-button{
    border-radius: 4px;
    border: 1px solid #d9d9d9;
    height: 35px;
    display: grid;
    align-items: center;
    padding: 4px 15px 4px 15px;
}
</style>