<script>
  import { blur } from "svelte/transition";
  import Nav from "../components/Nav.svelte";
  import SlotTransition from "../components/SlotTransition.svelte";

  export let segment;
</script>

<style>
  @keyframes -global-flicker-primary {
    0%,
    19.999%,
    22%,
    62.999%,
    64%,
    64.999%,
    70%,
    100% {
      border: 0.1rem solid;
      border-color: var(--color-primary-main);
      box-shadow: 0 0 0.75rem var(--color-primary-main);
    }
    20%,
    21.999%,
    63%,
    63.999%,
    65%,
    69.999% {
      border: 0.1rem solid;
      border-color: rgba(24, 240, 240, 0.6);
      box-shadow: 0 0 0.5rem rgba(24, 240, 240, 0.6);
    }
  }

  @keyframes -global-flicker-secondary {
    0%,
    19.999%,
    22%,
    62.999%,
    64%,
    64.999%,
    70%,
    100% {
      border: 0.1rem solid;
      border-color: var(--color-secondary-main);
      box-shadow: 0 0 0.75rem var(--color-secondary-main);
    }
    20%,
    21.999%,
    63%,
    63.999%,
    65%,
    69.999% {
      border: 0.1rem solid;
      border-color: rgba(255, 24, 96, 0.6);
      box-shadow: 0 0 0.5rem rgba(255, 24, 96, 0.6);
    }
  }

  main {
    position: relative;
    padding: 2rem;
    margin: 6rem auto 0 auto;
    box-sizing: border-box;
  }

  @media only screen and (max-width: 960px) {
    main {
      margin: 0 auto 6rem auto;
    }
  }
</style>

<svelte:head>
  <meta
    name="description"
    content="My name is Ben Chidlow, and I am a developer that likes to be where
    the future is, not where is it was" />
</svelte:head>

<Nav {segment} />

<SlotTransition bind:changer={segment} transition={blur}>
  <main>
    <slot />
  </main>
</SlotTransition>
