<template>
  <section class="dogs">
    <DogCard
      v-for="dog in dogs"
      :key="dog.name"
      :name="dog.name"
      :image="dog.image"
      :description="dog.description"
    />
  </section>
</template>

<script setup lang="ts">
import DogCard from './DogCard.vue';

const dogs = [
  {
    name: 'Dogue Alemão',
    image: new URL('../assets/images/alemao.jpg', import.meta.url).href,
    description: 'É um cachorro muito grande, amigável e elegante. Dogue alemão, também chamado de grande dinamarquês, porém apesar do nome, não sabe -se com clareza sua origem. Sua origem de cruzamentos de mordidas de touros (Bulldogs), e cães de caça,criado pela nobreza para o hábito de caçar ursos, veadados e lobos. Conhecida pelo seu porte gigante. Existe uma ramificação do Dogue alemão, O Arlequim é um Dogue Alemão branco com manchas escuras de vários tamanhos e formas, irregularmente distribuídas pelo corpo.'
  },
  {
    name: 'Schnauzer Gigante',
    image: new URL ('../assets/images/SchnauzerGigante.jpg', import.meta.url).href,
    description: 'Inteligente, ativo e muito protetor. O schnauzer gigante é uma raça de cão oriunda da Alemanha. Do cruzamentos entre Dogue Alemão e o Boiadeiro de Flandres. Feito para conduzir gado e pastorear ovelhas. Existe 3 tipos : o miniatura, o média (Standard) e o gigante.'
  },
  {
    name: 'Vira-Lata',
    image: new URL ('../assets/images/ViraLata.jpg', import.meta.url).href,
    description: 'Mistura de amor, resistência e companheirismo. Mais conhecidos nacionalmente como "caramelos",originam-se de cães europeus na época da colonização.Em 2020, foram realizadas petições para pôr a imagem do caramelo nas cédula de R$ 200. Sendo uma raça não "pura", há alguns casos que pode-se notar as misturas de raças e em outros casos não.'
  },
  {
    name: 'Dálmata',
    image: new URL ('../assets/images/dalmata.jpg', import.meta.url).href,
    description: 'Famoso pelos filmes, enérgico e muito sociável. Dálmata é uma raça de cães oriunda da região histórica da Dalmácia na Croácia. São cães que podem ter sua pelagem branca com manchas pretas ou marrons. Não sabe-se sua origem realmente; Existe uma pintura no egito antigo de um cão parecido com dalmata. Também acreditam que pode ser originária do Arlequim (Dogue Alemão) com cão pastor.'
  },
  {
    name: 'Bull Terrier',
    image: new URL ('../assets/images/Bull.jpg', import.meta.url).href,
    description: 'Cheio de energia, divertido e forte. O Bull Terrier Inglês surgiu na metade do século 19. O cruzamento entre o Old English terrier e o bulldog realizado pelo James Hinks, para realizar uma prática antiga (esportiva) Bull-baiting.'
  },
  {
    name: 'Pit Bull',
    image: new URL ('../assets/images/American pit bull terrier.jpg', import.meta.url).href,
    description: 'Leal, carinhoso e incompreendido. Conhecido como Pit Bull; Atualmente existem várias ramificações da raça, porém originário do cruzamento com o cruzamento do Bulldog Inglês com Old English terrier no século XIX, criado e usado especialmente para Bull-baiting. Por isso a fama de "cão matador".'
  }
];
</script>

<style>
    .dogs {
      display: grid;
      grid-template-columns: repeat(3, 350px);
      gap: 16px;
      margin-top: 42px;
    }
    .dog{
        border: solid 1px rgb(253, 226, 184);
    }
    img{
        width: 90%;
    }

      @media (max-width: 767px) {
        .dogs {
          grid-template-columns: 1fr;
        }
      }
      @media (min-width: 540px) and (max-width: 720px) {
        .dogs {
          margin: 12px;
        }
      }
      @media (min-width: 768px) and (max-width: 1023px) {
        .dogs {
          grid-template-columns: repeat(3, 220px);
        }
      }
      @media (min-width: 1024px) and (max-width: 1366px) {
        .dogs {
          margin-left: 24px;
          gap: 3px;
          grid-template-columns: repeat(3, 320px);
        }
      }
    
</style>