<script lang="ts">
	import {useChat} from "ai/svelte"
	const {messages, handleSubmit, input} = useChat({
		api: "/chat",
	})
</script>

   <img
      src="https://safaridesmetiers.tech/wp-content/uploads/2019/08/Simplon-logo-simplon.co_.png"
      width="500"
      height="100"

	  alt="logo simplon"
    />
	<h2>Démo Simplon: Formatteur dev IA Chat Bot</h2>
<ul>
	{#each $messages as message}
		<li>{message.role} dit... {message.content}</li>
	{/each}
</ul>

<form on:submit={handleSubmit}>
	<input bind:value={$input}/>
	<button type= "submit">Envoyer</button>
</form>
