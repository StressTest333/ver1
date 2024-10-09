
<script>
  let Title = 'обучения';
  let src = 'https://www.meme-arsenal.com/memes/f5f8c0a96659af21ee2a18086ae8cd3a.jpg';
	let name = 'Rick Astley';
  import Nested from './text.svelte';
  let string = `this string contains some <strong>HTML!!!</strong>`;
</script>

<main>
  <h2>Добро пожаловать!</h2>
  <h3>Начало {Title}!</h3>
  <img {src} alt="{name} dances." />
  <p>Котяра</p>
  <Nested />
  <p>{@html string}</p>
</main>

<style>
	p {
		color: green;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>