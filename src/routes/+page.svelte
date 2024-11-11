<script>
    import KeyBoard from "../lib/components/KeyBoard.svelte";
    import '$lib/global.scss';

    let lcd = "";
    let mem = 0;
    let arithmetic;
    let commaSet = false;
    
    
    function clickBtn(e){ 
        let num = e.target.value;
        if(num.substring(0, 1) ==="b") {
            num = num.substring(1, 2)
            lcd = lcd + num;  
     }
     else if(num === "+") {
        setOperator("add");
     }
     else if(num === "-") {
        setOperator("sub");
     }
     else if (num === "*") {
        setOperator("mul");
     }
     else if(num === "/") {
        setOperator("div");
     }
     else if(num === "clear") {
        clearMem();
     }
     else if(num === "equals") {
        calculate();
     }
     else if(num === ".") {
        checkComma();
     }

    }

    function setOperator(operator) {
        mem = lcd;
        if(operator === "add") {
            arithmetic = "+";
        }
        else if(operator === "sub") {
            arithmetic = "-";
        }
        else if(operator === "mul") {
            arithmetic = "*";
        }
        else if(operator === "div") {
            arithmetic = "/";
        }

        clearLcd();

    }

    function roundIt(tempVal) {
    tempVal = Math.round(tempVal * 1e14) / 1e14;
    return tempVal;
}

    function calculate() {
        if(arithmetic === "+") {
        lcd = +mem + +lcd;
        lcd = roundIt(lcd);

    }
    else if(arithmetic === "-") {
        lcd = mem - lcd;
        lcd = roundIt(lcd);

    }
    else if(arithmetic === "*") {
        lcd = mem * lcd;
        lcd = roundIt(lcd);

    }
    else if(arithmetic === "/") {
        lcd = mem / lcd;
        lcd = roundIt(lcd);

    }
    }

    function checkComma() {
        if(commaSet === false) {
        lcd = lcd + '.';
        commaSet = true;
    }
    else {
        console.log("komma finns")
    }

    }

    function clearLcd() {
        lcd = "";
        commaSet = false;
    }

    function clearMem() {
        clearLcd();
        mem = 0;
        arithmetic = null;
    }

</script>
 
<section>
    <input type="text" value={ lcd } disabled>
</section>

<KeyBoard on:click={clickBtn} />

