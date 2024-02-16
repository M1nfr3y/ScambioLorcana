<script>
    import { fade } from "svelte/transition";

    export let showModal = false;

    function slideIn(node, { delay = 0, duration = 400 }) {
        return {
            delay,
            duration,
            css: (t) => `
        transform: translateX(${
            (1 - t) * 100
        }%); // Sposta il componente dall'alto verso il basso
        opacity: ${t};
      `,
        };
    }
</script>

{#if showModal}
    <div class="backdrop" transition:fade>
        <div class="modalAccount" transition:slideIn={{ duration: 400 }}>
            <div class="account-section">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="25"
                    height="25"
                    fill="currentColor"
                    class="bi bi-person-circle"
                    viewBox="0 0 16 16"
                    ><path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0" /><path
                        fill-rule="evenodd"
                        d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8m8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1"
                    />
                </svg>
                <p>Silvia la mejo</p>
                <div class="line"></div>
            </div>
            <ul class="actions">
                <li><button>Home</button></li>
                <li><button>Impostazioni</button></li>
                <li class="separator"></li>
                <li><button>Esci</button></li>
            </ul>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        z-index: 1000;
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

    .actions {
        list-style: none;
        padding: 0;
    }

    .actions li {
        margin-bottom: 5px;
    }

    .actions button {
        width: 100%;
        padding: 10px;
        border: none;
        border-radius: 5px;
        background-color: #d2b786; /* Stesso colore dello sfondo della modal */
        color: white;
        font-size: 16px;
        cursor: pointer;
        transition: background-color 0.3s; /* Aggiunge una transizione al cambiamento di colore */
        text-align: left; /* Imposta l'allineamento del testo a sinistra */
        padding-left: 20px; /* Aggiunge spazio a sinistra del testo */
    }

    .actions button:hover {
        background-color: #e3cdaa; /* Colore dello sfondo leggermente più chiaro al passaggio del mouse */
    }

    .separator {
        border-bottom: 1px solid white; /* Aggiungi una linea sottile bianca */
        margin-bottom: 10px; /* Spazio sotto la linea */
        margin-left: 3px;
        margin-right: 3px;
    }

    .account-section {
        color: white;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .account-section svg {
        width: 40px;
        height: 40px;
        margin-bottom: 15px;
        margin-top: 22px;
    }

    .account-section p {
        font-size: 20px;
    }

    .line {
        width: 100%;
        height: 1px;
        background-color: white;
        margin-bottom: 10px;
    }
</style>
