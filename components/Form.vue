<template>
  <div>
    <header class="header">
      <div class="container flex justify-between p-4">
        <h1 class="text-white tracking-widest text-4xl w-4/5 pt-4">
          Formulário<br />
          para compra de<br /><strong>Pacote de Stickers</strong>
        </h1>
        <img src="~/assets/box_header.png" alt="Caixa" class="pb-12 w-5/12" />
      </div>
    </header>

    <section>
      <div class="container">
        <h2 class="py-4 text-2xl">Quais stickers?</h2>
        <p>
          <input type="checkbox" id="queroReact" value="=Stickers1" v-model="opcao"/>
          <label for="aceitaTermos">React</label>
        </p>

		<p>
          <input type="checkbox" id="queroVue" value="=Stickers2" v-model="opcao" />
          <label for="aceitaTermos">Vue</label>
        </p>

		<p>
          <input type="checkbox" id="queroAngular" value="=Stickers3" v-model="opcao" />
          <label for="aceitaTermos">Angular</label>
        </p>
      </div>

	  <div class="container py-6">
        <h2 class="py-4 text-2xl">Quantos Stickers de cada?</h2>
		<div class="flex justify-start space-x-6">
			<button class="text-white text-center bg-blue-800 border border-black rounded w-10 h-10">-</button>
			<button class="text-white text-center bg-blue-800 border border-black rounded w-20 h-10">100</button>
			<button class="text-white text-center bg-blue-800 border border-black rounded w-10 h-10">+</button>
		</div>
	  </div>


      <div class="container">
        <p class="text-black text-2xl">Observações</p>
        <p class="whitespace-pre-line">{{ message }}</p>
        <br />
        <textarea class="border border-gray-700 rounded w-full p-2 my-8 bg-pink-50" v-model="message" placeholder="Alguma dúvida? Recado?"></textarea>
      </div>

	  <div class="container flex justify-end bg-pink-50 w-64 h-36 pr-4">
		  <button class="text-white text-center bg-blue-800 border border-black rounded w-20 h-10 my-4">enviar</button>
	  </div>

    </section>


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
	data(){
		return{
			

		}
	}
}
</script>

