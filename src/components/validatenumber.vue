<template>
  <div class="container">
    <div class="topBar">
      <span>
        <span class="time">9:00AM</span>
      <i class="fas fa-location-arrow"></i>
      </span>
      
        
        <span class="largeCircle"></span>
       <span class="circle"></span>
   
      
      <span>
        <i class="fas fa-wifi"></i>
      <span>LTE</span>
      <i class="fas fa-battery-half"></i>
      </span>
      
    </div>
    <div class="input"> 
       <input type="text" v-model="currentNumber" placeholder="Enter number">
       <p  class="valid">{{this.text}}</p>
      

    </div>
 
    
    
    <div class="containerNumber">
       <button @click="add('1')" @keyup.enter="submit('1')">1</button>
    <button @click="add('2')">2</button>
    <button @click="add('3')">3</button>
    <button @click="add('4')">4</button>
    <button @click="add('5')">5</button>
    <button @click="add('6')">6</button>
    <button @click="add('7')">7</button>
    <button @click="add('8')">8</button>
    <button @click="add('9')">9</button>
    <button >*</button>
    <button @click="add('0')">0</button>
    <button>#</button>
    
    <button class="fas fa-phone" @click="validate"></button>
    </div>

    <div class="bottomBar">
      
        <i class="fas fa-id-badge"></i>
       
      

       
          <i class="fas fa-clock"></i>
          <i class="fas fa-keyboard"  id="keyboard"></i>
          <i class="fas fa-star"></i>
            <i class="fas fa-phone"></i>
     
  
    </div>
    <div class="bottomBarText"> 
      <span class="bottomText">Contacts</span>
       <span class="bottomText">Recents</span>
         <span class="bottomText">keyboard</span>
           <span class="bottomText">Favorites</span>
           <span class="bottomText">Voicemail</span>
      
    </div>
    
  </div>
</template>

<script>


export default {


  name: "validatenumber",
  data(){
    return{
      currentNumber:'',
      text:''
    }
  },
  methods:{
    add(number){
      this.currentNumber = this.currentNumber + number;
      
    },
    
    validate(){
      
      parseInt(this.currentNumber);
      console.log(this.currentNumber)
      if(isNaN(this.currentNumber)){
        this.text= "Invalid phone number"
      }
      else if(this.currentNumber.length>10 || this.currentNumber.length<10){
        console.log(this.currentNumber.length)
        console.log('entre en este if')
        this.text= "Invalid phone number"
      }
      else{
        this.text="Valid phone number"
      }
    }
    
  
  }
};
</script>

<style scoped>
.containerNumber{
  display: grid;
  grid-template-columns: 80px 80px 80px ;
  justify-content: center;
  
}
.container{
  
  background: black;
  width:300px;
  border-radius: 10px;
  border: 4px solid gray;
  
}
.input{
  padding: 20px;
}
input[type="text"] {
    width: 220px;
    height: 40px;
    background: black;
    border-color: gray;
    color: white;
    text-align: center;
}
button {
    border-radius: 70px;
    height: 50px;
    width: 50px;
    padding: 5px;
    padding: 10px;
    margin: 5px 13px;
    background: #6a6a6a;
    border: none;
    color: white;
    font-size: 20px;
}

button:hover{
  background: rgb(229, 226, 226);
}


p {
    margin-bottom: -10px;
    color: white;
    font-size: 13px;
}
i{
  color: white;
}

button.fas.fa-phone {
    background: #53f253;
    border: none;
    margin-left: 96px;
    font-size: 20px;
}
.topBar{
  display: flex;
  justify-content: space-between;
}

.time {
    margin: 0px 10px;
}

span.largeCircle {
    background: #6a6a6a;
    width: 50px;
    height: 5px;
    border-radius: 5px;
    margin-left: -9px;
}
span.circle {
    background: #6a6a6a;
    width: 6px;
    height: 6px;
    border-radius: 10px;
    margin: 9px 0px 0px -44px;
}
span {
    margin-top: 10px;
    padding: 0px 5px;
    
}
span[data-v-2a01d322] {
    margin-top: 10px;
    font-size: 12px;
    color: white;
}
i.fas.fa-battery-half {
    margin-right: 10px;
}
.bottomBar{
  display: flex;
  justify-content: space-between;
  padding: 20px 20px 2px 20px;
  font-size: 25px;
}
.bottomText{
  color: gray !important;
}
#keyboard{
  color: blue;
 
}
.valid{
  color: blue;
}
</style>
