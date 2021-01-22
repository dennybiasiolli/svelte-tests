<script>
import Nested from './components/Nested.svelte';

let name = 'world';
let src = 'favicon.png';
let string = `This string contains some <strong>HTML!!!</strong>`;
let count = 0;
let ccc = 0;
$: doubled = count * 2;
$: if (count >= 10) {
  alert(`count is dangerously high!`);
  count = 9;
}
$: console.log(`the count is ${count}`);
$: console.log(`the ccc is ${ccc}`);
$: console.log(`both are ${count} and ${ccc}`);

function handleClick() {
  count += 1;
}
function handleCcc() {
  ccc += 1;
}
</script>

<h1>Hello {name}!</h1>
<img src={src} alt="A man dances" />
<p class="custom-1">This is a paragraph.</p>
<Nested answer={42} />
<p>{@html string}</p>
<button on:click={handleClick}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<button on:click={handleCcc}>
  Clicked {ccc} {count === 1 ? 'time' : 'times'}
</button>
<p>{count} doubled is {doubled}</p>

<style>
p.custom-1 {
  color: purple;
  font-family: cursive;
  font-size: 2em;
}
</style>
