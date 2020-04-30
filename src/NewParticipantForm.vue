<template>
  <div>
    <form @submit.prevent="add()">
	<div class="form-group">
      <label>Firstname</label>
      <input type="text" class="form-control" placeholder="Enter firstname" v-model="newParticipant.firstname">
      <label>Lastname</label>
      <input type="text" class="form-control" placeholder="Enter lastname" v-model="newParticipant.lastname">
	  <br>
      <button class="btn btn-primary mb-2">Add new participant</button>
	</div>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {newParticipant: {}};
    },
    methods: {
      add() {
        this.$emit('added', this.newParticipant);
        this.newParticipant = {};
      }
    }
  };
</script>