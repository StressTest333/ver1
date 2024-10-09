
<script>
  let Title = 'обучения';
  let src = 'https://www.meme-arsenal.com/memes/f5f8c0a96659af21ee2a18086ae8cd3a.jpg';
	import Nested from './text.svelte';
  let string = `this string contains some <strong>HTML!!!</strong>`;
  let count = 0;
  let numbers = [1, 2];
  $: sum = numbers.reduce((total, currentNumber) => total + currentNumber, 0);
  $: doubled = count * 5;
  $: if (count >= 1000) {
		alert('Достигнут лимит значений, счётчик обнуляется!');
		count = 0;
    numbers = [1, 2];
	}
	function increment() {
		count += 100;
    numbers = [...numbers, numbers.length + 1];
	}
  
</script>

<main>
  <h2>Добро пожаловать!</h2>
  <h3>Начало {Title}!</h3>
  <img {src} alt="{Title} dances." />
  <p>Котяра</p>
  <button on:click={increment}>
    Счётчик, {count}
    {count === 1 ? 'баллов' : 'баллов'}
  </button>
  <p>{count} * 5 = {doubled}</p>
  <p>{numbers.join(' + ')} = {sum}</p>
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