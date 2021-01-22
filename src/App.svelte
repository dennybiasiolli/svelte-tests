<script>
import Nested from './components/Nested.svelte';

let name = 'world';
let src = 'favicon.png';
let string = `This string contains some <strong>HTML!!!</strong>`;
let count = 0;
$: doubled = count * 2;

function handleClick() {
  count += 1;
}
</script>

<h1>Hello {name}!</h1>
<img src={src} alt="A man dances" />
<p class="custom-1">This is a paragraph.</p>
<Nested />
<p>{@html string}</p>
<button on:click={handleClick}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<p>{count} doubled is {doubled}</p>

<style>
p.custom-1 {
  color: purple;
  font-family: cursive;
  font-size: 2em;
}
</style>
