<script>
    import { defineComponent } from 'vue';

    export default defineComponent ({
        data() {
        return {
            amount: 0,
            weeks:0,
            people: 1,
            eachPerson: 0,
            totalOfEach: 0.00,
            total: 0.00,
            week: true,
            month: true,
            year: true,
        }
    },

    methods: {
        // single() {
        //     // this.total = this.amount * this.people
        // }, 
        
        getWeeks(event) {
            // this.single();
            if (event.target.textContent === '5 Weeks') {
                this.weeks = 5
            } else if (event.target.textContent === '10 Weeks') {
                this.weeks = 10
            } else if (event.target.textContent === '15 Weeks') {
                this.weeks = 15
            } else if (event.target.textContent === '20 Weeks') {
                this.weeks = 20
            }
            else if (event.target.textContent === '25 Weeks') {
                this.weeks = 25
            }
            else if (event.target.textContent === '30 Weeks') {
                this.weeks = 30
            }
            else if (event.target.textContent === '40 Weeks') {
                this.weeks = 40
            } else if (event.target.textContent === '50 Weeks') {
                this.weeks = 50
            }

            this.totalOfEach = this.amount * this.weeks
            this.total = this.amount * this.people * this.weeks
            console.log(event.target.textContent)
                
        },

        reset() {
                this.amount= 0,
                this.weeks=0,
                this.people= 1,
                this.eachPerson= 0,
                this.totalOfEach= 0.00,
                this.total= 0.00
        }
    }
    })

</script>

<template>
    <main class="space-y-4 bg-green-400 rounded-[20px] px-[1.2em] py-[1.5em] border-4 border-green-700">

<div class="space-y-2">
    <p class="text-green-900 text-[1.2em]">Amount Contributed</p>

    <div class="amount bg-green-200 text-green-900 px-[0.8em] py-[0.8em] flex justify-between rounded-[10px]  font-bold text-[1.2em]">
        <p>#</p>
        <input class="outline-none bg-green-200 text-right" type="text" placeholder="0" v-model.number="amount">
    </div>
</div>


<div class="week-month-year grid grid-cols-2 md:grid-cols-3">
    <p @click="week = !week" class="text-green-900 text-[1.2em]">Number of Weeks</p>
    <p @click="month = !month" class="text-green-900 text-[1.2em]">Number of Months</p>
    <p @click="month = !month" class="text-green-900 text-[1.2em]">Number of Years</p>
</div>
<!-- <div class="space-y-2"> -->
    <div v-if="week" class="weeks grid grid-cols-3 gap-[0.5em]">
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">5 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">10 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">15 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">20 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">25 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">30 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">40 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">50 Weeks</p>
        <input class="bg-green-300 text-green-700 text-center font-bold text-[1.2em] rounded-[10px] cursor-pointer outline-none" type="text" placeholder="Custom" v-model="weeks" @keyup.enter="getWeeks">
    </div>
<!-- </div> -->


<!-- <div class="space-y-2"> -->
    <div v-if="!month" class="weeks grid grid-cols-3 gap-[0.5em]">
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">5 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">10 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">15 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">20 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">25 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">30 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">40 Weeks</p>
        <p class="bg-green-700 text-green-300 font-bold text-[1.2em] py-[0.5em] rounded-[10px] flex items-center justify-center cursor-pointer" @click="getWeeks($event)">50 Weeks</p>
        <input class="bg-green-300 text-green-700 text-center font-bold text-[1.2em] rounded-[10px] cursor-pointer outline-none" type="text" placeholder="Custom" v-model="weeks" @keyup.enter="getWeeks">
    </div>
<!-- </div> -->

<div class="space-y-2">
    <p class="text-green-900 text-[1.2em]">Number of People</p>

    <div class="people  bg-green-200 text-green-900 px-[0.8em] py-[0.8em] flex justify-between rounded-[10px]  font-bold text-[1.2em]">
        <!-- <p>#</p> -->
        <img class="w-[1.5em]" src="../assets/prof chef.png" alt="">
        <input class="outline-none bg-green-200 text-right" type="text" placeholder="0" v-model.number="people">
    </div>
</div>


<div class="result space-y-6 bg-green-900 px-[0.8em] py-[0.8em] text-green-200 font-bold text-[1.2em] rounded-[10px]">
    <div class="each flex justify-between">
        <p>Each Person</p>
        <p>{{totalOfEach}}</p>
    </div>

    <div class="each  flex justify-between">
        <p>Total</p>
        <p>{{total}}</p>
    </div>

    <button class="bg-green-200 text-green-900 w-[100%] rounded-[10px] py-[0.8em]" @click="reset">RESET</button>
</div>
</main>
</template>