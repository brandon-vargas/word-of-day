<template>
    <div>
        <v-app-bar
            dense
            light
            color="rgba(0,0,0)"
            flat
            class="app-bar"
            v-bind:style="{background: '#fff9ef'}">

        <img src="../assets/astronaut.png" v-bind:style="{justifySelf: 'left', width: '30px'}"/>
        <v-spacer></v-spacer>
        <router-link class="routerLink" to='/'>
            <v-btn class="buttonMaster" text small>Home</v-btn>
        </router-link>
        <router-link class="routerLink" to='/work'>
            <v-btn class="buttonMaster" text small>Work</v-btn>
        </router-link>
        <router-link class="routerLink" to='/about'>
            <v-btn class="buttonMaster" text small>About</v-btn>
        </router-link>
        </v-app-bar>
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
    padding-top: 20px;
}
.innerBarWrapper {
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 1fr 1fr;
    justify-content: right;
    width: 90%;
}
/* .v-btn {
    padding: 0 4px;
    font-family: Avenir,Helvetica,Arial,sans-serif;
    font-size: 14px;
} */
.buttonMaster {
    text-transform: none !important;
    padding: 0 4px !important;
    font-family: Avenir,Helvetica,Arial,sans-serif !important;
    font-size: 14px !important;
    font-weight: 400;
}
</style>

    <!-- <div class="outterBarWrapper">
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
    </div> -->