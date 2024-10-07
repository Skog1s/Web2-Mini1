<script>
    import Display from "../lib/components/Display.svelte";
    import KeyBoard from "../lib/components/KeyBoard.svelte";
    import '$lib/global.scss';

    function clickBtn(e){ 
        lcd = lcd + e.target.value;   
    }
</script>
 
<Display />
<KeyBoard on:click={clickBtn} />