<script>
    export let twitter;
    export let insta;
    export let github;
    export let resume;
    export let name;

</script>

<section>
    <h1>gärten</h1>
    <h3>by <a href="{ resume }">{ name }</a></h3>
    <div id="sw">
        <a href="https://www.twitter.com/{ twitter }">t</a>
        <span> | </span>
        <a href="https://www.instagram.com/{ insta }">i</a>
        <span> | </span>
        <a href="https://www.github.com/{ github }">g</a>
    </div>
</section>

<style>
    #sw{
        width:100%;
        display:flex;
        justify-content: space-around;
        align-items:center; 
    }
    #sw > a {
        font-weight: bold;
    }
</style>