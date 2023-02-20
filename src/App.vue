<template>
  <div class="landing-page">
    <div class="error" v-if="showError">
      <div class="container">
        <h2>Oops, algo deu errado!</h2>
        <p>
          Por favor tente novamente mais tarde ou contate o autor diretamente.
           <br /> <br />

          <a href="https://wa.me/5548991949721?text=Gostaria+de+saber+mais+sobre+o+livro" class="badge">Chamar no WhatsApp</a>
          <br /> <br /> <strong @click="showError = false">Fechar</strong>

        </p>
      </div>
    </div>
    <div class="book-header">
      <div class="book-cover">
        <div class="badge">Pré-venda do livro</div>
        <h1 class="book-title">{{ bookTitle }}</h1>
        <h2 class="book-subtitle">{{ bookSubtitle }}</h2>
      </div>
    </div>
    <div class="section">
      <div class="container">
        <div class="content">
          <h3>Para quem é esse livro?</h3>
        </div>
        <div class="content">
          <div>
            <p>Você provavelmente já escutou que <strong>é até 7x mais barato vender para quem já é seu cliente</strong> que conquistar um novo. </p>
            <p>Esse livro ensina estratégias práticas, com exemplos, de como atingir e automatizar esse resultado.</p>
            <h4>Esse livro é para você caso você responda SIM para alguma dessas perguntas:</h4>
            <ul>
              <li>O mesmo cliente pode comprar de você 2x ou mais por ano?</li>
              <li>Você gostaria de aumentar a frequência de compra dos seus clientes?</li>
              <li>Você gostaria de saber mensurar melhor o quão fiel é a sua base de clientes?</li>
              <li>Seus funcionários possuem tempo ocioso em momentos de baixo movimento que poderia ser utilizado para trabalhar sua base de clientes?</li>
            </ul>
            <h4>Esse livro <strong>com certeza</strong> é para você caso você não saiba alguma dessas respostas:</h4>
            <ul>
              <li>Quantos % do seu faturamento vem da sua base atual de clientes vs de novos clientes?</li>
              <li>Quanto custa para o seu negócio perder um cliente?</li>
              <li>Quando você considera que perdeu um cliente?</li>
              <li>A sua base de clientes ativos está crescendo ou diminuindo nos últimos meses?</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div class="book-header fixed">
      <div class="content">
        <div>
          <h1 class="book-title">{{ bookTitle }}
          </h1>
          <h2 class="book-subtitle">100% de garantia de satisfação ou seu dinheiro de volta.</h2>
        </div>
        <button class="badge" @click="buy" v-if="!loading"><strong>Comprar agora</strong> <br /> De <span class="strike">R$59,90</span> por <em>R$24,90</em></button>
        <button class="badge" v-else> Processando... </button>
      </div>
    </div>
    <div class="section">
      <div class="author-section">
        <div class="content">
          <h3> Sobre o Autor</h3>

        </div>
        <div class="content">
          <img class="author-photo" src="./assets/author.jpeg"/>
          <div class="description">
            <p class="author-description"><strong>Gabriel Chiminelli</strong>
              É empresário e engenheiro de software. Atualmente é CEO da Kevi uma startup que visa automatizar processos de retenção de clientes para empresas de diversos segmentos.
              Nos últimos 5 anos deu consultoria sobre retenção de clientes à dezenas de empresas de tamanhos, setores e operações variadas.
            </p>
          </div>
        </div>
        <div class="content">
          <ul>
            <li>Trouxe 27 mil de faturamento extra para uma pizzaria com uma mensagem automatizada na hora certa. A mensagem teve 14% de taxa de conversão e exigia 0 esforço.</li>
            <li>Ajudou uma loja de eletro-domésticos a faturar R$2.1 milhões de reais a mais no ano de 2022 com um mix de estratégias de retenção.</li>
            <li>Gerou 17 mil de faturamento com única campanha com custo de menos de R$500 para uma loja de roupas mirando em um segmento específico dos seus clientes.</li>
          </ul>
        </div>
      </div>
      <div class="container content">
        <h3>O que esse livro pode fazer por você?</h3>
      </div>
      <div class="container content">
        <div>
          <ul>
            <li>Te mostrar que fidelização e retenção de clientes vai muito além de dar descontos.</li>
            <li>Te ensinar 12 estratégias de fidelização que vão aumentar seu faturamento.</li>
            <li>Elevar seus conhecimentos como empresário e gestor fornecendo uma maneira analítica de olhar para sua base de clientes e avaliar seus resultados.</li>
          </ul>
        </div>
      </div>
      <div class="container content" style="justify-content: center">
        <button class="badge" @click="buy" v-if="!loading"><strong>Quero ser um empresário melhor</strong> <br /> De <span class="strike">R$59,90</span> por <em>R$24,90</em></button>
        <button class="badge" v-else> Processando... </button>
      </div>

    </div>
    <div class="book-description">
      <p>Em resumo, este livro é uma leitura obrigatória para qualquer empresário ou gerente de negócios que deseje melhorar a retenção de seus clientes e, consequentemente, aumentar seus lucros. Com as informações e estratégias que você aprenderá neste livro, você pode transformar sua empresa e ter uma base de clientes leal e satisfeita. Então, por que esperar?</p>
    </div>

    <div class="summary-section">
      <div class="content">
        <h3> Sumário e conteúdo</h3>
      </div>
      <div class="content">
        <ol>
          <li><strong>I. Introdução</strong></li>
          <li>A. Qual é o propósito deste livro?</li>
          <li>B. Quem é o público-alvo?</li>

          <li><strong>II. Retenção de Clientes:</strong></li>
          <li>A. O que é a retenção de clientes?</li>
          <li>B. Por que é crucial para o seu negócio?</li>

          <li><strong>III. Conhecendo sua base de clientes</strong></li>
          <li>A. Como coletar informações valiosas?</li>
          <li>B. O que é um cliente ativo?</li>
          <li>C. Como você sabe quando perdeu um cliente?</li>
          <li>D. Qual o tamanho da sua base de clientes ativos?</li>
          <li>E. Quanto custa perder um cliente?</li>
          <li>F. Como segmentar sua base de clientes para obter resultados máximos?</li>
          <li>G. Análise RFM, o que é e como realizar?</li>
          <li>H. Quem são seus clientes A na curva ABC?</li>

          <li><strong>IV. As métricas</strong></li>

          <li>A. Como medir a retenção de clientes?</li>
          <li>B. O que é faturamento de recompra?</li>
          <li>C. Qual sua taxa de aproveitamento da base de clientes?</li>
          <li>D. Entendendo a curva de retenção</li>
          <li>E. Analisando a sua taxa de recompra</li>
          <li>F. Qual o tempo médio entre compras?</li>
          <li>G. O valor do tempo de vida do cliente (LTV)</li>
          <li>H. CLV vs LTV, qual a diferença?</li>
          <li>I. Entendendo a análise de safras (Cohort)</li>

          <li><strong>V. Processos e Automatização</strong></li>
          <li>A. Por que é importante ter processos claros?</li>
          <li>B. Qual é o risco de não automatizar?</li>
          <li>C. Como utilizar sistemas e tecnlogia ao seu favor?</li>

          <li><strong>VII. Estratégias de Retenção de Clientes</strong></li>
          <li>A. Comunicar para ser lembrado</li>
          <li>B. Conhecer para encantar</li>
          <li>C. Entender para melhorar</li>
          <li>D. Responder para criar vínculo</li>
          <li>E. Recompensar lealdade</li>
          <li>F. Recompensar ticket alto</li>
          <li>G. Bonificar para reengajar</li>
          <li>H. Monitorar para se antecipar</li>
          <li>I. Conectar para crescer junto</li>
          <li>J. Educar para se diferenciar</li>
          <li>K. Atualizar para tranquilizar</li>

          <li><strong>VIII. Diagnóstico de Retenção</strong></li>
          <li><strong>IX. Conclusão</strong></li>
          <li>A. Os próximos passos</li>
          <li>B. Dicas de ferramentas</li>
          <li>C. Recomendações para melhorar sua retenção de clientes</li>
        </ol>
      </div>
      <div class="content" style="justify-content: center; align-items: center">
        <br /> <br />
        <button class="badge" @click="buy" v-if="!loading"><strong>Comprar agora</strong> <br /> De <span class="strike">R$59,90</span> por <em>R$24,90</em></button>
        <button class="badge" v-else> Processando... </button>
      </div>
    </div>
    <div class="contact-information">
      <div class="content">
        <h3>Contate o Autor</h3> <br />
        <a href="mailto:email@gabrielfelipe.com">email@gabrielfelipe.com</a> <br />
        <a href="https://wa.me/5548991949721?text=Gostaria+de+saber+mais+sobre+o+livro">(48) 99194-9721</a>
      </div>
    </div>
  </div>
