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
                <!-- <li><button>Le mie carte</button></li> -->
                <li>
                    <button>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-arrow-down-left"
                            viewBox="0 0 16 16"
                        >
                            <path
                                fill-rule="evenodd"
                                d="M2 13.5a.5.5 0 0 0 .5.5h6a.5.5 0 0 0 0-1H3.707L13.854 2.854a.5.5 0 0 0-.708-.708L3 12.293V7.5a.5.5 0 0 0-1 0z"
                            />
                        </svg> Proposte ricevute</button
                    >
                </li>
                <li>
                    <button>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-arrow-up-right"
                            viewBox="0 0 16 16"
                        >
                            <path
                                fill-rule="evenodd"
                                d="M14 2.5a.5.5 0 0 0-.5-.5h-6a.5.5 0 0 0 0 1h4.793L2.146 13.146a.5.5 0 0 0 .708.708L13 3.707V8.5a.5.5 0 0 0 1 0z"
                            />
                        </svg> Proposte inviate</button
                    >
                </li>
                <li class="separator"></li>
                <li>
                    <button>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-gear-fill"
                            viewBox="0 0 16 16"
                        >
                            <path
                                d="M9.405 1.05c-.413-1.4-2.397-1.4-2.81 0l-.1.34a1.464 1.464 0 0 1-2.105.872l-.31-.17c-1.283-.698-2.686.705-1.987 1.987l.169.311c.446.82.023 1.841-.872 2.105l-.34.1c-1.4.413-1.4 2.397 0 2.81l.34.1a1.464 1.464 0 0 1 .872 2.105l-.17.31c-.698 1.283.705 2.686 1.987 1.987l.311-.169a1.464 1.464 0 0 1 2.105.872l.1.34c.413 1.4 2.397 1.4 2.81 0l.1-.34a1.464 1.464 0 0 1 2.105-.872l.31.17c1.283.698 2.686-.705 1.987-1.987l-.169-.311a1.464 1.464 0 0 1 .872-2.105l.34-.1c1.4-.413 1.4-2.397 0-2.81l-.34-.1a1.464 1.464 0 0 1-.872-2.105l.17-.31c.698-1.283-.705-2.686-1.987-1.987l-.311.169a1.464 1.464 0 0 1-2.105-.872zM8 10.93a2.929 2.929 0 1 1 0-5.86 2.929 2.929 0 0 1 0 5.858z"
                            />
                        </svg> Impostazioni</button
                    >
                </li>
                <li>
                    <button
                        ><svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-person-plus-fill"
                            viewBox="0 0 16 16"
                        >
                            <path
                                d="M1 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6"
                            />
                            <path
                                fill-rule="evenodd"
                                d="M13.5 5a.5.5 0 0 1 .5.5V7h1.5a.5.5 0 0 1 0 1H14v1.5a.5.5 0 0 1-1 0V8h-1.5a.5.5 0 0 1 0-1H13V5.5a.5.5 0 0 1 .5-.5"
                            />
                        </svg> Invita i tuoi amici</button
                    >
                </li>
                <li>
                    <button
                        ><svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-question-circle-fill"
                            viewBox="0 0 16 16"
                        >
                            <path
                                d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M5.496 6.033h.825c.138 0 .248-.113.266-.25.09-.656.54-1.134 1.342-1.134.686 0 1.314.343 1.314 1.168 0 .635-.374.927-.965 1.371-.673.489-1.206 1.06-1.168 1.987l.003.217a.25.25 0 0 0 .25.246h.811a.25.25 0 0 0 .25-.25v-.105c0-.718.273-.927 1.01-1.486.609-.463 1.244-.977 1.244-2.056 0-1.511-1.276-2.241-2.673-2.241-1.267 0-2.655.59-2.75 2.286a.237.237 0 0 0 .241.247m2.325 6.443c.61 0 1.029-.394 1.029-.927 0-.552-.42-.94-1.029-.94-.584 0-1.009.388-1.009.94 0 .533.425.927 1.01.927z"
                            />
                        </svg> Assistenza</button
                    >
                </li>
                <li class="separator"></li>
                <li>
                    <button>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="16"
                            height="16"
                            fill="currentColor"
                            class="bi bi-box-arrow-left"
                            viewBox="0 0 16 16"
                        >
                            <path
                                fill-rule="evenodd"
                                d="M6 12.5a.5.5 0 0 0 .5.5h8a.5.5 0 0 0 .5-.5v-9a.5.5 0 0 0-.5-.5h-8a.5.5 0 0 0-.5.5v2a.5.5 0 0 1-1 0v-2A1.5 1.5 0 0 1 6.5 2h8A1.5 1.5 0 0 1 16 3.5v9a1.5 1.5 0 0 1-1.5 1.5h-8A1.5 1.5 0 0 1 5 12.5v-2a.5.5 0 0 1 1 0z"
                            />
                            <path
                                fill-rule="evenodd"
                                d="M.146 8.354a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L1.707 7.5H10.5a.5.5 0 0 1 0 1H1.707l2.147 2.146a.5.5 0 0 1-.708.708z"
                            />
                        </svg> Esci</button
                    >
                </li>
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
