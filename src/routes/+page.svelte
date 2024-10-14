<script>
    import Display from "../lib/components/Display.svelte";
    import {lcd} from "../lib/components/Display.svelte";
    import KeyBoard from "../lib/components/KeyBoard.svelte";
    import Calculate from "../lib/components/Calculate.svelte";
    import '$lib/global.scss';

    let mem = 0;
    let isComma = false;

    function clickBtn(e){ 
        let val = e.target.value;


        if(val === Number) {
            addDigit();
        }
        

    }

    function addDigit() {
        $lcd = $lcd + val;

    }


</script>
 
<Display />
<KeyBoard on:click={clickBtn} />