</template>

<script>
import mixpanel from 'mixpanel-browser';
mixpanel.init('2366040f152887ad86bcc4da08663ac9', {debug: true});

export default {
  data() {
    return {
      loading: false,
      showError: false,
      bookTitle: 'Clientes de Alta Fidelidade',
      bookSubtitle: 'Descubra como manter seus clientes ativos, satisfeitos e recompensados para aumentar suas vendas.',
      bookDescription: 'In this book, John Doe explores the best practices and techniques for writing clean, efficient, and maintainable code. He covers topics such as code organization, testing, debugging, and more, using real-world examples and practical tips.',
      bookSummary: 'Whether you are just starting out as a software engineer or you are a seasoned veteran, this book is a must-read for anyone looking to write code that is both elegant and effective.'
    }
  },
  mounted() {
    mixpanel.track('Page view');
  },
  methods: {
    buy() {
      mixpanel.track('Click Buy');
      this.loading = true;
      window.setTimeout(() => {
        this.loading = false;
        this.showError = true;
      }, 2000)
    }
  }
}
</script>

<style lang="scss">

$main-color: #32A05F;
$light-main: #B9E3D0;
$dark-main: #2E7A4E;

$accent-color: #FFC107;
$light-accent: #FFE082;
$dark-accent: #FFA000;

