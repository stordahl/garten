<script>
    let current = false;
</script>

<div id="wtfWrap" class:open="{ current === true }" on:click="{ () => current = !current}">
    <h6 class="headline">wtf?</h6>
    <h6 class="sub">this is my code garden; a place to experiment, try new things & learn</h6>
</div>

<style>
    #wtfWrap{
        position:absolute;
        top:0;
        right:0;
        display:flex;
        align-items: center;
        justify-content: center;
        width:175px;
        cursor: pointer;
        transform:translate(130px, 500px);
        transition: transform 200ms;
        transition-timing-function: ease;
    }
    .open{
        transition: transform 200ms;
        transition-timing-function: ease;
        transform:translate(0px, 500px) !important;
    }
    .headline{
        writing-mode: vertical-rl;
        text-orientation: upright;
        margin:1rem;
    }
    .sub{
        max-width:100px;
    }
    @media screen and (min-width:900px){
        #wtfWrap{
            transform:translateX(130px);
        }
        .open{
            transition: transform 200ms;
            transition-timing-function: ease;
            transform:translateX(0px) !important;
        }
    }
</style>