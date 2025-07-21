<!-- Note: Attended Office Hours with KWK Jasmine to figure out this code! -->
<script>
    import { onMount } from "svelte";

    let { title, subtitle, author } = $props();
    let visible = $state(false);

    function typewriter(node, { speed = 1 }) {
        const valid =
            node.childNodes.length === 1 &&
            node.childNodes[0].nodeType === Node.TEXT_NODE;

        if (!valid) {
            throw new Error(
                `This transition only works on elements with a single text node child`,
            );
        }

        const text = node.textContent;
        const duration = text.length / (speed * 0.01);

        return {
            duration,
            tick: (t) => {
                const i = Math.trunc(text.length * t);
                node.textContent = text.slice(0, i);
            },
        };
    }

    onMount(() => {
        visible = !visible;
    });
</script>

<div class="title-card">
    <div class="content">
        {#if visible}
            <h1
                transition:typewriter
                onintroend={() => (visible = !visible)}
                onoutroend={() => (visible = !visible)}
            >
                {title}
            </h1>
        {/if}
        <p>{subtitle}</p>
        <h3>{@html author}</h3>
    </div>
</div>

<style>
.title-card {
    background-color: #22181c;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
}

.content {
    max-width: 700px;
    background-color: #d78388;
    padding: 2rem;
    border: 6px solid #5a0001;
    border-radius: 2rem;
    box-shadow: 10px 10px 5px #190a0b;
}

h1 {
    font-size: 3rem;
    margin: 0;
    color: #5a0001;
    text-shadow: 1px 1px 0 #22181c;
    font-family: Times, "Times New Roman", serif;
}

h3 {
    margin: 0;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #36242b;
    font-family: Times, "Times New Roman", serif;
}

p {
    font-size: 1.3rem;
    color: #f6e8ea;
    text-shadow: 1px 1px 0 #36242b;
    margin-top: 1rem;
    font-family: Georgia;
}

@media (max-width: 600px) {
    h1 {
      font-size: 2.2rem;
    }

    p {
      font-size: 1.1rem;
    }
}
</style>