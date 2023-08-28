<script>
	import ContactCard from './ContactCaqrd.svelte'

	let name = "Jack";
	let title = ""
	let imageUrl=""
	let description = ""
	let age = 26;

	$:uppercaseName = name.toUpperCase()

	$: console.log(name);

	$: if(name === "JackLi"){
		console.log("It runs")
		age = 31;
	}

	function incrementAge(){
		age += 1;
	}

	function changeName(){
		name = "JackLi"
	}

	function nameInput(event){
		const enteredValue = event.target.value
		name = enteredValue
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}! My age is {age}!</h1>
<button on:click="{incrementAge}" >Change Age</button>
<!-- <button on:click="{changeName}">Change Name</button> -->
<!-- <input type="text" value="{name}" on:input={nameInput}> -->

<input type="text" bind:value="{name}" placeholder="name"/>
<input type="text" bind:value="{title}"
placeholder="title"/>
<input type="text" bind:value="{imageUrl}"
placeholder="imageUrl"/>
<textarea row="3" bind:value="{description}"></textarea>
<ContactCard
userName={name}
jobTitle={title} 
{description}
imagePath = {imageUrl}/>
