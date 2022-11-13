<template>
<div class="container">
  <h1> Mortgage Calculator</h1>
<p> Purchase price: {{price}} USD</p>
<p>Down payment:  {{Dowm}}USD</p>
<p> Repayment time: {{month}}   months </p>
<p> Interest rate: {{rate}}   months </p>
<p>Estimated pr. month: {{estimated}} USD</p>
<p>Loan amount: {{loan}} USD</p>

<button class="copy">Copy</button>

<button class="close">Close</button>
</div>

</template>

<script>
export default {
props:['price','Dowm','rate','month','estimated' ,'loan']
}
</script>

<style>
/* .box {
  perspective: 120px;
} */
.copy {
position:absolute;
  bottom:0;
  left:0;
  width:20%;
  background: #333333;
  height:50px;
  margin: 5px;
  border-radius: 10px;
box-shadow: 5px 5px 10px inset;
  overflow: auto;
}
.close {
position:absolute;
  bottom:0;
  right:0;
  width:20%;
  background: #333333;
  border-radius: 10px;
  height:50px;
  margin: 5px;
  overflow: auto;
box-shadow: 5px 5px 10px inset;
}
.copy:hover{
    animation: spin 1.5s ease-in-out 1;
}
.close:hover{
  /* padding-bottom:20px; */
  /* padding-bottom: 50px; */
 /* font-size:50px; */
    animation: spin 1.5s ease 1;

}
.container{
  /* position: relative; */
}

@keyframes spin {
  to {
    transform: rotateY(540deg);
  }
}
</style>