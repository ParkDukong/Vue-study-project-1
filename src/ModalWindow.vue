<template>
    <div class="black-bg" v-if="modal_open == true">
      <div class="white-bg">
        <h3>집 상세내용</h3>
        <img :src=onerooms[click_number].image>
        <h4>{{ onerooms[click_number].title }}</h4> 
        <p>가격 : {{ onerooms[click_number].price }}</p>
        <p>{{ onerooms[click_number].content }}</p>
        <button @click="modal_open = false">닫기</button>
      </div>
    </div>
</template>

<script>

export default {
    name: "ModalWindow"
}
</script>