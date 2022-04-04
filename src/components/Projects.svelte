<script>
    import Project from '../components/Project.svelte';

    let projects = [
		{
			name: 'looking',
			url: 'https://looking.netlify.app/',
		},
        {
            name: 'sketchbook',
            url: 'https://sketchbook.stordahl.dev'
        },
    ];
    let current = false;
    
</script>
<div id="nav-wrap" class:open="{ current === true }" on:click="{ () => current = !current}">
    <h6  >projects</h6>
<nav>
    {#each projects as project}
        <Project project={ project }/>
    {/each}    
</nav>
</div>

<style>
    #nav-wrap{
        position: absolute;
        top:0;
        left:0;
        transform: translate(-100px, 55%);
         transition: transform 200ms;
        transition-timing-function: ease;
        display: flex;
        flex-direction:row-reverse;
        align-items: center;
        justify-content: center;
        cursor: pointer;
    }
    .open{
        transition: transform 200ms;
        transition-timing-function: ease;
        transform:translate(35px, 55%) !important;
    }
    h6{
        writing-mode: vertical-rl;
        text-orientation: upright;
        
        margin:1rem;
    }
    nav{
        display:flex;
        flex-direction: column;
        
    }
    @media screen and (min-width:900px){
        #nav-wrap{
            transform: translate(-100px, 200%);
         transition: transform 200ms;
        transition-timing-function: ease;
        }
        .open{
        transition: transform 200ms;
        transition-timing-function: ease;
        transform:translate(35px, 200%) !important;
    }
    }
</style>