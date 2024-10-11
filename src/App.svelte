<div class="card"> 
    <div class ='header'>
        <h1>Заголовок</h1>
    </div>

    <div class ='content'>
      <p>Содержание</p>
        <p>123</p>
    </div>

    <div class ='footer'>Подвал</div>
  </div>

<style>
  .content{
    border:1px solid rgb(95, 23, 190);
    height: -webkit-fill-available;
    height:100%;
}
  .card {
    width: 50%;
    display: flex;
    flex-flow: column;
    background:#dde;
    height: 300px;
    justify-content: space-between;
    background:#dde;
    height: 300px;
    text-align: center;
  }
  .footer{
    background: #8f7c8c;;
  }
  .header{
    background: #8f7c8c;;
  }

  .content, .footer, .header{
    padding:5px;
  }
</style>
