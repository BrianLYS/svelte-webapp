<script>
	export let name;
	export let age;

	function incrementAge() {
		age += 1;
	}

	function changeName() {
		name = "Svelte";
	}

	let username = '';
    let password = '';

    function handleLogin() {
        // Validate the username and password
        if (username === 'admin' && password === 'password') {
            alert('Login successful');
        } else {
            alert('Login failed');
        }
    }

	// Authenticate from backend
	// async function handleLogin() {
    //     // Send a request to the server with the user's credentials
    //     const response = await fetch('/api/login', {
    //         method: 'POST',
    //         headers: { 'Content-Type': 'application/json' },
    //         body: JSON.stringify({ username, password })
    //     });

    //     // Check the response from the server
    //     if (response.ok) {
    //         const data = await response.json();
    //         alert(data.message);
    //     } else {
    //         alert('Login failed');
    //     }
    // }
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}! You are {age} years old</h1>
<button on:click="{incrementAge}"> Increment age </button>
<!-- create text input -->
<input type="text" bind:value="{name}" />

<h1>Login</h1>
<form on:submit|preventDefault={handleLogin}>
    <label for="username">Username:</label>
    <input type="text" id="username" bind:value={username} />

    <label for="password">Password:</label>
    <input type="password" id="password" bind:value={password} />

    <button type="submit">Login</button>
</form>