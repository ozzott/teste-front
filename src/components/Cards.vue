<template>
  <div>
      
    <div class="select_all_box">  
        <a class="check"><p> Selecionar tudo </p><i class="material-icons">check_box_outline_blank</i></a>
    </div>

    <section class="cards">
      <div v-for="(item, i) in items" :key="'A' + i">
        <Card v-bind:item='item'/> 
      </div>
    </section>
    
  </div>
</template>

<script>
import api from "../config/api";
import Card from "./Card";

export default {
  data () {
    return {
      items: []
     }
  },
  destroyed () { },
  mounted () { },
  created () {
      api.get("cards?_sort=id&_order=asc").then(
      (response) => {
      this.items = response.data;
      },
      (error) => {
        console.log("error", error);
      }
    );
 },
  
  name: 'Cards',
  props: [],
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
  },
   components: {
    Card
    
  },

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