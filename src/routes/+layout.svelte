<script>
    import Display from "../lib/components/Display.svelte";
    import KeyBoard from "../lib/components/KeyBoard.svelte";
    import '$lib/global.scss';
</script>

<Display></Display>
<slot></slot>
<KeyBoard></KeyBoard>