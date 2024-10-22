<script>
// @ts-nocheck

  import Comp1 from "./lib/Comp1.svelte";
  import Comp2 from "./lib/Comp2.svelte";
  import Comp3 from "./lib/Comp3.svelte";
  import TopMenu from "./lib/TopMenu.svelte";

  import DetectMessage from "./lib/Detector.svelte";

  //Массив объектов, содержащий ссылки на 3 компонента
  const options = [
    { component: Comp1 },
    { component: Comp2 },
    { component: Comp3 },
  ];

  let selected = options[0]; //компонент по умолчанию
  let active_item = 0;

  /**
   * @param {number} idcomp
   */
  function SelectComp(idcomp) {
    //Функция вызывается из верхнего меню и определяет
    //выбранный пользователем компонент
    selected = options[idcomp];
    active_item = idcomp;
  }

  let current_message;

  /**
   * @param {string} mess - текст сообщения
   */
  function SendMessage(mess) {
    //функция вызывается из компонентов Comp1, Comp2 и Comp3
    //Каждый из них формирует свое сообщение, к-е передается
    //через аргумент mess  и определяет переменную current_message.
    //Current_message передается в компонент Detector через prop messagefrom
    current_message = mess;
    clicked = true;
    setTimeout(() => {
      clicked = false;
    }, 200);
  }

  let clicked = false;
  import Fa from 'svelte-fa'
  import { faFlag } from '@fortawesome/free-solid-svg-icons'
  import { faGithub } from '@fortawesome/free-brands-svg-icons';
</script>

<main>
  <div class="holy-grail">
    <header>
      <nav>
        <TopMenu {SelectComp} act_idx={active_item} />
      </nav>
    </header>

    <div class="container">
      <div class="left-sidebar">
        <h2 align="center">Новости</h2>
        <h3 align="center">Суперлуна</h3>
        <p>Суперлуну 17 октября нашим читателям не помешали разглядеть даже огни большого города. 
          Она кажется большой и яркой из-за того, что находится на предельно близком расстоянии от Земли 357 364 километра. Максимальное приближение полной луны называют суперлунием или суперполнолунием.
          Самые впечатляющие моменты — первый час после заката солнца или перед рассветом. В эти периоды Луна располагается низко у горизонта и выглядит огромной.
          В народе это полнолуние называли охотничьей луной. Считалось, что в это время в поля выходят дикие звери, на которых пора охотиться.</p>
      </div>

      <div class="main-content">
        <h1>Основной контент</h1>
        <div style="color:green">
          <!-- Динамические компоненты -->
          <svelte:component
            this={selected.component}
            app_function={SendMessage}/>
        </div>
        <Fa icon={faGithub}  pull="left" size="5x" spin />
      </div>
      <div class="right-sidebar">
        <h3>Победители викторины:</h3>
        <uv>
          <li>Петров Константин Викторович</li>
          <li>Сидоров Семён Анатольевич</li>
          <li>Семейкина Ирина Васильевна</li>
        </uv> 
      </div>
    </div>
    <footer>
      <p>Создатель StressTest</p>
    </footer>
  </div>
</main>

<style>
  :root {
    font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
    line-height: 1.5;
    font-weight: 400;
  }

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  .holy-grail {
    display: flex;
    flex-direction: column;
    min-height: 100vh;

  }

  header {
    /* background-color: #333; */
    color: #fff;
    padding: 1em;
    text-align: center;
  }

  .container {
    display: flex;
    flex-wrap: wrap;
    padding: 20px;
    flex: 1;
  }

  .left-sidebar {
    flex: 2;
    max-width: 300px;
    margin-right: 20px;
    background-color: #f7f7f7;
    padding: 20px;
  }

  .main-content {
    flex: 3;
    padding: 20px;
  }

  .right-sidebar {
    flex: 2;
    max-width: 300px;
    margin-left: 20px;
    background-color: #f7f7f7;
    padding: 20px;
  }

  footer {
    background-color: #333;
    color: #fff;
    padding: 1em;
    text-align: center;
    height: 50px;
    margin-top: auto;
  }

  @media (max-width: 1200px) {
    .left-sidebar,
    .right-sidebar {
      flex: 0 0 200px;
    }
  }

  @media (max-width: 992px) {
    .left-sidebar,
    .right-sidebar {
      flex: 0 0 150px;
    }
  }

  @media (max-width: 768px) {
    .container {
      flex-direction: column;
    }
    .left-sidebar,
    .right-sidebar {
      max-width: 100%;
      margin: 20px 0;
    }
    .main-content {
      flex: 1;
    }
  }
</style>