@import url('https://fonts.googleapis.com/css2?family=Sarabun:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&family=Zilla+Slab:ital,wght@0,300;0,400;0,600;1,300;1,400;1,600&display=swap');


html, body {
  margin: 0;
  padding: 0;
  font-family: 'Sarabun', sans-serif;
  @media(max-width: 500px) {
    font-size: 14px;
  }
}

* {
  box-sizing: border-box;
}

.badge {
  background: $accent-color;
  border-radius: 10px;
  display: inline-block;
  padding: 10px;
  color: #333;
}
button {
  cursor: pointer;
  border: none;
  line-height: 1.5em;
  .strike {
    text-decoration: line-through;
  }
  em {
    font-size: 1.4em;
  }
}

ol {
  li {
    list-style: none;
    strong {
      margin-top: 20px;
      display: block;
    }
  }
}

ul {
  li {
    margin-top: 10px;
    font-size: 1.1rem;
  }
}

h3 {
  text-align: center;
  width:  100%;
  color: $dark-accent;
  font-size: 1.5rem;
}

h4 {
  text-align: center;
  width:  100%;
  color: $dark-accent;
  font-size: 1.1rem;
  strong {
    color: #333;
    font-weight: 900;
  }
}

.error {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  .container {
    max-width: 600px;
    height: auto;
    padding: 30px;
    border-radius: 30px;
    background: #fff;
  }
  &:before {
    content: "";
    display: block;
    position: absolute;
    background: rgba(0,0,0,0.7);
    width: 100%;
    height: 100%;
    z-index: -1;
  }
}

.content {
  padding: 0 10px;
  width: 100%;
  max-width: 700px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;
}
.landing-page {
  display: flex;
  flex-direction: column;
  align-items: stretch;

  .book-header {
    text-align: center;
    margin-bottom: 2rem;
    background: $main-color;
    color: #fff;
    position: relative; z-index: 1;
    .badge {
      margin-top: 20px;
    }
    h1 {
      margin-top: 0;
      margin-bottom: 0;
    }
    h2 {
      margin-top: 20px;
      margin-bottom: 40px;
    }
  }
  .book-header.fixed {
    position: sticky;
    top: 0;
    z-index: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 20px 0;
    left: 0;
    .content {
      padding:  0 10px;
      width: 100%;
      max-width: 700px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      h1, .badge {
        margin-top: 0;
        margin-bottom: 0;
      }
      h1 {
        padding: 0;
        line-height: 1em;
      }
      h1, h2 {
        text-align: left;
      }
      h2 {
        font-size: 1rem;
        margin: 10px 0 0;
      }
      @media(max-width: 500px) {
        flex-direction: column;
        align-items: flex-start;
        h2 {
          display: none;
        }
        .badge {
          margin-top: 20px;
          flex-basis: auto;
        }
      }
    }
    h1 {
      display: block;
      font-size: 2rem;
    }
    .badge {
      flex-basis: 250px;
      margin-left: 20px;
      display: block;
    }
  }

  .book-title {
    font-size: 3rem;
    font-weight: bold;
  }

  .book-subtitle {
    font-size: 1.5rem;
    font-weight: lighter;
  }

  .author-section {
    display: flex;
    align-items: center;
    margin-bottom: 2rem;
    flex-direction: column;

    .author-photo {
      width: 10rem;
      height: 10rem;
      border-radius: 50%;
      margin-right: 2rem;
    }

    .author-description, p, li {
      font-size: 1.3rem;
    }
  }

  .book-description {
    text-align: left;
    font-size: 1.5rem;
    max-width: 700px;
    margin: 0 auto;
    padding:  0 10px;

  }

  .cta-section {
    text-align: center;

    .cta-button {
      background-color: green;
      color: white;
      padding: 1rem 2rem;
      border-radius: 2rem;
      font-size: 1.5rem;
    }
  }

  .summary-section {
    font-size: 1.2rem;
    &:after {
      content: "";
      display: block;
      width: 100%;
      clear: both;
    }
  }
  .contact-information {
    .content {
      margin-top: 30px;
      flex-direction: column;
      margin-bottom: 150px;
      font-size: 1.5rem;
      text-align: center;

      h3 {
        margin-bottom: 0;
      }
    }
  }
}
</style>