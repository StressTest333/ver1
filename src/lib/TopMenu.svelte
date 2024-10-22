<script>
    let menu_items = ["Главное меню", "Товар", "Контакты"];
    /**
     * @prop {function} - ссылка на функцию, переключащую компоненты;
     */
    export let SelectComp; //ссылка на функцию, переключащую компоненты; находится в App
    let active_idx = 0; //индекс активного пункта меню -> переделан на props

    /**
     *@prop {number} - id выбранного пункта
     */
    export let act_idx; // = 0;
</script>

<div class="menu-bar">
    {#each menu_items as item, i}
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        
        <div class:active={act_idx == i}
            on:click={() => {
                SelectComp(i);
            }}>
           <ul>
            <li>{item}</li>
           </ul>
        </div>
    {/each}
</div>
<style>
    /*.menu-items {
        display: flex;
        justify-content: space-between;
    }
    .active {
        border-bottom: 2px solid yellowgreen;
        transition: 0.5s all ease-out;
    }

    .menu-items > div {
        padding: 10px 20px;
        cursor: pointer;
    }
    .menu-items > div:hover {
        background-color: #f0f0f0;
        color: rgb(37, 35, 35);
    }

    @media (max-width: 480px) {
        div.menu-items {
            flex-direction: column;
            align-items: center;
        }
    }
    body {
    height: 100vh;
    margin: 0;
    display: flex;
    justify-content: center;
  }*/
  
  .menu-bar {
    justify-content: center;
    border-radius: 25px;
    height: -webkit-fit-content;
    height: -moz-fit-content;
    height: fit-content;
    display: inline-flex;
    background-color: rgba(0, 0, 0, 0.4);
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
    align-items: center;
    padding: 0 10px;
    margin: 50px 0 0 0;
  }
  .menu-bar li {
    list-style: none;
    color: white;
    font-family: sans-serif;
    font-weight: bold;
    padding: 12px 16px;
    margin: 0 8px;
    position: relative;
    cursor: pointer;
    white-space: nowrap;
  }
  .menu-bar li::before {
    content: " ";
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    z-index: -1;
    transition: 0.2s;
    border-radius: 25px;
  }
  .menu-bar li:hover {
    color: black;
  }
  .menu-bar li:hover::before {
    background: linear-gradient(to bottom, #e8edec, #d2d1d3);
    box-shadow: 0px 3px 20px 0px black;
    transform: scale(1.2);
  }
</style>
