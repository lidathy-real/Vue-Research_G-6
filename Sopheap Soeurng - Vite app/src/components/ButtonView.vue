<template>
    <div class="name-card" v-for="card in cards" :key="card">
        <div class="full-name">
            <h3>{{card.firstName}} {{card.lastName}}</h3>
        </div>
        <div class="comment-card">
            <p>{{card.comment}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['cards']
};
</script>
