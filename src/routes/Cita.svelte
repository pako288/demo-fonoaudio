<script>
	import cita from '../images/cita.jpg';
	import photoCita from '../images/photo-cita.jpg';
	import book from '../images/book.svg';
	let parrafoInfo = `Nos mantenemos a la vanguardia para atender eficazmente las diferentes áreas de la comunicación
	`;
	let toggle = $state(false);

	const onclick = (e) => {
		e.preventDefault();
		toggle = true;
	};

	const noModal = (e) => {
		e.preventDefault();
	};
</script>

<h1>Agenda tu cita</h1>
<section>
	<article>
		<p>
			{parrafoInfo}
		</p>

		<button {onclick}
			><svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24"
				><path
					fill="#00000080"
					d="M19 3.25H6.75a2.43 2.43 0 0 0-2.5 2.35V18a2.85 2.85 0 0 0 2.94 2.75H19a.76.76 0 0 0 .75-.75V4a.76.76 0 0 0-.75-.75m-.75 16H7.19A1.35 1.35 0 0 1 5.75 18a1.35 1.35 0 0 1 1.44-1.25h11.06Zm0-4H7.19a3 3 0 0 0-1.44.37V5.6a.94.94 0 0 1 1-.85h11.5Z"
				/><path
					fill="#6ef174"
					d="M8.75 8.75h6.5a.75.75 0 0 0 0-1.5h-6.5a.75.75 0 0 0 0 1.5m0 3.5h6.5a.75.75 0 0 0 0-1.5h-6.5a.75.75 0 0 0 0 1.5"
				/></svg
			>Agenda tu cita aquí</button
		>
	</article>

	<figure class="photoCita">
		<img src={photoCita} alt="" />
	</figure>

	{#if toggle}
		<dialog open={toggle}>
			<figure>
				<img src={cita} alt="" />
			</figure>
			<form action="">
				<label for="asunto"
					>Asunto
					<input type="text" name="" id="asunto" placeholder="Asunto" />
				</label>
				<label for="paciente"
					>Nombre del paciente
					<input type="text" name="" id="paciente" placeholder="Nombre del paciente" />
				</label>
				<button onclick={noModal} class="submit">Enviar</button>



				<svg
					onclick={() => (toggle = false)}
					xmlns="http://www.w3.org/2000/svg"
					width="42"
					height="42"
					viewBox="0 0 24 24"
					><path
						fill="#e70404"
						d="M12 20c-4.41 0-8-3.59-8-8s3.59-8 8-8s8 3.59 8 8s-3.59 8-8 8m0-18C6.47 2 2 6.47 2 12s4.47 10 10 10s10-4.47 10-10S17.53 2 12 2m2.59 6L12 10.59L9.41 8L8 9.41L10.59 12L8 14.59L9.41 16L12 13.41L14.59 16L16 14.59L13.41 12L16 9.41z"
					/></svg
				>
			</form>
		</dialog>
	{/if}
</section>

<style>
	section {
		height: 90dvh;
		padding: 20px;
		background: linear-gradient(to top left, #6ef174 30%, transparent 50%);
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(min(280px, 100%), 1fr));
		place-content: center;
		gap: 30px;
		/* grid-auto-rows: 80dvh; */
	}
	p {
		color: var(--azulito);
		font-size: 18px;
		font-weight: 600;
		width: 50%;
	}

	button {
		background: linear-gradient(to left, rgb(110, 241, 116), #1854a3);
		border-radius: 20px;
		padding: 10px;
		cursor: pointer;
		width: 230px;
		margin-top: 20px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	article {
		padding-left: 20px;
		display: flex;
		justify-content: center;
		flex-direction: column;
	}
	.photoCita {
		& img {
			width: 100%;
			/* height: 400px; */
			object-fit: cover;
			/* object-position: 50% ; */
			aspect-ratio: 1/1;
		}
	}
	dialog {
		position: fixed;
		top: 50%;
		transform: translateY(-50%);
		z-index: 11;
		display: flex;
		background: var(--secundary);
		width: 90%;
		height: 80dvh;
		background: linear-gradient(to bottom left, #6ef174 30%, #fff 50%);

		& figure {
			width: 100%;

			& img {
				height: 100%;
				width: 100%;
			}
		}

		& form {
			display: flex;
			padding: 10px;
			width: 100%;
			justify-content: center;
			flex-direction: column;
			align-items: center;

			& label {
				width: 100%;
				padding: 10px;
				display: flex;
				flex-direction: column;
				color: var(--azulito);

				& input {
					width: 80%;
					height: 40px;
					padding: 10px;
					border-radius: 20px;
				}
			}
			& svg {
				position: absolute;
				top: 10px;
				right: 10px;
				height: 40px;
			}

			& .submit{
				width: 40%;
			}
		}
	}
</style>
