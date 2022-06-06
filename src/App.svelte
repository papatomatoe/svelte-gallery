<script>
	let images = [
		{
			id: 1,
			full: "https://images.unsplash.com/photo-1654032390271-6e786c4e49f0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80",
			preview:
				"https://images.unsplash.com/photo-1654032390271-6e786c4e49f0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwxNHx8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 2,
			full: "https://images.unsplash.com/photo-1648737155328-0c0012cf2f20?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80",
			preview:
				"https://images.unsplash.com/photo-1648737155328-0c0012cf2f20?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwzNXx8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 3,
			full: "https://images.unsplash.com/photo-1654147801998-1f2f4aa9486b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1051&q=80",
			preview:
				"https://images.unsplash.com/photo-1654147801998-1f2f4aa9486b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw1M3x8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 4,
			full: "https://images.unsplash.com/photo-1654124983654-333683b0ba71?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80",
			preview:
				"https://images.unsplash.com/photo-1654124983654-333683b0ba71?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw2OHx8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 5,
			full: "https://images.unsplash.com/photo-1654147127874-766687deea20?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80",
			preview:
				"https://images.unsplash.com/photo-1654147127874-766687deea20?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw4M3x8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 6,
			full: "https://images.unsplash.com/photo-1654099521678-bfb05b565b03?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1025&q=80",
			preview:
				"https://images.unsplash.com/photo-1654099521678-bfb05b565b03?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw5OHx8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 7,
			full: "https://images.unsplash.com/photo-1654108535097-b828b2c1ad8e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1004&q=80",
			preview:
				"https://images.unsplash.com/photo-1654108535097-b828b2c1ad8e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwxMDV8fHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
		},
		{
			id: 8,
			full: "https://images.unsplash.com/photo-1653773712213-4c51f7768da7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80",
			preview:
				"https://images.unsplash.com/photo-1653773712213-4c51f7768da7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwxMDd8fHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60",
		},
	];

	let index = 0;

	$: selectedImage = images[index];

	const handleSelectImage = (idx) => {
		index = idx;
	};

	const handleNextIdx = () => {
		index = index >= images.length - 1 ? 0 : index + 1;
	};

	const handlePrevIdx = () => {
		index = index <= 0 ? images.length - 1 : index - 1;
	};

	const scroll = (node) => ({
		update(isSelect) {
			isSelect && node.scrollIntoView({ behavior: "smooth", inline: "center" });
		},
	});
</script>

<div class="gallery">
	<div class="container">
		<button
			class="button previous"
			type="button"
			aria-label="previous"
			on:click={handlePrevIdx}
		/>
		<img class="main-image" src={selectedImage.full} alt="main" />
		<button
			class="button next"
			type="button"
			aria-label="next"
			on:click={handleNextIdx}
		/>
	</div>
	<div class="wrapper">
		<ul class="preview">
			{#each images as image, idx (image.id)}
				<li use:scroll={idx === index} class="preview__item">
					<button
						class="button preview__button"
						class:active={idx === index}
						type="button"
						on:click={() => handleSelectImage(idx)}
						><img
							class="preview__image"
							src={image.preview}
							alt="prw"
						/></button
					>
				</li>
			{/each}
		</ul>
	</div>
</div>

<style>
	.gallery {
		width: 950px;
		margin: 0 auto;
		padding: 20px 0;
	}

	.container {
		display: grid;
		grid-template-columns: min-content 800px min-content;
		align-items: center;
		gap: 20px;
	}

	.button {
		position: relative;
		width: 40px;
		height: 40px;
		margin: 0;
		padding: 0;
		background-color: transparent;
		border: none;
		cursor: pointer;
	}

	.previous::before,
	.next::before {
		position: absolute;
		content: "";
		width: 30px;
		height: 30px;
		top: 50%;
		left: 50%;
		border: 3px solid gray;
		border-top: none;
		border-left: none;
	}

	.previous::before {
		transform: translate(-50%, -50%) rotateZ(135deg);
	}

	.next::before {
		transform: translate(-50%, -50%) rotateZ(-45deg);
	}

	.main-image {
		width: 800px;
		height: 450px;
		object-fit: contain;
		object-position: center;
	}

	.wrapper {
		width: 100%;
		height: 200px;
		margin-top: 20px;
		overflow: hidden;
		overflow-x: auto;
	}

	.preview {
		list-style: none;
		width: fit-content;
		margin: 0;
		padding: 10px;
		display: flex;
		gap: 20px;
	}

	.preview__item {
		width: 150px;
		height: 150px;
		background-color: rgb(227, 227, 227);
	}

	.active {
		box-shadow: 0 0 0 3px skyblue;
	}

	.preview__button {
		width: auto;
		height: auto;
		display: block;
	}

	.preview__image {
		display: block;
		width: 150px;
		height: 150px;
		object-fit: contain;
		object-position: center;
	}
</style>
