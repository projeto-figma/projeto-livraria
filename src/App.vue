<script setup>
import { ref } from 'vue';
const produtos = ref([
    {
        id: 1,
        titulo: 'Chain of Iron: Volume 2',
        autor: 'Cassandra Clare',
        preco: 23.24,
        capa: "public/imagens/livro1.png",
    },
    {
        id: 2,
        titulo: 'Chain of Thorns',
        autor: 'Cassandra Clare',
        preco: 23.24,
        capa: "public/imagens/livro2.png",
    },
    {
        id: 3,
        titulo: 'City of Fallen Angels',
        autor: 'Cassandra Clare',
        preco: 13.94,
        capa: "public/imagens/livro3.png",
    },
    {
        id: 4,
        titulo: 'Nona the Ninth',
        autor: 'Cassandra Clare',
        preco: 16.84,
        capa: "public/imagens/livro4.png",
    },
    {
        id: 5,
        titulo: 'Harlem Shuffle',
        autor: 'Colson Whitehead',
        preco: 26.92,
        capa: "public/imagens/livro5.png",
    },
    {
        id: 6,
        titulo: 'Two Old Women',
        autor: 'Velma Wallis', 
        preco: 13.95,
        capa: "public/imagens/livro6.png",
    },
    {
        id: 7,
        titulo: 'Carrie Soto Is Back',
        autor: 'Taylor Jenkins Reid',
        preco: 26.04,
        capa: "public/imagens/livro7.png",
    },
    {
        id: 8,
        titulo: 'Book Lovers',
        autor: 'Emily Henry',
        preco: 15.81,
        capa: "public/imagens/livro8.png",
    },
])

</script>

<template>
<main>
  <header>
    <div class="topo">
      <div class="if">
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
    <hr>
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
          <img src="/public/imagens/book.png" alt="book.png" style="display: block;">
        </div>
  </div> 
  </section>
  <section class="mais">
    <div class="itenss">
      <div class="frete">
        <i class="fa-solid fa-truck"></i>
        Frete grátis para SC
      </div>
      <hr>
      <div>
        <i class="fa-solid fa-star"></i>
        Livros recomendados
      </div>
      <hr>
      <div>
        <i class="fa-solid fa-book-open"></i>
        Mais vendidos
      </div>
    </div>
  </section>
  <section class="lancamentos">
    <div>
      <h1>Lançamentos</h1>
    </div>
    <ul>
      <li v-for="(item, index) of produtos" :key="index">
        <img :src="item.capa" :alt="item.titulo">
        <h2>{{ item.titulo }}</h2>
        <p>{{ item.autor }}</p>
        <span>{{ item.preco }}</span>
        <button>
          <i class="fa-solid fa-cart-shopping"></i>
          Comprar 
        </button>
      </li>
    </ul>
  </section>
</main> 
<footer>
  <div class="ifbooks">
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
  div.pagina1{
    display: flex;
}
header div.topo{
    display: flex;
}
  div.pagina1 div.mudar h1{
    font-size: 2.5rem;
  }
  svg{
    width: 20px;
  }
  p.apreco{
    color: #27AE6099;
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
  section.lancamentos{
    padding: 0 8vw;
  }
  section.lancamentos ul{
    display: flex;
    flex-wrap: wrap;
  }
  section.lancamentos ul li{
    width: 22%;
    margin: 0 1vw;
  }
  section.lancamentos ul li img{
    width: 100% ;
  }
  section.mais div.itenss {
    display: flex;
    justify-content: space-between;
    width: 70%;
  }
  section.mais hr{
    border-bottom: solid 20px;
  }
  section.mais{
    margin: 30px;
  }
  section
  header div.icons{
    color: #27AE60;
  }
  header div.itens nav a{
    color: #7B7881;
  }
  header hr{
    color: #27AE60;
  }
  footer{
    background-color: #27AE60;
    color: white;
  }
  footer div.ifbooks h2{
    font-size: 0.9rem;
  }


</style>
