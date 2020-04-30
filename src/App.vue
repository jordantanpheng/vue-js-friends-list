<template>
  <div>
    <div>
	  <h1>Participants list</h1>
	  <participants-list :list="participants" @removed="removeParticipant($event)"></participants-list>
    </div>
    <h3>New participant</h3>
    <new-participant-form @added="addNewParticipant($event)"></new-participant-form>
  </div>
</template>

<script>
  import ParticipantsList from "./ParticipantsList.vue";
  import NewParticipantForm from "./NewParticipantForm.vue";
  export default {
    components: {NewParticipantForm, ParticipantsList},
    data() {
      return {
	    participants: []
	  };
    },
    methods: {
      addNewParticipant(newParticipant) {
        this.participants.push(newParticipant);
      },
	  removeParticipant(participant) {
	    this.participants.remove(participant);
	  }
    }
  };
</script>