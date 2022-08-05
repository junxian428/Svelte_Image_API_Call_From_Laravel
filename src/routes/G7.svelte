<script>
	const fetchImage = (async () => {
		const response = await fetch('http://localhost:8000/api/PhotoAPI')
    return await response.json()
	})()

    console.log(fetchImage)
</script>

{#await fetchImage}
	<p>...waiting</p>
{:then data}
	<img src={data[0]['image']} alt="Image" />
{:catch error}
	<p>An error occurred!</p>
{/await}