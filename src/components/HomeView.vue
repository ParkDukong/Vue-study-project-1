<template>
    <div>
        <img :src="oneroom.image">
        <h4 @click="$emit('openModal', oneroom.id)">{{ oneroom.title }}</h4>
        <p>{{ oneroom.price }} 만원</p>
    </div>
</template>

<script>
export default {
    props : {
        oneroom: Object
    }
}
</script>