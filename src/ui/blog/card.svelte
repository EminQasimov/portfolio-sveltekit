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
			<p class="author-name">{title}</p>
		</a>
		<div class="paragraf">
			<div class="author-image" />
			<div class="author-data">
				<p>Emin Qasimov</p>
				<span>{date + ', 2019'}</span>
			</div>
		</div>
	</div>
</div>
