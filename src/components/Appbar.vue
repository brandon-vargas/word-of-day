<template>
    <div class="outterBarWrapper">
        <img src="../assets/astronaut.png" v-bind:style="{justifySelf: 'left', paddingLeft: '20px'}"/>
        <div class="innerBarWrapper">
            <div v-bind:style="{alignSelf: 'center', color: '#2c90c6'}">
                Home
            </div>
            <div v-bind:style="{alignSelf: 'center'}">
                Work
            </div>
            <div v-bind:style="{alignSelf: 'center'}">
                About
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Appbar',
    data() {
        return {
            collapsed: true,
        };
    },
    methods: {
        toggleCollapsed() {
          this.collapsed = !this.collapsed;
        },
    },
}
</script>
<style scoped>
.outterBarWrapper {
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 1fr;
    justify-items: right;
    padding: 5px;
    margin-top: 20px;
}
.innerBarWrapper {
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 1fr 1fr;
    justify-content: right;
    width: 90%;
}
</style>