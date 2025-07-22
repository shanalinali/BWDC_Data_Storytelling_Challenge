<script>
    import { onMount } from "svelte";

    let { children, callback, options } = $props();

    // this uniqueId just lets us target the element 
    // with `document.getElementById(uniqueId)` later on.
    // it's a little hacky, but it works. 
    let uniqueId = Math.random().toString();

    // here we define the onMount() function for this component.
    // svelte handles calling the onMount() function *after* all of the HTML in this
    // component has been mounted to the DOM. we have to put the intersection observer
    // stuff in onMount() because we need to target the <div> we create below,
    // but it won't actually exist in the DOM until it's been mounted. 
    onMount(() => {
        let intersectionObserver = new IntersectionObserver(callback, options);

        const observedElement = document.getElementById(uniqueId);
        intersectionObserver.observe(observedElement);
    });
</script>

<!-- assign the containing div the id `uniqueId` so we can target it -->
<div id={uniqueId} class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        background-color: #9D6381;
        color: #f6e8ea;
        border: solid #4b2f5f 3px;
        border-radius: 65px;
        padding: 25px;
        font-size: 1.2rem;
        text-shadow: 1px 1px 0 #60595c;
        margin-top: 1rem;
        /* Font inspired by this The Pudding website: https://pudding.cool/2025/04/music-dna/ */
        font-family: var(--font-body, serif);
        transition: transform 0.5s ease; 
    }

    /* CSS animation for text content */
    .article-text:hover{
        transform: scale(1.07);
    }
</style>
