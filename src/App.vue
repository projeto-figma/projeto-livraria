<script setup>
/*davi dospassos */
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
        <p class="ifbook">IFbooks</p>
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
    <hr class="head">
  </header>
  <section class="inicio">
  <div class="pagina1">
        <div class="mudar">
          <p class="moldura">Autor de Abril</p>
          <h1>Eric-Emanuel Schmitt </h1>
          <p class="texto">Eric-Emmanuel Schmitt has been awarded more than 20 <br> literary prizes and distinctions, and in 2001 he received the <br> title of Chevalier des Arts et des Lettres. His books have been <br> translated into over 40 languages.</p>
          <button>Acessar página do livro</button>
        </div>  
        <div class="imagembook">
          <img src="/public/imagens/book.png" alt="book.png" style="display: block;">
        </div>
  </div> 
  </section>
  <section class="mais">
    <hr class="linha">
    <div class="itenss">
      <div class="frete">
        <i class="fa-solid fa-truck"></i>
        Frete grátis para SC
      </div>
      <hr class="coluna">
      <div class="frete">
        <i class="fa-solid fa-star"></i>
        Livros recomendados
      </div>
      <hr class="coluna">
      <div class="frete">
        <i class="fa-solid fa-book-open"></i>
        Mais vendidos
      </div>
    </div>
    <hr class="linha">
  </section>
  <section class="lancamentos">
    <div class="titulo">
      <h1>Lançamentos</h1>
    </div>
    <ul>
      <li v-for="(item, index) of produtos" :key="index">
        <img :src="item.capa" :alt="item.titulo">
        <h2>{{ item.titulo }}</h2>
        <p>{{ item.autor }}</p>
        <p class="preco">R${{ item.preco }}</p>
        <button>
          <i class="fa-solid fa-cart-shopping"></i>
          Comprar 
        </button>
      </li>
    </ul>
  </section>
</main> 
<footer>
  <nav>
    <div class="redes">
      <h2>IFbooks</h2>
      <i class="fa-brands fa-square-facebook"></i>
      <i class="fa-brands fa-square-instagram"></i>
      <i class="fa-brands fa-square-twitter"></i>
    </div>
    <div class="contato">
      <h2>Contato</h2>
      <nav>
        <i class="fa-solid fa-phone"></i> 
        <p>+55 47 40045263</p>
        <i class="fa-solid fa-clock"></i> 
        <p>8h às 23h - Seg a Sex</p>
        <i class="fa-solid fa-envelope"></i> 
        <p>contato@ifbooks.com</p>
      </nav>
      <img src="/public/imagens/paypal.png" alt="paypal.png">
      <img src="/public/imagens/MasterCard.png" alt="MasterCard.png">
      <img src="/public/imagens/VISA.png" alt="VISA.png">
    </div>
    <hr>
    <div class="copy">
      <p>&copy; Alguns direitos reservados. IFbooks 2025. </p>
    </div>
  </nav>
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
    font-size: 3rem;
    font-weight: bold;
    margin: 2vw 0 1vw 0;
  }
  div.pagina1 div.mudar p.texto{
    margin: 10px 0 20px 0;
  }
  div.pagina1 div.mudar p.moldura{
    border: solid 1px;
    color: #27AE60;
    width: 20%;
    padding: 15px 10px 15px 10px;
  }
  div.pagina1 div.mudar button{
    background-color: #27AE60;
    color: white;
    font-size: 1.2rem;
    padding: 15px 15px 15px 15px;
    margin: 1vw 0 0 0;
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
  section.lancamentos div h1 {
    font-size: 2rem;
    margin: 1vw 0 3vw 0 ;
    font-weight: bold;
  }
  section.lancamentos ul{
    display: flex;
    flex-wrap: wrap;
  }
  section.lancamentos ul button{
    color: #27AE60;
  }
  section.lancamentos ul li{
    width: 22%;
    margin: 0 1vw;
  }
  section.lancamentos ul li img{
    width: 100% ;
  }
  section.lancamentos ul li button{
    background-color: #27AE60;
    color: white;
    width: 100%;
    margin: 0 0 70px 0;
    font-size: 1.2rem;
    height: 9%;
  }
  section.lancamentos ul li h2{
    font-size: 1.7rem;
    margin: 20px 0 20px 0;
  }
  section.lancamentos ul li p{
    font-size: 1.2rem;
    margin: 0 0 20px 0 ;
    color: #4F4C57;
  }
  section.lancamentos ul li p.preco{
    color: #382C2C;
    font-weight: bold;
  }
  section.mais div.itenss {
    display: flex;
    justify-content: space-between;
    width: 70%;
  }
  section.mais hr{
    border-bottom: solid 10px;
  }
  section.mais{
    margin: 30px;
  }
  header div.icons{
    color: #27AE60;
  }
  header div.itens nav a{
    color: #7B7881;
  }
  footer {
    background-color: #27AE60;
  }
  footer nav div.ifbooks h2{
    color: white;
  }
  footer nav div.contato h2{
    color: white;
  }
  footer nav div.contato {
    color: #FFFFFFCC;
    opacity: 0.8;
    display: flex;
    justify-content: right;
  }
  footer nav div.redes {
    color: white;
  }
  footer hr{
    border-top: 2px;
    color: #FFFFFF;
    margin: 0 0 10px 0;
  }
  footer div.copy{
    display: flex;
    justify-content: center;
    color: #FFFFFF99;
    opacity: 0.6;
  }
  footer div.copy p {
    margin: 30px;
  }
  section.inicio .pagina1 {
    display: flex;
    justify-content: space-between;
    margin: 10px 10vw 10px 0;
  }
  div.pagina1 div.mudar{
    margin: 6vw 10vw 0 8vw;
  }
  div.pagina1 h1{
    font-size: 3rem;
  }
  header div.topo{
   margin: 20px 20px 20px 20px;
  }
  header p.ifbook{
    margin: 5px 5px 0 5vw ;
  }
  header .apreco{
    margin: 0 5vw 0 5px;
  }
  header hr.head{
    color: #27AE60;
  }
  header div.itens{
    margin: 6px 2vw 0 8vw;
  }
  header .icons{
    margin: 6px 2vw 0 10vw;
  }
  header span{
    margin: 0 5px 0 5px;
  }
  .pesquisa input{
    border: none;
    background: #F1F1F1;
    padding: 10px 10vw 10px 20px;
  }
  .pesquisa i{
    transform: translateX(-30px);
  }
  section.mais .linha{
    border-bottom: solid 1px;
    color: #27AE60;
    margin: 30px;
  }
  section.mais div.frete{
   margin: 5px 0 0 0 ;
   font-size: 1.8rem;
  }
  section.mais div.itenss{
    margin: 0 0 0 13vw;
  }

</style>
