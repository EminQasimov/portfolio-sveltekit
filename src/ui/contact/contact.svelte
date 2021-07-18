<script>
	import { LocationIcon, MailIcon, PhoneIcon } from '../icons';
	import accounts from '../../utils/accounts';
</script>

<section class="contact bg" id="about">
	<div class="container">
		<div class="contact-about">
			<p>Who</p>
			<h1>I am</h1>
			<div class="about">
				I wrote my first "Hello World" in 2013 and started off as a self-taught coder. I am now a
				full- fledged Frontend developer since 2019. I improve my knowledge and skills continually
				and learn new, modern technologies - like GraphQL, SSR, Testing, NoSQL, Typescript etc. for
				creating amazing, performant web applications. When I don't write code or read books, I play
				the accordion and write technical articles on Medium. If you want to contact and get faster
				response then use Messenger below.
			</div>
		</div>

		<div class="contact-info">
			<p>My</p>
			<h1>Contacts</h1>
			<div class="contact-info-list">
				<div class="contact-left">
					<ul class="contact-text">
						<li>
							<MailIcon />
							<a href="mailto:eminqasimov@outlook.com"> eminqasimov@outlook.com </a>
						</li>
						<li>
							<LocationIcon /> Baku, Azerbaijan
						</li>
						<li>
							<PhoneIcon />
							<a href="tel:+994517873301"> (+99451) 787 33 01</a>
						</li>
					</ul>

					<ul class="social-buttons">
						{#each accounts as { href, title, icon }}
							<a {href} {title}>
								<li>
									<svelte:component this={icon} />
								</li>
							</a>
						{/each}
					</ul>
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss" src="./contact.scss" global>
</style>
