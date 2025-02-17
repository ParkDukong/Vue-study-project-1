<template>
    <div>
        <img :src="oneroom.image" style="width: auto; height: auto;">
        <h4 @click="$emit('openModal', oneroom.id)">{{ oneroom.title }}</h4>
        <p>{{ oneroom.price }} 만원</p>
        <p>{{ oneroom.content }}</p>
    </div>
</template>

<script>
export default {
    props : {
        oneroom: Object
    }
}
</script>