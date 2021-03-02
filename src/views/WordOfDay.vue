<template>
    <div class="wordViewWrapper">
        <a-menu v-model="current" mode="horizontal" v-bind:style="{marginBottom: '50px'}" @click="menuItemClicked">
            <a-menu-item key="vocab"> Vocabulary </a-menu-item>
            <a-menu-item key="fin"> Finance </a-menu-item>
        </a-menu>
        <Card class="myCard1" :title="currentLesson.title" :content="currentLesson.content"/>
        <div class="button-wrapper">
            <a-button @click="nextButtonClicked">Next</a-button>
        </div>
        <br/><br/>
    </div>
</template>
<script>
import axios from 'axios'
import Card from '@/components/Card.vue'
// import Button from '@/components/Button.vue'
// import Switch from 'ant-design-vue/lib/switch'

export default {
    name: 'WordOfDay',
    components: {
        Card,
        // Button,
        // Switch
    },
    data () {
      return {
        titleUno: 'Abate',
        contentUno: 'I am the body of uno',
        vocabObj: {title: '', content: ''},
        financeObj: {title: '', content: ''},
        allFinanceObj: {},
        currentLesson: {},
        title: '',
        content: '',
        current: ['vocab'],
        currentHeader: 'vocab'
      }
    },
    methods: {
        getRandomFinanceWord(wordsJson) {
            var keys = Object.keys(wordsJson)
            var gate = true
            while(gate) {
                var randomNum = Math.floor(Math.random() * keys.length);
                var randomWord = wordsJson[keys[randomNum]]
                if (this.currentLesson.title !== randomWord.title) break
            }
            this.currentLesson = {
                title: randomWord.title,
                content: randomWord.definition
            }            
        },
        menuItemClicked (event) {
            if(event.key === 'fin') {
                this.currentLesson = this.financeObj
                this.currentHeader = 'fin'
            }
            else {
                this.currentLesson = this.vocabObj
                this.currentHeader = 'vocab'
            }
        },
        nextButtonClicked () {
            if(this.currentHeader === 'vocab') location.reload()
            else this.getRandomFinanceWord(this.allFinanceObj)
        },
        capitalizeFirstLetter(string) {
           return string.charAt(0).toUpperCase() + string.slice(1);
        }
    },
    mounted () {
        axios
        .get('https://word-of-day-backend.herokuapp.com/wordofday')
        .then(response => {
            this.vocabObj = {
                title: this.capitalizeFirstLetter(response.data.data.name),
                content: response.data.data.description
            }
            this.currentLesson = {
                title: this.capitalizeFirstLetter(response.data.data.name),
                content: response.data.data.description
            }
        })
        .catch(error => {
            console.log(error)
        })
        .finally(() => this.loading = false)

        axios
        .get('https://word-of-day-backend.herokuapp.com/financeofday')
        .then(response => {
            this.allFinanceObj = JSON.parse(JSON.stringify(response.data.cardData))
            // let temp = this.getRandomFinanceWord(response.data.cardData)
            this.financeObj = {
                title: response.data.cardData.Card1.title,
                content: response.data.cardData.Card1.definition
            }
        })
        .catch(error => {
            console.log(error)
        })
        .finally(() => this.loading = false)
    }
}
</script>
<style scoped>
.myCard1{
    height: 350px;
    margin: 0 20px 20px 20px;
}
.button-wrapper{
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr;
    justify-items: center;
    margin-right: 20px;
    margin-left: 20px;
}
.wordDecision{
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 1fr 1fr;
}
.lessonTitle {
    margin-left: 20px;
    margin-right: 20px;
    text-align: left;
    font-size: 20px;
    font-weight: 700;
}
</style>