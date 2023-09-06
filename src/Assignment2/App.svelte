<h1>Assignment</h1>

<ol>
	<li>Add a password input field and save the user input in a variable.</li>
	<li>Output "Too short" if the password is shorter than 5 characters and "Too long" if it's longer than 10.</li>
	<li>Output the password in a paragraph tag if it's between these boundaries.</li>
	<li>Add a button and let the user add the passwords to an array.</li>
	<li>Output the array values (= passwords) in a unordered list (ul tag).</li>
	<li>Bonus: If a password is clicked, remove it from the list.</li>
</ol>

<script>
	let password= ""
	let passwords = [];

	function addPassword(){
		passwords = [...passwords, password]
	}

	function removePassword(index){
		passwords = passwords.filter((pw,idx) => {
			return idx !== index;
		})
	}

</script>

<input type="password" bind:value={password} id="password" />

{#if password.trim().length < 5}
	<p>Too short</p>
{:else if password.trim().length > 10}
	<p>Too long</p>
{:else}
	<p>Password: {password}</p>
	<button on:click={addPassword}>Add password</button>
{/if}

<ul>
{#each passwords as password, index}
	<li on:click={removePassword.bind(this, index)}>{password}</li>

{/each}
</ul> 