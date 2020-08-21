<template>
     
      <div class="card"> 

        <a class="check"><i class="material-icons">check_box_outline_blank</i></a>
          <div class="card_head" v-bind:class='getClassColor(item.status)'>
          <p><span id="count_days">{{item.days}}</span> Dias</p> 
        </div>
        
        <div class="name">  
          <h1>{{item.patientName}} </h1>
          <p><span id="health_insurance" >{{item.healthInsurance}}</span></p> 
        </div>
                                        
        <div class="card_data" >
          <p v-for="(billSources, i) in item.billSources" :key="i"><span id="data_title">{{billSources.label}}</span><br> <span id="data_number"> <b>{{billSources.value}} </b> </span> </p>
  
        </div>
         
        <div class="value_pendencies">
          <h2>R$ {{item.value}}</h2>
          <p>{{item.pendencies}} pendências</p>
          
        </div>

        <div class="card_footer">
           <div class="initials_footer"> 
             <p v-for="(billTypes, i) in item.billTypes" :key="i" ><span id="item1_footer">{{billTypes}}</span></p> 
            
           </div>

            <div class="footer_icons">
                <img src="../assets/attachment.svg">
                <img src="../assets/document.svg">
            </div>
        
        </div>
        
      </div>
  
</template>

<script>

export default {
  data () {
    return {
      items: [
        
      ]
     }
  },
  destroyed () { },
  mounted () { },
  created  () { },
  name: 'Card',
  props: [
    'item'
  ],
  methods:  {
    getClassColor(status) {
      if(status === 'WARNING'){
        return 'color2' 
      }  
      else if (status === 'DELAYED'){
        return 'color1'
      }
      return 'color3'
    }
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Fira+Sans:wght@300;400;700&family=Lato:wght@300;400;700&family=Open+Sans:wght@300;700&family=Recursive:wght@300;400;500;600;700&display=swap');

.select_all_box  {
  position: absolute;
  top: 0;
}

.cards {
  max-width: 1500px;
  margin: 0 10vh;
  padding-top: 50px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 50px;
  padding-left: 50px 100px;
  
}

.card{
  box-shadow: 1px  1px  3px  1px #c3c3c3;
  background-color: #FFFFFF;
  position: relative;
  text-align: center;
  left: 10%;
}

.card_head {
 
  padding: 25px;
  
  max-width: 30px;
  max-height: 30px;
  border-radius: 50%;
  margin: 15px;
  color: white;
  font-family: 'Roboto', sans-serif;
  display: flex;
  justify-content: center; 
  align-items: center; 
  float: left;
  
}

.card_head.color1{
background-color:#FE5959;
}

.card_head.color2{
background-color: #FFC733 ;
}

.card_head.color3{
background-color:#20BF6B ;
}
.card_head p {
  font-size:15px ;
  
}

.card_head #count_days { 
  font-size: 30px;
 
}

.cards .name {
  float: left;
  padding-top: 30px;
  font-family: 'Fira Sans', sans-serif;
  
}

.card .name h1 {
  font-weight: lighter;
  color: #2C2F3A;
  position: relative;
  
}

.card .name p {
    color: #B6BFCA;
    font-size: 12px;
    padding-top: 5px;
    position: absolute;
    
} 

 .check { 
  position: absolute;
  right: 0;
  color: #525A70;
  padding: 10px;
  cursor: pointer;
}
.card_data {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  width: 88%;
  padding: 10px 0px 0px 20px;
  color: #2C2F3A;
  font-family: 'Fira Sans', sans-serif;
  gap: 20px;
 
  padding-bottom: 30px;
 
}

.card_data #data_title {
  font-size: 15px;
  
}

.card_data #data_number{ 
  font-size: 20px;
  color: #525A70;
  
}

.cards .value_pendencies {
  display: flex;
  gap: 125px;
  text-align: center;
  padding: 10px; 
  margin: 0 auto;
  max-width: 80%;
  background-color: #F5F6F9;
  font-family: 'Fira Sans', sans-serif;
  white-space: nowrap;
}

.cards .value_pendencies h2 {
  
  font-weight: lighter;
  color: #3F414B;
  font-family: 'Lato', sans-serif;
  font-weight: bold;
  font-size: 20px;
}

.cards .value_pendencies p {
  color: #2793FF;
  border: 1px solid #2793FF;
  padding: 5px 20px;
  border-radius: 20px 20px 20px 20px;
  
}

.card_footer .initials_footer {
  display: flex;
  padding: 15px;
  gap: 10px

}
.card_footer .initials_footer p {
  border: 2px solid #7A8093;
  padding: 6px 10px 6px 10px;
  border-radius: 60%;
   font-family: 'Roboto', sans-serif;
  color: #7A8093; 
  font-weight: bold;
 
}


.card .card_footer {
  display: grid;
  grid-template-columns: 1fr 1fr;

}

.card .footer_icons {
  position: absolute;
  right: 0;
  bottom: 0;
  padding: 15px;
}

.card .footer_icons:hover {
  cursor: pointer;
  
}

.card .footer_icons img:hover {
  background-color: lightgrey;
  border-radius: 20%;
}


</style>