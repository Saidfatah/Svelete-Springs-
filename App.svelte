<script>
 import { spring } from "svelte/motion";

 const fadeSpring = spring(1, { stiffness: 0.1, damping: 0.5 });
 const transformSpring = spring(0, { stiffness: 0.9, damping: 0.7 });

 const toggleFade = () => fadeSpring.update(val => (val ? 0 : 1));
 const toggleTransform = () => transformSpring.update(val => (val ? 0 : 500));
 const snapTransform = () => transformSpring.update(val => val, { hard: true });
</script>

<div style="opacity: {$fadeSpring}">Content to toggle</div>
<br />
<button on:click={toggleFade}>Toggle</button>
<hr />
<div class="box" style="transform: translateX({$transformSpring}px)">I'm a box.</div>
<br />
<button on:click={toggleTransform}>Move it!</button>
<button on:click={snapTransform}>Snap into place</button>