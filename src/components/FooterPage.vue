<template>
  <div >   
    <footer>
        <div class="footer_page">
          
          <a class="left_arrow"><i class="material-icons">keyboard_arrow_left</i></a>
            <p>1</p>
            <p>2</p>
            <p>3</p>
            <p>4</p>
            <p>5</p>
          <a class="right_arrow"><i class="material-icons">keyboard_arrow_right</i></a>  
        </div>
      </footer>  
  </div>

</template>

<script>

export default {
  data () {
    return { }
  },
  destroyed () { },
  mounted () { },
  name: 'FooterPage',
  props: [
   
  ]
  
}
</script>

<style>
footer {
        bottom: 0;
        position: fixed;
        width: 100%;
        text-align: center;
        position: relative;
        padding-top: 70px;
        padding-bottom: 40px;
        left: 37%;
        font-family: 'Roboto';
    }

footer .footer_page {
  display: flex;
  gap: 40px;
  color: #a6a6a6;
}

footer .footer_page p {
  padding: 5px;
}

footer .footer_page p:hover {
background-color: #2793FF;
border-radius:10%;
cursor: pointer;
}

footer .footer_page p:active {
background-color: #2793FF;
border-radius:10%;
}
</style>