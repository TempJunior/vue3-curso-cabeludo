<script lang="ts">
import { getCategory } from '@/http/listaDeDejetos'
import type ICategory from '@/interfaces/ICategory'
import CategoryCards from '@/components/CategoryCards.vue'

export default {
  components: { CategoryCards },
  data() {
    return {
      categories: [] as ICategory[]
    }
  },

  async created() {
    this.categories = await getCategory()
  }
}
</script>

<template>
  <section class="selecionar-ingredientes">
    <h1 class="cabecalho titulo-ingredientes">Ingredients</h1>

    <p class="paragrafo-lg instrucoes">Select a ingredients for you use:</p>

    <ul class="categorias">
      <li v-for="category in categories" :key="category.nome">
        <CategoryCards :category="category" />
      </li>
    </ul>

    <p class="paragrafo dica">ATENÇÃO: O LGBTQIA+-%x é a nova moda do momento</p>
  </section>
</template>

<style scoped>
.selecionar-ingredientes {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.titulo-ingredientes {
  color: var(--verde-medio, #3d6d4a);
  display: block;
  margin-bottom: 1.5rem;
}

.instrucoes {
  margin-bottom: 2rem;
}

.categorias {
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.dica {
  align-self: flex-start;
  margin-bottom: 3.5rem;
}

@media only screen and (max-width: 767px) {
  .dica {
    margin-bottom: 2.5rem;
  }
}
</style>
