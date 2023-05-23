<script>
	import Details from './Details.svelte';
	
	  let formData = {
		name: '',
		email: '',
		// Add more fields as needed
	  };
	
	  function handleSubmit() {
		// Handle form submission logic here
		// You can make an API request or perform any other necessary actions
		// Once the submission is successful, show the details
		showDetails = true;
	  }
	
	
	  let showDetails = false;
	</script>
	
	<form on:submit|preventDefault={handleSubmit}>
	  <label for="name">Name:</label><br/>
	  <input type="text" id="name" bind:value={formData.name} required><br/>
	
	  <label for="email">Email:</label><br/>
	  <input type="email" id="email" bind:value={formData.email} required><br/>
	
	  <!-- Add more fields as needed -->
	  <br/>
	<button class="btn btn-primary" type="submit">Submit</button>
	  
	</form>
	
	{#if showDetails}
	  <Details {formData}/>
	{/if}
	