<template>
  <p> Loan amount : {{totalmethod}} USD</p>

  <p>Estimated pr. month : {{totalMonth}}  USD</p>
          <div class="pop"> 
          <POP :price="price" :Dowm="Dowm" :rate="rate" :month="month" :estimated="totalMonth" :loan="totalmethod"/>
        
        </div>
</template>

<script>
import POP from './Pop.vue'
import {ref , computed} from 'vue'
export default {
    data(){
        return{
            totalmethod : 0 ,
            totalMonth : 0 
        }
    },
  components:{
POP
  }
,
props:['price' ,'Dowm', 'rate','month'],
setup(props) {
const totalmethod = computed(()=>{
    const total =(props.price - props.Dowm )
    return ( total + (( total * props.rate  ) /100))
})
const totalMonth = computed(()=>{

    return totalmethod.value/props.month

})

return {totalmethod ,totalMonth} ;
}
}
</script>

<style>
.pop{
    /* display: flex; */
  width: 100%;
  height:auto;
  background:#1D1B1B;
  padding: 50px;
  /* overflow: hidden; */
  overflow: auto;
  outline: none;
    -webkit-appearance: none;
    position: relative;
    /* display: hidden; */

}
</style>