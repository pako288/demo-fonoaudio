<script>
	import somos1 from '../images/somos1.jpg';
	import somos2 from '../images/somos2.jpg';
	import somos3 from '../images/somos3.jpg';

	let titleSomos = `Somos Fonoaudiologia`

	const imagenes = $state([
		{
			image: somos1,
			description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, porro!`
		},
		{
			image: somos2,
			description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, porro!`
		},
		{
			image: somos3,
			description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati, porro!`
		}
	]);
</script>

<section>
	<h2> {titleSomos} </h2>

	<article class="main-article">
		{#each imagenes as img}
			<article class="box">
				<figure>
					<img src={img.image} alt="" width="400" height="400" />
				</figure>
				<p>
					{img.description}
				</p>
			</article>
		{/each}
	</article>
</section>

<style>
	section {
		background: var(--secundary);
		/* background: red; */
		color: var(--azulito);
		& h2 {
			padding-top: 20px;
			text-align: center;
			font-size: 30px;
			font-weight: bold;
		}
	}

	.main-article {
		/* background: blue; */
		margin-top: 40px;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(min(240px, 43%), 1fr));
		justify-content: center;
		align-items: center;
		gap: 40px;
		padding: 20px;
	}
	.box {
		display: flex;
		flex-direction: column;
		align-items: center;
		color: var(--secundary);
		border-radius: 20px;
		gap: 20px;
		padding: 10px;
		height: max-content;
		min-height: 240px;
		background: linear-gradient(to left, rgb(24, 84, 163) 10%, rgb(131, 182, 127));
		position: relative;
	}

	figure {
		position: absolute;
		top: -30px;
	}

	img {
		border-radius: 50%;
		height: 180px;
		width: 100%;
		aspect-ratio: 1/1;
	}

	p {
		text-wrap: pretty;
		text-align: center;
		margin-top: 200px;
		width: 80%;
		font-weight: bold;
	}
</style>
