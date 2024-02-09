<script>
    import { fade } from "svelte/transition";

    export let showModal = false;

    function slideIn(node, { delay = 0, duration = 400 }) {
    return {
      delay,
      duration,
      css: (t) => `
        transform: translateX(${(1 - t) * 100}%); // Sposta il componente dall'alto verso il basso
        opacity: ${t};
      `
    };
  }

</script>

{#if showModal}
    <div class="backdrop" transition:fade>
        <div class="modalAccount" transition:slideIn={{ duration: 400 }}>
            <h1>Sign up for offers!</h1>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.274);
    }

    .modalAccount {
        position: absolute;
        right: 0;
        margin-right: 25px;
        border-radius: 10px;
        margin-top: 0.5%;
        width: 300px;
        height: 600px;
        text-align: center;
        background: #d2b786;
    }


</style>
