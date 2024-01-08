<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="row">

      <div class="col-md text-center">
        <h5>Example 1</h5>
        Username: {{ name }}
        <!-- input bị disabled khi giá trị disable=true -->
        <input type="text" v-model="name" v-bind:disabled="disable" class="form-control w-50 mt-2">
        <!-- Bắt sự kiện click để thay đổi giá trị disable -->
        <button @click="setDisable()" class="btn btn-primary mt-2"> Unlock</button>
      </div>

    </div>
    <div class="row mt-3">
      <div class="col-md mt-2 text-center">
        <h5>Example 2</h5>
        <!-- Hiển thị giá trị number -->
        <h5 class="text-bold">Đếm số : {{ number }}</h5>
        <!-- Bắt sự kiện click để tăng giảm giá trị number -->
        <button class="btn btn-success" v-on:click="increment()">Tăng</button>
        <button class="btn btn-warning ms-3" v-on:click="descreasement()">Giảm</button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  // Xác định tên của thành phần là "HomeView". Tên này sẽ được sử dụng trong quá trình định danh của Vue.js.
  name: 'HomeView',
  /**
   * Định nghĩa dữ liệu cho thành phần.
    name: Một biến dùng để lưu trữ giá trị của ô nhập (input).
    disable: Một biến boolean dùng để kiểm soát trạng thái "enable/disable" của ô nhập (input).
    number: Một biến dùng để lưu trữ giá trị của biến đếm.
   */
  data() {
    return {
      name: '',
      disable: true,
      number: 0

    }
  },
  /**
   * Định nghĩa các phương thức (methods) của thành phần.
    setDisable(): Phương thức này chuyển đổi giá trị của biến disable giữa true và false, 
    thay đổi trạng thái "true/false" 
    của ô nhập.
    increment(): Tăng giá trị của biến number lên 1 khi được gọi.
    descreasement(): Giảm giá trị của biến number trừ 1 khi được gọi.
*/ 
  methods: {
    setDisable() {
      if (this.disable == true) {
        this.disable = false;
      } else {
        this.disable = true
      }
    },
    increment(){
      this.number=this.number+1
    },
    descreasement(){
      this.number=this.number-1
    }
  }
}
</script>
<style>
.home {
  width: 100%
}

.col-md>input {
  margin: 0px auto
}
</style>
