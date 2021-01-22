<script>
import Nested from './components/Nested.svelte';

let name = 'world';
let src = 'favicon.png';
let string = `This string contains some <strong>HTML!!!</strong>`;
</script>

<h1>Hello {name}!</h1>
<img src={src} alt="A man dances" />
<p class="custom-1">This is a paragraph.</p>
<Nested />
<p>{@html string}</p>

<style>
p.custom-1 {
  color: purple;
  font-family: cursive;
  font-size: 2em;
}
</style>
