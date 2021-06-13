<template>
  <div id="app">
    <form @submit.prevent="submit" class="border border-gray-700 rounded">
      <div class="header">
        <div class="container flex justify-between p-4">
          <h1 class="text-white tracking-widest text-4xl w-4/5 pt-4">
            Formulário<br />
            para compra de<br /><strong>Pacote de Stickers</strong>
          </h1>
          <img src="~/assets/box_header.png" alt="Caixa" class="pb-12 w-5/12" />
        </div>
      </div>

      <div>
        <div class="container">
          <h2 class="py-4 text-2xl">Quais stickers?</h2>
          <p>
            <input type="checkbox" id="react" value="=react" v-model="option" />
            <label for="react">React</label>
          </p>

          <p>
            <input type="checkbox" id="vue" value="=vue" v-model="option" />
            <label for="vue">Vue</label>
          </p>

          <p>
            <input
              type="checkbox"
              id="angular"
              value="=angular"
              v-model="option"
            />
            <label for="angular">Angular</label>
          </p>
        </div>

        <div class="container py-6">
          <h2 class="py-4 text-2xl">Quantos Stickers de cada?</h2>
          <div class="flex justify-start space-x-6">
            <div class="cursor-pointer" @click.prevent="decrease">
              <button
                class="
                  text-white text-center
                  bg-blue-800
                  border border-black
                  rounded
                  w-10
                  h-10
                "
              >
                -
              </button>
            </div>
            <input
              type="text"
              name="quantidade"
              id="quantidade"
              :value="score"
              class="
                text-white text-center
                bg-blue-800
                border border-black
                rounded
                w-20
                h-10
              "
            />
            <div class="cursor-pointer" @click.prevent="increase">
              <button
                class="
                  text-white text-center
                  bg-blue-800
                  border border-black
                  rounded
                  w-10
                  h-10
                "
              >
                +
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="container">
        <h2 class="text-black text-2xl">Observações</h2>
        <textarea
          name="message"
          v-model="message"
          id="message"
          cols="45"
          rows="5"
          placeholder="Alguma dúvida? Recado?"
          style="resize: none"
          class="border border-gray-700 rounded w-full p-2 my-8 bg-pink-50"
        ></textarea>
      </div>

      <div class="container flex justify-end bg-pink-50 w-64 h-36 pr-4">
        <button
          type="submit"
          class="
            text-white text-center
            bg-blue-800
            border border-black
            rounded
            w-20
            h-10
            my-4
          "
        >
          enviar
        </button>
      </div>
    </form>
  </div>
</template>

<style scoped>
.header {
  min-height: 26vh;
  background: url("~/assets/background_header.png");
  background-size: cover;
  background-repeat: no-repeat;
}

.container {
  margin: 0 auto;
  width: 100%;
  max-width: 1000px;
}
</style>

<script>
export default {
  data() {
    return {
      option: [],
      score: 0,
      message: "",
    };
  },
  methods: {
    decrease() {
      this.score -= 1;
    },
    increase() {
      this.score += 1;
    },
    submit() {
      if (!this.option.length) alert("Você precisa selecionar um sticker");
      
      if (this.score === 0) alert("Você precisa selecionar a quantidade");
      if (this.score < 0) alert("Sua quantidade não pode ser negativa");
      if (!this.message) alert("Digite a sua observação");
      if (this.option.length && this.score > 0 && this.message) {
        alert("Você consegui :)!");
        this.option.length = 0;
        this.score = 0;
        this.message = "";
      }
    },
  },
};
</script>