<script>
    import { onMount, onDestroy } from 'svelte';
let time = new Date();
$: hours = time.getHours();
$: minutes = time.getMinutes();
$: seconds = time.getSeconds();
$: dayorNight = (hours >= 12) ? "PM" : "AM";

onMount(() => {
    const interval = setInterval(() => {
        time = new Date();
    }, 1000);
})

onDestroy(() => {
    clearInterval(interval);
})

</script>

<div>{ hours }: { minutes }: { seconds } { dayorNight }</div>

<style>
    div {
        display: flex;
        height: 100%;
        width: 100%;
        justify-content: center;
        align-items: center;
        color: #ff3e00;
        font-size: 5em;
        font-weight: 100;
    }
</style>
