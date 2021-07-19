<script>
	import Git from './logos/git.svelte';
	import Ant from './logos/ant.svelte';
	import Bash from './logos/bash.svelte';
	import Css from './logos/css.svelte';
	import Cypress from './logos/cypress.svelte';
	import Docker from './logos/docker.svelte';
	import Es6 from './logos/es6.svelte';
	import Eslint from './logos/eslint.svelte';
	import Express from './logos/express.svelte';
	import Figma from './logos/figma.svelte';
	import Firebase from './logos/firebase.svelte';
	import Html from './logos/html.svelte';
	import Jest from './logos/jest.svelte';
	import Jquery from './logos/jquery.svelte';
	import Js from './logos/js.svelte';
	import Material from './logos/material.svelte';
	import Mongo from './logos/mongo.svelte';
	import Nest from './logos/nest.svelte';
	import Next from './logos/next.svelte';
	import Node from './logos/node.svelte';
	import Npm from './logos/npm.svelte';
	import Prettier from './logos/prettier.svelte';
	import React from './logos/react.svelte';
	import Redux from './logos/redux.svelte';
	import Sass from './logos/sass.svelte';
	import Sql from './logos/sql.svelte';
	import Story from './logos/story.svelte';
	import Svelte from './logos/svelte.svelte';
	import Ts from './logos/ts.svelte';
	import Vite from './logos/vite.svelte';
	import Webpack from './logos/webpack.svelte';
	import Yarn from './logos/yarn.svelte';
	import Browser from './logos/browser.svelte';

	const data = [
		{
			icon: Html,
			title: 'Html5'
		},
		{
			icon: Css,
			title: 'Css'
		},
		{
			icon: Sass,
			title: 'Sass'
		},
		{
			icon: Js,
			title: 'Javascript'
		},
		{
			icon: Ts,
			title: 'Typescript'
		},
		{
			icon: React,
			title: 'React'
		},
		{
			icon: Redux,
			title: 'Redux'
		},
		{
			icon: Svelte,
			title: 'Svelte'
		},
		{
			icon: Next,
			title: 'Next'
		},
		{
			icon: Node,
			title: 'Node'
		},

		{
			icon: Ant,
			title: 'AntDesign'
		},
		{
			icon: Material,
			title: 'Material UI'
		},

		{
			icon: Git,
			title: 'Git'
		},
		{
			icon: Cypress,
			title: 'Cypress'
		},

		{
			icon: Jest,
			title: 'Jest'
		},
		{
			icon: Eslint,
			title: 'Eslint'
		},
		{
			icon: Prettier,
			title: 'Prettier'
		},
		{
			icon: Npm,
			title: 'Npm'
		},
		{
			icon: Yarn,
			title: 'Yarn'
		},

		{
			icon: Story,
			title: 'Storybook'
		},
		{
			icon: Vite,
			title: 'Vite'
		},
		{
			icon: Webpack,
			title: 'Webpack'
		},
		{
			icon: Browser,
			title: 'Extentions'
		},
		{
			icon: Docker,
			title: 'Docker'
		},
		{
			icon: Es6,
			title: 'Es6'
		},
		{
			icon: Express,
			title: 'Express.js'
		},

		{
			icon: Firebase,
			title: 'Firebase'
		},

		{
			icon: Mongo,
			title: 'MongoDb'
		},
		{
			icon: Nest,
			title: 'Nest'
		},

		{
			icon: Sql,
			title: 'Sql'
		},
		{
			icon: Bash,
			title: 'Bash'
		},
		{
			icon: Jquery,
			title: 'Jquery'
		},
		{
			icon: Figma,
			title: 'Figma'
		}
	];
</script>

<section class="skills" id="skills">
	<div class="container">
		<p>My</p>
		<h1>Skills</h1>
		<div class="wrapper-two">
			<ul class="skill-items">
				{#each data as { icon, title }}
					<li class="skill">
						<div class="skill-icon">
							<svelte:component this={icon} />
						</div>
						<div class="skill-title">
							{title}
						</div>
					</li>
				{/each}
			</ul>
		</div>
	</div>
</section>

<style lang="scss" src="./skills.scss" global></style>
