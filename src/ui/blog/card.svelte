<script>
	export let post = {};

	$: ({ img, title, date, link } = post);
</script>

<div class="card">
	<div class="img__wrapper">
		<img src={img} loading="lazy" alt={title} />
	</div>
	<div class="card__title">
		<a href={'https://medium.com/@eminqasimov' + link}>
			<h3>{title}</h3>
		</a>
		<div class="paragraf">
			<div class="author-image" />
			<div class="author-data">
				<h4>Emin Qasimov</h4>
				<span>{date + ', 2019'}</span>
			</div>
		</div>
	</div>
</div>
