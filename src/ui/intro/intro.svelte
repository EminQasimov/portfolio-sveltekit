<script>
	import { DocumentIcon, DownloadIcon } from '../icons';
	import accounts from '../../utils/accounts';

	const menus = [
		{
			text: 'Blog',
			href: '#blog'
		},
		{
			text: 'Portfolio',
			href: '#portfolio'
		},
		{
			text: 'Skills',
			href: '#skills'
		},
		{
			text: 'About',
			href: '#about'
		}
	];

	const cvUrl = '/assets/Emin-Qasimov-Resume.pdf';

	function openCvNewTab(e) {
		e.preventDefault();
		window.open(cvUrl, 'Emin Qasimov CV');
	}
</script>

<section class="intro">
	<div class="container">
		<aside class="left">
			<div>
				<nav class="menu-list">
					<ul>
						{#each menus as { text, href }}
							<li>
								<a {href}>{text}</a>
							</li>
						{/each}
					</ul>
				</nav>
			</div>

			<div>
				<h1>Emin Qasımov</h1>
				<h2>Frontend Developer</h2>
			</div>

			<div>
				<div class="cv-buttons">
					<button class="view-cv">
						<a href="#viewcv" on:click={openCvNewTab}>
							<DocumentIcon /> View my cv
						</a>
					</button>

					<span> or </span>

					<button class="download-cv">
						<a href={cvUrl} download="CV - Emin Qasimov Frontend developer">
							<DownloadIcon /> Download
						</a>
					</button>
				</div>
			</div>

			<div>
				<ul class="social-buttons">
					{#each accounts as { href, title, icon }}
						<li>
							<a {href} {title}>
								<svelte:component this={icon} />
							</a>
						</li>
					{/each}
				</ul>
			</div>
		</aside>
	</div>
</section>

<style lang="scss" src="./intro.scss" global>
</style>
