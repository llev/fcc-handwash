<script>
    import Timer from './Timer.svelte';
    import HowTo from './HowTo.svelte';
    let audio; 
    function timerEnds(e) {
        audio.play();
    }
</script>


<h1 class="title">Handwash App</h1>

<Timer on:end={timerEnds} />
<HowTo />

<div bp="grid">

<h6 bp="offset-5@md 2@md 12@sm">
<a href="https://www.who.int/gpsc/clean_hands_protection/en/">Picture Source</a>
</h6>

<h6 bp="2@md 12@sm">
<a href="https://freesound.org/people/metrostock99/sounds/345086/">Sound Source</a>
</h6>

</div>

<audio bind:this={audio} src="sound.wav"></audio>