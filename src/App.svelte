<script >
	import { writable } from 'svelte/store';
	import Nested from './nested.svelte';
	let name = 'worldSamet'
	export let abc = 'testa25'
	const count2 = writable(0)
	count2.set(1)
	console.log($count2)
	export function instanceMethod() {
		alert(abc)
	}
	let count = 1
	$: doubled = count * 2
	$: quadriple = doubled *2
	function handleClick() {
		count +=1
	}
	let messageHTml = "here's some <strong>HTML!!! flash</strong>"
	$: if (count >= 10) {
		alert(`count is dangerously high!`);
		count = 0;
	}
	$: {
		console.log(`multiple statements can be combined`);
		console.log(`the current title is ${count}`);
	}
	let style = 'color: green'
</script>
<style>
	:global(*) {
		color: red;
	}
</style>

<h1>Hello {name}!</h1>
<Nested abc={messageHTml}/>
<h3 on:click={instanceMethod} {style}>Hello {abc}!</h3>

<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<p>{count} * 2 = {doubled}</p>
<p>{doubled} * 2 = {quadriple}</p>
