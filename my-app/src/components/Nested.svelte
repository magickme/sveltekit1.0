<script>
    export let name = "Svelte"
    let src =
        "https://media.istockphoto.com/id/1209650664/photo/happy-well-dressed-gentleman-having-photoshooting-in-studio.jpg?s=612x612&w=is&k=20&c=4yU-3Ip8njIMCUyUunLfLq20ZCA5K0ahpSC72dOvMF4="
    export let clan = 'Panders'
    export let pack
    export let city
    export let path
</script>

<img {src} alt="A {name} man dances." />
<h1>Hello {name.toUpperCase()}!</h1>
<p>Welcome to the Sabbat!</p>
<p>I see that you're a shovelhead of the {clan} clan, of the {pack} pack from {city}, and a follower of the Path of {path}. Welcome—enter freely and of your own will!</p>

<style>
    p {
        color: purple;
        font-family: "Comic Sans MS", cursive;
        font-size: 2em;
    }
</style>
