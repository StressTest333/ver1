<script>
    /**
     * функция, переключающая компоненты
     */
    export let app_function;
    // export let parr
    // let arr = parr//[1, 2, 3, 4, 5];
    import { tarr } from "./store.js";

    function addItem() {
        if ($tarr.length == 0) {
            $tarr = [...$tarr, 0];
        } else {
            $tarr = [...$tarr, Math.max(...$tarr) + 1];
        }
    }

    let numberclick = 0
    function clicksum1() {
        numberclick = numberclick + 1;
    }
    function clicksum100() {
        numberclick = numberclick + 100;
    }
    function clickum() {
        numberclick = numberclick * 2;
    }
    function clicknclear() {
        numberclick = 0;
    }
    
    const removeItem = () => {
        $tarr.splice(0, 1);
        $tarr = [...$tarr];
        console.log($tarr);
    };
    let flt = 0.1;
    const filterby = (idx) => {
        flt = idx;
    };
</script>
<body>
    <div class="wrapper">
        <h1>Массивы и циклы</h1>
        <div>
            <button class="btn-new" on:click={() => clicksum1()}>+1</button>
            <button class="btn-new" on:click={() => clicksum100()}>+100</button>
            <button class="btn-new" on:click={() => clickum()}>*2</button>
            <button class="btn-new" on:click={() => clicknclear()}>Очистить</button>
            <h1>{numberclick}</h1>
        </div>
    </div>
</body>
<style>
    /*button {
        width: 100px;
        height: 50px;
        background-color: red;
        color: azure;
    }*/
    .btn-new {
        width: 100px;
        height: 50px;
        border-radius: 20px;
        color: white;
        transition: .2s linear;
        background: #0bf63a;
    }

    .btn-new:hover {
    box-shadow: #21c500 0 0px 0px 40px inset;
    }
    .wrapper {
        border: 1px solid silver;
        border-radius: 30px;
        padding: 30px;
        align-content: center;
    }
</style>
