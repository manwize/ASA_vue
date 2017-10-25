<template>
	<div class="container">
		<h2>User Profile</h2>
		<button class="btn btn-danger" 
        @click="u_clearData">
          Clear
      </button>

      <button class="btn btn-primary" 
        @click="u_saveData">
          Save
      </button>
      <button class="btn btn-success" 
        @click="navigate_to_Vehicle">
          Save & Continue
      </button>
	</div>
</template>

<script>
export default {
	name: 'UserComponent',
	data () {
	  return {
	  	json: null
	  }
	},
  methods: {
    u_clearData: function () {
      alert('Clearing information')
    },
    u_saveData: function () {
      alert('Saving information')
    },
    u_submitData: function () {
      alert('Submitting information')
    },
    navigate_to_Vehicle: function () {
      this.$router.push('/vehicle');
    },
     created: function () {
      fetch("/data.json")
        .then(r => r.json())
        .then(json => {
          this.json=json;
        });
    }
  }
}
</script>