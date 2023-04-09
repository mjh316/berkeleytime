<script lang="ts">
  import {Temporal} from 'temporal-polyfill';
  let time = Temporal.PlainDateTime.from(Temporal.Now.plainDateTimeISO());
  let startOfDay = Temporal.PlainDateTime.from({year: time.year, month: time.month, day: time.day, hour: 0, minute: 0, second: 0, millisecond: 0, microsecond: 0, nanosecond: 0});
  let count = startOfDay.until(time, {largestUnit: 'minute'});
</script>

<main class="flex flex-col items-center justify-center h-screen text-center mx-10 snap-start">
  <h1 class="text-4xl mt-auto font-semibold">There's been <em>{count.minutes}</em> minutes since {startOfDay.toLocaleString()}.</h1>  

  <h2 class="font-semibold text-2xl mt-4">
    just kidding, it's <em>actually</em> been...
  </h2>
    <svg class="mt-auto animate-bounce bottom-0 h-32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 12 15 18 9"></polyline></svg>
</main>

<div class="snap-start h-screen w-screen flex items-center justify-center" id="second_page">
  <p class="px-10 break-all text-3xl ml-auto mr-auto ">{'Berkeley'.repeat(count.minutes / 10) + 'Time!'}
    </p>
</div>
<style>
  .break-all {
    font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  }
</style>
