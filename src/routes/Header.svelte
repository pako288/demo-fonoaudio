<script>
	import portada from '../images/portada.jpg';
	import menu from '../images/menu.svg';

	let contador = $state(0);
	let showMenu = $state(false);

	const handleClick = () => {
		showMenu = !showMenu;
		console.log(`click`)
	};

	$effect(() => {
		contador = window.innerWidth;
	});
</script>

<header>
	<div class="mani {contador > 500 ? "casi" : ""}" onclick={handleClick} >
	<img src={menu} alt="">
	</div>
	<nav class ="{showMenu ? "otro" : ""} {contador < 500 ? "rte" : "main-nav"}">
		<a href="#">Inicio</a>
		<a href="#">Quienes somos</a>
		<a href="#">Solicita tu cita</a>
		<a href="#">Más información</a>
	</nav>

	<section class="header-section">
		<article>
			<h3>Aqui va la informacion sobre la pagina de <span>landing page</span></h3>
		</article>
		<figure>
			<img src={portada} alt="" />
		</figure>
	</section>
</header>

<style>
	header {
		padding: 0 20px;
		height: 100dvh;
		background: white;
		color: var(--secundary);
		background: linear-gradient(to right, rgb(24, 84, 163) 10%, rgb(131, 182, 127));

		& nav {
			/* background: blue; */
			text-align: end;
			color: var(--azulito);
			padding: 10px;
			font-size: 18px;
			display: block;
		}

		& .header-section {
			height: 95dvh;
			padding: 20px;
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(min(300px, 100%), 1fr));
			place-content: center;
			gap: 20px;

			& article {
				display: flex;
				font-size: 20px;

				justify-content: center;
				align-items: center;

				& h3 {
					text-align: center;

					& span {
						background: linear-gradient(to left bottom, rgb(18, 40, 236), rgb(243, 35, 80));
						color: transparent;
						background-clip: text;
						font-weight: 700;
					}
				}
			}
			& figure {
				& img {
					border-radius: 50%;
					width: 100%;
					height: 100%;
					object-position: center;
				}
			}
		}
	}

	.mani {
		display: block;
		position: fixed;
		top: 5px;
		right: 20px;
		z-index: 999999;
	}
	

	
	
	.rte {
		position: fixed;
		right: 0;
		top: 0;
		height: 100dvh;
		display: flex;
		justify-content: space-evenly;
		background: #ffffff;
		background: linear-gradient(to right, white 20%, var(--verdedos));
		align-items: center;
		width: 100%;
		flex-direction: column;
		transition: 0.3s linear;
		z-index: 999;
		clip-path: polygon(100% 0, 100% 0, 100% 0, 100% 0);
	}
	.otro {
		position: fixed;
		right: 0;
		top: 0;
		height: 100dvh;
		display: flex;
		justify-content: space-evenly;
		background: #ffffff;
		background: linear-gradient(to right, white 20%, var(--verdedos));
		align-items: center;
		width: 100%;
		flex-direction: column;
		transition: 0.3s linear;
		z-index: 999;
		clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
	}
	.casi {
		display: none;
	}
	.main-nav{
		text-align: end;
			color: var(--azulito);
			padding: 10px;
			font-size: 18px;
			display: block;
	}

	/* @media (width < 500px) {

		nav{
			display: none;
		
		
		}
	} */
</style>
