<script>

  const getBurger = (async () => {
		const response = await fetch('https://bobsburgers-api.herokuapp.com/burgerOfTheDay/20')
    return await response.json()
	})()


</script>

{#await getBurger}
	<p>...waiting</p>
{:then data}
<p>{data.name}</p>
<p>{data.price}$</p>
<p>season {data.season}</p>
<p>episode {data.episode}</p>
    
{:catch error}
	<p>An error occurred!</p>
{/await}