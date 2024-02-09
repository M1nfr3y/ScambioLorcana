<script>
    export let showModal = false;
</script>

{#if showModal}
    <div class="backdrop">
        <div class="modalAccount">
            <h1>Sign up for offers!</h1>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }

    .modalAccount {
        position: static;
        border-radius: 10px;
        margin-top: 0.5%;
        width: 300px;
        height: 600px;
        text-align: center;
        background: #d2b786;
    }
</style>
