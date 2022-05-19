<script>
  let shown = true;
  let moved = 0;

  const toggleShow = () => (shown = !shown);
  const toggleMove = () => (moved = moved ? 0 : 500);
</script>

<div style="opacity: {shown ? 1 : 0}">Content to toggle</div>
<br />
<button on:click={toggleShow}>Toggle</button>
<hr />
<div class="box" style="transform: translateX({moved}px)">I'm a box.</div>
<br />
<button on:click={toggleMove}>Move it!</button>