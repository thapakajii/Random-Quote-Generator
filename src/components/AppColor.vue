<template>
<div class="container">
    <div class="row">
        <div class="col-5 color" :style="'background:' + myColor">
            <div class=" container quote-content" v-if="isClicked">
                "{{ quote.content }}"
            </div>
            <button class="box-button" @click="display">Click Me</button>
        </div>
        <div class="col-1"></div>
        <div class="col-5 color" :style="'background:' + myColor1">
            <div class=" container quote-content" v-if="isClicked1">
                "{{ quote1.content1 }}"
            </div>
            <button class="box-button" @click="display1">Click Me</button>
        </div>
    </div>
    <div class="row">
        <div class="col-5 color" :style="'background:' + myColor2">
            <div class=" container quote-content" v-if="isClicked2">
                "{{ quote2.content2 }}"
            </div>
            <button class="box-button" @click="display2">Click Me</button>
        </div>
        <div class="col-1"></div>
        <div class="col-5 color" :style="'background:' + myColor3">
            <div class=" container quote-content" v-if="isClicked3">
                "{{ quote3.content3 }}"
            </div>
            <button class="box-button" @click="display3">Click Me</button>
        </div>
    </div>
    <div class="row">
        <div class="col-5 color" :style="'background:' + myColor4">
            <div class=" container quote-content" v-if="isClicked4">
                "{{ quote4.content4 }}"
            </div>
            <button class="box-button" @click="display4">Click Me</button>
        </div>
        <div class="col-1"></div>
        <div class="col-5 color" :style="'background:' + myColor5">
            <div class=" container quote-content" v-if="isClicked5">
                "{{ quote5.content5 }}"
            </div>
            <button class="box-button" @click="display5">Click Me</button>
        </div>
    </div>
</div>

</template>

<script>
export default {
    data(){
        return{
            myColor: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            myColor1: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            myColor2: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            myColor3: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            myColor4: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            myColor5: '#' + (Math.random()*0xFFFFFF<<0).toString(16),
            quote: {
            content: ''
            },
            quote1: {
            content1: ''
            },
            quote2: {
            content2: ''
            },
            quote3: {
            content3: ''
            },
            quote4: {
            content4: ''
            },
            quote5: {
            content5: ''
            },
            quotes: [],
            isClicked: false,
            isClicked1: false,
            isClicked2: false,
            isClicked3: false,
            isClicked4: false,
            isClicked5: false
        }
    },
    mounted(){
    },
    methods:{
        async getQuote(){
        const data = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote = {
            content: data.quote
        };
        },
        async getQuote1(){
        const data = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote1 = {
            content1: data.quote
        };
        },
        async getQuote2(){
        const data2 = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote2 = {
            content2: data2.quote
        };
        },
        async getQuote3(){
        const data3 = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote3 = {
            content3: data3.quote
        };
        },
        async getQuote4(){
        const data4 = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote4 = {
            content4: data4.quote
        };
        },
        async getQuote5(){
        const data5 = await fetch('https://animechan.vercel.app/api/random').then(res => res.json());

        this.quote5 = {
            content5: data5.quote
        };
        },
        display(){
            this.isClicked = true
        },
        display1(){
            this.isClicked1 = true
        },
        display2(){
            this.isClicked2 = true
        },
        display3(){
            this.isClicked3 = true
        },
        display4(){
            this.isClicked4 = true
        },
        display5(){
            this.isClicked5 = true
        },
    },
    created(){
    this.getQuote();
    this.getQuote1();
    this.getQuote2();
    this.getQuote3();
    this.getQuote4();
    this.getQuote5();
  }
}
</script>

<style>
.color{
    border-radius: 8px;
    text-align: center;
    margin-bottom: 40px;
    padding: 100px;
    font-size: 2rem;
    border: 1px solid #e5e5e5;
}
.box-button{
    color: #0c9775;
    font-weight: bold;
    border: 1px solid transparent;
    border-radius: 5px;
    opacity: 0.6;
}
.quote-content{
    background-color: #caf0f8;
    opacity: 0.3;
    color: #000;
    margin-bottom: 5px;
}
</style>