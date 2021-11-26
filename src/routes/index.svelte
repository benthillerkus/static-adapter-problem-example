<script context="module">
  export const ssr = false
  export const prerender = true
  export const hydrate = false

  export async function load ({ page, fetch}) {
    const markdown = await fetch("/HELLO.md")

    return {
      props: {
        markdown: await markdown.text()
      }
    }
  }
</script>

<script>
  export let markdown
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<code>{markdown}</code>
