<template>
    <div class="black-bg" v-if="modal_open == true">
      <div class="white-bg">
        <h3>집 상세내용</h3>
        <img :src=onerooms[click_number].image style="width: 50%;">
        <h4>{{ onerooms[click_number].title }}</h4> 
        <select v-model="option">
          <option>미선택</option>
          <option>에어컨</option>
          <option>냉장고</option>
          <option>청소기</option>
        </select>
        <p></p>
        <input v-model="month">
        <p>{{ month }}개월 선택 가격 : {{ onerooms[click_number].price * month }}</p>
        <p>선택 기본 1개 옵션 : {{ option }}</p>
        <p>{{ onerooms[click_number].content }}</p>
        
        <button @click="$emit('closeModal')">닫기</button>
      </div>
    </div>
</template>
<script>
export default {
    name: "ModalWindow",
    data() {
        return {
            month : 1,
            option : ""
        }
    }, 
    props : {
      onerooms : Array,
      click_number : Number,
      modal_open : Boolean
    }
}
</script>