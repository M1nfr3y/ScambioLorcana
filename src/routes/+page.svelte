<script>
    import Header from "../components/UI/Header.svelte";
    import Card from "../components/Card.svelte";
    import Footer from "../components/UI/Footer.svelte";


    let cards = ["Titolo 1", "Titolo 2", "Titolo 3", "Titolo 4"];
</script>

<Header></Header>

<div class="carousel slide" data-ride="carousel">
    {#each cards as title}
        <div class="carousel item">
            <Card {title}></Card>
        </div>
    {/each}
</div>

<Footer></Footer>


<style>
    .carousel {
        display: flex;
        justify-content: space-around;
    }
</style>
