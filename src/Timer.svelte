<script>
    import Progress from './Progress.svelte';
</script>

<style>
h2 {
    margin: 0;
}
.start {
    background-color: #0000ff;
    color: #fff;
    width: 100%;
}
</style>


<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">Seconds Left:</h2>
</div>
<Progress />

<div bp="grid">
<button class="start" bp="offset-5@md 4@md 12@sm">Start</button>
</div>
