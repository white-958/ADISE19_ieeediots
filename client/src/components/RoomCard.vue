<template>
  <v-card class="room-card">
    <v-card-title class="room-card__title">{{ creator }}'s room</v-card-title>
    <div class="room-card__subcontainer">
      <span
        class="room-card__size-label"
        :class="{ 'room-card__size-label--full': roomIsFull }"
        >{{ usersJoined }}/8</span
      >
      <v-btn class="room-card__button" @click="buttonPressed"> JOIN </v-btn>
    </div>
  </v-card>
</template>

<script>
export default {
  props: {
    creator: String,
    usersJoined: Number,
    id: String
  },
  methods: {
    buttonPressed() {
      var url = this.$props.id;
      this.$router.push("/play/" + url);
    }
  },
  computed: {
    roomIsFull() {
      return this.$props.usersJoined == 8;
    }
  }
};
</script>
