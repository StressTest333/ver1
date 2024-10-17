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

<div class="menu-items">
    {#each menu_items as item, i}
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div
            class:active={act_idx == i}
            on:click={() => {
                SelectComp(i);
            }}
        >
            {item}
        </div>
    {/each}
</div>

<style>
    .menu-items {
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
</style>
