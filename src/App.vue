<script setup>
import { ref } from 'vue';
const produtos = ref([
  {
    id: 1,
    titulo:'Chain of Iron:Vol.2',
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
]);
const carrinho = ref([]);

function adicionarAoCarrinho(produto) {
  const itemExistente = carrinho.value.find(p => p.id === produto.id);
  if (itemExistente) {
    itemExistente.quantidade++;
  } else {
    carrinho.value.push({ ...produto, quantidade: 1 });
  }
}

function removerDoCarrinho(produto) {
  const item = carrinho.value.find(p => p.id === produto.id);
  if (item) {
    item.quantidade--;
    if (item.quantidade <= 0) {
      const index = carrinho.value.indexOf(item);
      carrinho.value.splice(index, 1);
    }
  }
}
function aumentarQuantidade(produto) {
  const item = carrinho.value.find(p => p.id === produto.id);
  if (item) {
    item.quantidade++;
  } else {
    carrinho.value.push({ ...produto, quantidade: 1 }); 
  }
}


function totalCarrinho() {
  return carrinho.value.reduce((total, item) => total + item.preco * item.quantidade, 0).toFixed(2);
}

const mostrarcarrinho = ref(false);
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
          <i @click="mostrarcarrinho = !mostrarcarrinho" class="fa-solid fa-cart-shopping"></i>
          <span></span>
          <i class="fa-solid fa-heart"></i>
          <span></span>
          <i class="fa-solid fa-user"></i>
        </div>
      </div>
      <hr class="head">
    </header>
    <section class="inicio" v-if="!mostrarcarrinho">
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
    <section class="mais" v-if="!mostrarcarrinho">
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
    <section class="lancamentos" v-if="!mostrarcarrinho">
      <div class="titulo">
        <h1>Lançamentos</h1>
      </div>
      <ul>
        <li v-for="(item, index) of produtos" :key="index">
          <img :src="item.capa" :alt="item.titulo">
          <h2>{{ item.titulo }}</h2>
          <p>{{ item.autor }}</p>
          <p class="preco">R${{ item.preco }}</p>
          <button @click="adicionarAoCarrinho(item)">
            <i class="fa-solid fa-cart-shopping"></i>
            Adicionar ao Carrinho
          </button>
        </li>
      </ul>
    </section>

    <section class="carrinho" v-if="mostrarcarrinho">
      <h1>Carrinho</h1>
      <div class="classes">
      <ul>
        <li>
          <p>Título</p>
        </li>
        <li>
          Quantidade
        </li>
        <li>
          Subtotal
        </li>
      </ul>
      </div>  
      <hr>
      <ul v-if="carrinho.length > 0">
        <li v-for="item in carrinho" :key="item.id" class="livcontval">
          <div class="nlivro">
            <img :src="item.capa" alt="item.titulo">
            <div>
              <h3>{{ item.titulo }}</h3>
              <p>R$ {{ (item.preco * item.quantidade).toFixed(2) }}</p>
            </div>
          </div>
            <div class="button">
              <button @click="removerDoCarrinho(item)">
                -
              </button>
              <p> {{ item.quantidade }}</p>
              <button @click="aumentarQuantidade(item)">
                +
              </button>
            </div>
            <div>
            <p>R$00</p> 
            </div>         
        </li>
      </ul>
      <p v-else>O carrinho está vazio.</p>
    
      <button @click="mostrarcarrinho = false" class="voltar">Voltar para loja</button>
      <div class="botoes">
      <div>
      <p class="cupom">
        <input type="text" placeholder="Código do cupom">
        <button>
          Inserir Cupom
        </button>
      </p>
      </div>
      <div class="totalCompra">
      <ul class="cubo">
        <li>
          <h2>Total da Compra</h2>
        </li>
        <li>
          <p>Produtos: <span>R$ {{ totalCarrinho() }}</span></p>
        </li>
        <hr>
        <li>
          <p>Frete: <span>Grátis</span></p>
        </li>
        <hr>
        <li>
          <p>Total: <span>R$ {{ totalCarrinho() }}</span></p>
        </li>
        <li>
          <button class="irpagamento">
            Ir para o pagamento
          </button>
        </li>
      </ul>
      </div>
    </div>
    </section>
  </main> 
  <footer>
    <nav>
    <div class="sepelement">
      <div class="redes">
        <h2>IFbooks</h2>
        <i class="fa-brands fa-square-facebook"></i>
        <i class="fa-brands fa-square-instagram"></i>
        <i class="fa-brands fa-square-twitter"></i>
      </div>
      <div class="contato">
        <nav>
        <h2>Contato</h2>
        <div>
            <div class="loglegenda">
              <i class="fa-solid fa-phone"></i> 
              <p>+55 47 40045263</p>
            </div>
            <div class="loglegenda">
              <i class="fa-solid fa-clock"></i>
              <p>8h às 23h - Seg a Sex</p>
            </div>
            <div class="loglegenda">
              <i class="fa-solid fa-envelope"></i> 
              <p>contato@ifbooks.com</p>
            </div>
        </div>
        </nav>
    </div>  
      </div>
      <div class="cartao"> 
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
    margin: 20px 15px 0 0;
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
  /*------footer-----*/
  footer div.sepelement{
    display: flex;
    justify-content: space-between;
  }
  footer div.redes i{
    font-size: 1.6rem;
    margin: 10px 10px 0 0;
  }
  footer div.redes{
    padding: 40px 0 0 80px;
  }
  footer div.loglegenda i{
    margin-right: 9px;
  }
  footer div.cartao{
    display: flex;
    justify-content: flex-end;
    margin-right: 80px;
  }
  footer img{
    margin: 20px 7px 35px 7px;
  }
  footer div.loglegenda{
    display: flex;
    margin: 20px 40px 0 0 ;
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
    margin: 40px 2vw 2vw 2vw ;
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
  /*----final-footer----*/
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
  /*-----carrinho-----*/
  section.carrinho span{
    display: flex;
    justify-content: flex-end;
  }
  section.carrinho ul.cubo{
    border: 1px solid black;
    padding: 20px 10px 20px 10px;
  }
  section.carrinho h2{
    font-size: 1.4rem;
    margin: 3px 2px 30px 0;
  }
  section.carrinho button.irpagamento{
    background-color: #27AE60;
    color: white;
    padding: 15px 45px 15px 45px;
    margin: 10px 40px 10px 40px;
  }
  section.carrinho div.totalcompra{
    border: 1px solid black;
  }
  section.carrinho div.botoes {
    display: flex;
    justify-content: space-between;
  }
  section.carrinho p.cupom input{
    padding: 15px 60px 15px 15px;
  }
  section.carrinho p.cupom button{
    padding: 15px 40px 15px 40px;
    background-color: #27AE60;
    color: white;
    margin: 0 0 0 20px;
  }
  section.carrinho button.voltar{
    padding: 15px 40px 15px 40px;
    font-weight: bold;
    margin: 30px 0 50px 0;
  }
  section.carrinho div.button{
    display: flex;
    margin: 20px 0 0 0 ;
    height: 2vw;
  }
  section.carrinho ul li.livcontval{
    display: flex;
    justify-content: space-between;
    padding: 0 40px 0 0;
  }
  section.carrinho h1{
    margin: 2vw 0 2vw 0;
    font-size: 2rem;
    color: #27AE60;
    font-weight: bold;

  }
  section.carrinho{
    padding: 7vw;
  }
  section.carrinho div.classes ul{
    display: flex;
    justify-content: space-between;
    font-weight: bold;
    padding: 20px;
  }
  section.carrinho hr{
    border-bottom: #27AE60 1px;
  }
  section.carrinho img{
    width: 150px;
    height: auto;
    margin: 20px;
  }
  section.carrinho ul li div.nlivro{
    display: flex;
  }
  section.carrinho h3{
    font-size: 1.4rem;
    margin:40px 0 20px 0;
  }
</style>