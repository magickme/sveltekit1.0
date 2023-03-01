<script>
    import Nested from '../components/Nested.svelte'

    // Reactivity: Assignments
    let count = 0
    function increment() {
        count += 1
    }

    // Reactivity: Declarations
    $: doubled = count * 2

    // Reactivity: Statements

    $: {
        console.log(`the count is ${count}`)
        console.log(`I SAID THE COUNT IS ${count}`)
    }
    $: if (count >= 10) {
        console.log('count is dangerously high!')
        count = 0
    }
    
    // Reactivity: Updating arrays and objects

    let numbers = [1, 2, 3, 4]

    function addNumber() {
        numbers.push(numbers.length + 1)
        numbers = [...numbers, numbers.length + 1]
    }

    // Props Spread

    const shovelhead = { 
        name: 'Viteus',       
        clan: 'Lasombra',
        pack: 'Dead Spurs',
        city: 'Detroit',
        path: 'Cathari'
    }

    // If blocks - apparently needs some kind of TS

    // import Logic from '../components/Logic.svelte' 

    // Else-if

    let x = Math.floor(Math.random() * 10)

    // Each

    let cats = [
		{
			id: 'J---aiyznGQ',
			name: 'Keyboard Cat'
		},
		{
			id: 'z_AbfPXTKms',
			name: 'Maru'
		},
		{
			id: 'OUtn3pvWmpg',
			name: 'Henri The Existential Cat'
		}
	];

    // Keyed each blocks

</script>

<Nested
    {...shovelhead}
/>

<!-- <Logic /> -->

<p>We hope you enjoy your stay!</p>

<button on:click={increment}>
    Clicked {count}
    {count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {doubled}</p>

<p>The number is {x}</p>

{#if x > 10}
    <p>{x} is greater than 10</p>
{:else}
    {#if 5 > x}
        <p>{x} is less than 5</p>
    {:else}
        <p>{x} is between 5 and 10</p>
    {/if}
{/if}    

<h1>Here are the other members of your pack:</h1>

<ul>
    {#each cats as cat, i}
	<!-- open each block -->
    
	<li>
		<a
			target="_blank"
			href="https://www.youtube.com/watch?v={cat.id}"
            rel="noreferrer"
		>
			{i + 1}: {cat.name}
		</a>
	</li>
	<!-- close each block -->
    {/each}
</ul>
