<script>
	let name = "Jack";
	let age = 26;

	function incrementAge(){
		age += 1;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}! My age is {age}</h1>
<buton on:click="{incrementAge}" >Change Age</buton>
