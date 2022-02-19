<template>
    <div class="container">
        <h1 class="titleName">Counter</h1>
        <div class="butonDiv">
            <button @click="increment()" id="incrementNumber">Increment</button>
            <button @click="decrement()" id="decrementNumber">Decrement</button>
            <button @click="reset()" id="resetNumber">Reset</button>
        </div>
        <div ref="textNum" id="numberText">Number:{{counter}}</div>
        <div class="person">
            <button @click="showName('Sasho')" class="personName">Show name</button>
            <h3>Name:{{person}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Content',
    data (){
        return{
            counter: 0,
            person: ' ',
            text:this.$refs.textNum

        }
    },
    methods:{
        increment(){
            this.counter++
            this.$refs['textNum'].style.color ="blue"
        },
        decrement(){
            this.counter--
            this.$refs['textNum'].style.color ="red"
        },
        reset(){
            this.counter = 0
            this.$refs['textNum'].style.color ="grey"
        },
        showName(Name){
          this.person = Name
        }
    },
    mounted(){
        this.increment()
        this.decrement()
        this.reset()
        this.showName()
    }
}
</script>
    
<style scoped>
    .container{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    #incrementNumber,.personName{
        margin-right: 5px;
        width: 100px;
        height: 35px;
        border: 2px solid black;
        border-radius: 5px;
        background: rgb(81, 204, 81);
    }
    #incrementNumber:hover,.personName:hover{
        border: 2px solid rgb(81, 204, 81);
        background: white;
        color: rgb(81, 204, 81);
    }
    #decrementNumber{
        margin-right: 5px;
        width: 100px;
        height: 35px;
        border: 2px solid black;
        border-radius: 5px;
        background: rgb(212, 47, 47);
    }
    #decrementNumber:hover{
        border: 2px solid rgb(212, 47, 47);
        background: white;
        color: rgb(212, 47, 47);
    }
    #resetNumber{
        margin-right: 5px;
        width: 100px;
        height: 35px;
        border: 2px solid black;
        border-radius: 5px;
        background: rgb(172, 165, 165);
    }
    #resetNumber:hover{
        border: 2px solid rgb(172, 165, 165);
        background: white;
        color: rgb(172, 165, 165);
    }
    #numberText, .titleName{
        margin-top: 20px;
        margin-bottom: 20px;
        font-family: Georgia, 'Times New Roman', Times, serif;
        font-size: 20px;
    }
    
</style>