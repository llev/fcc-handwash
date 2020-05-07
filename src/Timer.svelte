<script>
    import Progress from './Progress.svelte';
    import { createEventDispatcher } from 'svelte';
    
    const totalSeconds = 20;
    let secondsLeft = totalSeconds;
    let isRunning = false;
    $: progress = ((totalSeconds - secondsLeft) / totalSeconds) * 100;
    const dispatcher = createEventDispatcher();

    function startTimer() {
        isRunning = true;
        const timer = setInterval(() => {
        secondsLeft -= 1;
        if (secondsLeft == 0) {
            clearInterval(timer);
            isRunning = false;
            secondsLeft = totalSeconds;
            dispatcher("end")
        }
    }, 1000)
    }
    
</script>

<style>

.start {
    background-color: #0000ff;
    color: #fff;
    width: 100%;
}

.start[disabled] {
    background-color: #9d9d9d;
    cursor: not-allowed;
}
</style>


<div bp="grid gap-none" >
    <h3 bp="offset-5@md 4@md 12@sm">Seconds Left: {secondsLeft} </h3>
</div>
<Progress {progress}/>

<div bp="grid">
<button disabled={isRunning} on:click={startTimer} class="start" bp="offset-5@md 4@md 12@sm">Start</button>
</div>
