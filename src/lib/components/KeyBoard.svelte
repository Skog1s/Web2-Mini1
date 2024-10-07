
    <section class="keyBoard">
        <button on:click value=7>7</button>
        <button on:click value=8>8</button>
        <button on:click value=9>9</button>
        <button class="operator">+</button>
        <button on:click value=4>4</button>
        <button on:click value=5>5</button>
        <button on:click value=6>6</button>
        <button class="operator">-</button>
        <button on:click value=1>1</button>
        <button on:click value=2>2</button>
        <button on:click value=3>3</button>
        <button class="operator">*</button>
        <button on:click value=".">.</button>
        <button on:click value=0>0</button>
        <button class="equals">=</button>
        <button class="operator">/</button>
        <button class="clear">CLEAR</button>
    </section>

<style lang="scss">
.keyBoard {
    width: 33%;

    button{
        width: 24.25%;
        font-size: 5rem;
        border-radius: 0.5rem;
        height: 8rem;
        color: black;

        .operator, .equals, .clear{
            color: #00BFFF;
        }

        .clear {
            min-width: 99%;
        }
    }


}


</style>