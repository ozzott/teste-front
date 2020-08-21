<template>
    <div>
    
      <div class="sidebar">
        <img src="../assets/brand.svg">
          
        <div class="menu">

            <div class="menu_data">
              <img src="../assets/accounts.svg">
              <p>Minhas atividades</p>
            </div>

            <div class="menu_data">
              <img src="../assets/accounts.svg">
              <p>Todas as contas</p>
            </div>

            <div class="menu_data">
              <img src="../assets/user.svg">
              <p>Usuários</p>
            </div>

            <div class="menu_data">
              <img src="../assets/performance.svg">
              <p>Desempenho</p>
            </div>

            <div class="menu_data">
              <img src="../assets/dashboard.svg">
              <p>Dashboard</p>
            </div>
        </div>
    </div>   

      <header class="page_content">

          <div class="head">
            <img id="arrow_img" src="../assets/arrow.svg"> 
            <h1> Unidade Internação I</h1>
            <p>Auditar conta</p>
          </div>
      

        <div class="cards_quantity">
            
            <div class="red">
              <h5><img src="../assets/red_situation.png">4 cards</h5>
              <p class="total_accounts"><span style = "color:  #A7B2CE;">Total: </span><span style = "color:  #000066;"> 54 contas</span></p> 
            </div>

            <div class="yellow">
              <h5><img src="../assets/yellow_situation.png">7 cards</h5>
            </div>

            <div class="green">
              <h5><img src="../assets/green_situation.png">43 cards</h5>
            </div>
        </div>

        <div class="dropdown">
          <h5>Organizar por:</h5>
          <select>
            <option>Prioridade(SLA)</option>
            <option>Receber documentos</option>
          </select>
        </div>
        
    </header>
  </div>
</template>


<script>
export default {
  data () {
    return { }
  },
  destroyed () { },
  mounted () { },
  name: 'Activity',
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Fira+Sans:wght@300;400;700&family=Open+Sans:wght@300;400;700&family=Recursive:wght@300;400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');

* {
    margin: 0;
    padding: 0;
    border: 0;
}

.sidebar {
    position: fixed;
    left: 0;
    width:90px;
    background-color:#E7EBF7;
    height: 100%;
}

 .menu img {
    padding-top: 30px;
 }


.menu {
    text-align: center;
    font-family: 'Roboto', sans-serif;
    font-size: 13px;
    color: #A7B2CE;
    
}

.menu .menu_data:hover {
  border-left: 5px solid #2793FF;
  color: #2793FF;
  cursor: pointer;
  
}

.menu .menu_data:active {
  border-left: 5px solid #2793FF;
  color: #2793FF;
  
}

header {
    max-width: 1450px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 160px;
    padding: 35px 50px 35px 0px;
    font-family: 'Fira Sans', sans-serif;
    
}
.head h1 {
    font-size: 40px;
    font-weight: lighter;
    color: #000066;
    position: relative;
}

.head p {
    color: #B6BFCA;
    font-size: 15px;
}

.head #arrow_img{
  float: right;
  padding-top: 15px;
  padding-right: 120px;
  cursor: pointer;
  position: absolute;
  left: 600px;  
}

.cards_quantity {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;   
  padding-top: 10px;
}

.total_accounts {
  padding-top: 5px;
}

.cards_quantity img {
  border-radius: 50%;
  max-width: 6px;
  max-height: 6px;
  margin-right: 5px;
}

.cards_quantity h5 {
  font-family: 'Roboto', sans-serif;
  font-weight: normal;
  color: #000066 ;
  font-size: 16px;
}

.cards_quantity p {
  font-size: 12px;
}




.dropdown {
  position: relative;
  width: 300px;
  display: flex; 
}

.dropdown h5 {
  margin-right: 20px;
  padding-top: 10px ;
  white-space: nowrap;
  font-family: 'Open Sans', sans-serif;
  color:#4E566D;
}

.dropdown select {
  color:#4E566D;
  width: 100%;
}

.dropdown > * {
  box-sizing: border-box;
  height: 2.5em;
}

</style>