<script>
	import photoinfo from '../images/info.jpg';

    const texto = `Lorem, ipsum dolor sit amet consectetur adipisicing elit. Blanditiis temporibus distinctio earum excepturi impedit saepe commodi, soluta eos, omnis at aspernatur natus ipsum dolorem alias sed.`

    const titleInfo = `Información`
</script>

<h1>{titleInfo}</h1>
<section>

	<figure>
		<img src={photoinfo} alt="" />
	</figure>
    <article>
        <p>{texto}</p>
    </article>
</section>

<style>
    	
	section {
		height: 500px;
		background: linear-gradient(to top , rgb(110, 241, 116) 30%, transparent 50%);
		display: grid;
		padding: 20px;
        grid-template-columns: repeat(auto-fit, minmax(min(280px, 100%), 1fr));
        place-content: center;
	
	
		& figure {
            margin: 0 auto;
			& img {
				height: 340px;
                border-radius: 30px;
				aspect-ratio: 1/1;
			}
		}
	}
    article{
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
        margin: 0 auto;
        width: 90%;
    }
    p{
        color: var(--azulito);
        text-align: center;
        text-wrap: pretty;
        font-size: 16px;
        font-weight: 600;
    }
</style>
