<script setup>

</script>

<template>
<main>
  <header>
    <div class="topo">
      <div>
        <p>IFbooks</p>
        </div>
        <span class="barra"></span>
        <div>
        <p class="apreco">Apreço a <br>leitura</p>
      </div>
      <div class="pesquisa">
        <input type="text" placeholder="Pesquisar">
        <i class="fa-solid fa-magnifying-glass"></i>
      </div>
    <div class="itens">
        <nav>
            <a href="#">Termos</a>
        
            <a href="#">Devoluções</a>
        
            <a href="#">Envio</a>
          
            <a href="#">Equipe</a>
        </nav>
    </div>
    <div class="icons">
      <i class="fa-solid fa-cart-shopping"></i>
      <span></span>
      <i class="fa-solid fa-heart"></i>
      <span></span>
      <i class="fa-solid fa-user"></i>
    </div>
    </div>
  </header>
  <section class="inico">

  <div class="pagina1">
        <div class="mudar">
          <p>Autor de Abril</p>
          <h1>Eric-Emanuel Schmitt </h1>
          <p>Eric-Emmanuel Schmitt has been awarded more than 20 <br> literary prizes and distinctions, and in 2001 he received the <br> title of Chevalier des Arts et des Lettres. His books have been <br> translated into over 40 languages.</p>
          <button>Acessar página do livro</button>
        </div>  
        <div>
          <img src="/public/imagens/book.png" alt="book.png" style="display: block; margin: ;">
        </div>
  </div> 
  </section>
  <section class="mais">
        <i class="fa-solid fa-truck"></i>
        Frete grátis para SC
        <i class="fa-solid fa-star"></i>
        Livros recomendados
        <i class="fa-solid fa-book-open"></i>
        Mais vendidos
  </section>
  <section class="lancamentos">
    <div class="cima">
      <div>
        <img src="/public/imagens/livro1.png" alt="livro1.png">
        <h2>Chain of Iron: Volume 2</h2>
        <p>Cassandra Clare</p>
        <p>R$23.24</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      <div>
        <img src="/public/imagens/livro2.png" alt="livro2.png">
        <h2>Chain of Thorns</h2>
        <p>Cassandra Clare</p>
        <p>R$23.24</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      
      <div>
        <img src="/public/imagens/livro3.png" alt="livro3.png">
        <h2>City of Fallen Angels</h2>
        <p>Cassandra Clare</p>
        <p>R$13.94</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      <div>
        <img src="/public/imagens/livro4.png" alt="livro4.png">
        <h2>Nona the Ninth</h2>
        <p>Cassandra Clare</p>
        <p>R$16.84</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
    </div>
    <div class="baixo">
      <div>
        <img src="/public/imagens/livro5.png" alt="livro5.png">
        <h2>Harlem Shuffle</h2>
        <p>Colson Whitehead</p>
        <p>R$26.92</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      <div>
        <img src="/public/imagens/livro6.png" alt="livro6.png">
        <h2>Two Old Women</h2>
        <p>Two Old Women</p>
        <p>R$13.95</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      <div>
        <img src="/public/imagens/livro7.png" alt="livro7.png">
        <h2>Carrie Soto Is Back</h2>
        <p>Taylor Jenkins Reid</p>
        <p>R$26.04</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
      <div>
        <img src="/public/imagens/livro8.png" alt="livro8.png">
        <h2>Book Lovers</h2>
        <p>Emily Henry</p>
        <p>R$15.81</p> <i class="fa-regular fa-heart"></i>
        <button><i class="fa-solid fa-cart-shopping"></i>comprar</button>
      </div>
    </div>
  </section>
</main> 
<footer>
  <div>
    <h2>IFbooks</h2>
    <i class="fa-brands fa-square-facebook"></i>
    <i class="fa-brands fa-square-instagram"></i>
    <i class="fa-brands fa-square-twitter"></i>
  </div>
  <div>
    <h2>Contato</h2>
    <i class="fa-solid fa-phone"></i> <p>+55 47 40045263</p>
    <i class="fa-solid fa-clock"></i> <p>8h às 23h - Seg a Sex</p>
    <i class="fa-solid fa-envelope"></i> <p>contato@ifbooks.com</p>
    <img src="/public/imagens/paypal.png" alt="paypal.png">
    <img src="/public/imagens/MasterCard.png" alt="MasterCard.png">
    <img src="/public/imagens/VISA.png" alt="VISA.png">
  </div>
  <div>
    &copy; Alguns direitos reservados. IFbooks 2025. 
  </div>
</footer>
</template>

<style scoped>
  div.pagina1 div.mudar h1{
    font-size: 2.5rem;
  }
  svg{
    width: 20px;
  }
  p.apreco{
    color:yellowgreen;
  }
  div.itens nav a{
    text-decoration: none;
    margin: 20px;
    color: black;
  }
  div.icons i{
    margin: 0 10px 10px 0 ;
  }
  div.icons span{
    border-left: solid 1px;
    margin: 0 10px 20px 0;
  }
  header span{
    border-left: solid 1px;
  }
  section.lancamentos div.cima{
    display: flex;
    padding: 5vw;
    justify-content: space-between;
  }
  section.lancamentos div.baixo{
    display: flex;
    margin: 5vw;
    justify-content: space-between;
  }
  section.lacamentos div.cima div h2{
    font-size: 1.4rem;
  }
</style>
