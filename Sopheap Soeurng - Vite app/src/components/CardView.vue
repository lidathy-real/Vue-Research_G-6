<template>
  <form>
    <div class="main-card">
      <h2>Add User :</h2>
    </div>
    <div class="form-group">
      <input type="firstname" placeholder="First Name" v-model="firstName" />
    </div>
    <div class="form-group">
      <input type="lastname" placeholder="Last Name" v-model="lastName" />
    </div>
    <div class="form-group">
      <input type="comment" placeholder="Comment" v-model="comment" />
    </div>
    <div class="form-group">
      <button @click="AddCard">Add Card</button>
    </div>
    <button-view :cards="cards"></button-view>
  </form>
</template>

<script>
import ButtonView from "./ButtonView.vue";

export default {
  components: {
    "button-view": ButtonView,
  },
  data() {
    return {
      firstName: "",
      lastName: "",
      comment: "",
      cards: [],
    };
  },
  methods: {
    AddCard(event) {
      event.preventDefault();
      let cardList = {};
      cardList.firstName = this.firstName.toUpperCase();
      cardList.lastName = this.lastName.toUpperCase();
      cardList.comment = this.comment;
      if (
        this.firstName !== "" &&
        this.lastName !== "" &&
        this.comment !== ""
      ) {
        this.cards.push(cardList);
        console.log(this.cards);
      }
    },
  },
};
</script>
