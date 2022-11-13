<template>
  <main>
    <div class="container">
      <div class="row row-cols-2">
        <div class="col">
          <p class="para">Purchase Price: {{ pprice }} USD</p>
          <input
            type="range"
            step="1000"
            v-model="pprice"
            min="0"
            max="10000000"
            name=""
            id=""
          />
        </div>
        <div class="col">
          <p>Down payment: {{ count }} USD</p>
          <!-- <input type="number" v-model="Numberpayment" name="" id=""> -->
          <input
            type="range"
            :step="200"
            v-model="Dpaym"
            min="0"
            :max="pprice"
            name=""
            id=""
          />
        </div>

        <div class="col">
          <div class="input-group">
            <p>Repayment time: {{ time_month }} month</p>
            <input
              type="range"
              step="1"
              v-model="time_month"
              min="1"
              max="120"
              name=""
              id=""
            />
          </div>
        </div>
        <div class="col">
          <div class="input-group">
            <p>Interest rate {{ rate }} %</p>
            <input
              type="range"
              step="1"
              v-model="rate"
              min="0"
              max="100"
              name=""
              id=""
            />
          </div>
        </div>
      </div>
    </div>

    <div>
      <LOAN :price="pprice" :Dowm="Dpaym" :rate="rate" :month="time_month" />
    </div>
  </main>
</template>

<script>
import LOAN from "./amount.vue";
import { ref, computed } from "vue";

export default {
  data() {
    return {
      pprice: 0,
      Dpaym: 0,
      Numberpayment: 0,
      time_month: 1,
      rate: 0,
      // dvalue : 0
    };
  },
  components: {
    LOAN,
  },
  computed: {
    count: function () {
      if (this.pprice <= 0) {
        this.Dpaym = 0;
      }
      return this.Dpaym;
    },
  },
};
</script>

<style>
input {
  width: 100%;
  height: 15px;
  background: #72b382;
  overflow: hidden;
  outline: none;
  -webkit-appearance: none;
  border-radius: 15%;
  box-shadow: inset 0 0 5px black;
  padding: 20px;
}
p {
  padding: 20px;
}
.main-container {
  display: inline-block;
}
.para {
  display: flex;
}
</style>

