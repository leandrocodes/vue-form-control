<template>
	<div id="app">
		<h1>Formulário Desafio</h1>
		<div class="conteudo">
			<form v-if="!enviado" class="painel">
				<div class="cabecalho">Formulário</div>

				<NomeCompleto v-model="nomecompleto"></NomeCompleto>
				<rotulo nome="Email">
					<input type="text" v-model="email">
				</rotulo>

				<rotulo nome="Senha">
					<input type="password" v-model="senha">
				</rotulo>

				<rotulo nome="Armazenar?">
					<input type="checkbox" v-model="dados">
				</rotulo>
				
				<button @click.prevent="enviar">enviar</button>
				
			</form>
			<div v-else class="painel">
				<div class="cabecalho">Resultado</div>
				<Rotulo nome="Nome">
					<span> {{nomecompleto.nome}} </span>
				</Rotulo>
				<Rotulo nome="Sobrenome">
					<span> {{nomecompleto.sobrenome}} </span>
				</Rotulo>
				<Rotulo nome="Email">
					<span> {{email}} </span>
				</Rotulo>
				<Rotulo nome="Senha">
					<span> {{senha}} </span>
				</Rotulo>
				<Rotulo nome="Armazenar">
					<span> {{armazenado}} </span>
				</Rotulo>
			</div>
		</div>
	</div>
</template>

<script>
import Rotulo from './components/Rotulo'
import NomeCompleto from './components/NomeCompleto'

export default {
	name: 'app',
	components: { Rotulo, NomeCompleto },
	methods:{
		enviar(){
			this.enviado = true
			
			if(this.dados === true)
				this.armazenado = 'Sim'
			 else
				this.armazenado = 'Não'
		}
	},
	data(){
		return{
			enviado: false,
			nomecompleto:{
				nome: '',
				sobrenome: ''
			},
			email:'',
			senha:'',
			dados: false,
			armazenado: ''
		}
	}
}
</script>

<style>

body {
	background-color: #ECECEC;
}

#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;

	display: flex;
	flex-direction: column;
}

.conteudo {
	display: flex;
}

.painel {
	flex: 1;
	background: #FFF;
	margin: 0px 10px;
	padding: 20px;
	border: 1px solid #AAA;
	border-radius: 5px;
}

.painel .cabecalho {
	width: 100%;
	background-color: #DDD;
	padding: 10px 0px;
	border-radius: 5px;
	font-size: 1.4rem;
}

#app form button {
	float: right;
	margin: 10px 0px;
	padding: 10px 20px;
	font-size: 1.4rem;
	border-radius: 5px;
	color: #FFF;
	background-color: #2196F3;
}

#app h1 {
	font-weight: 200;
	margin: 20px;
	padding: 0;
}

.mr-4 {
	margin-right: 40px;
}
</style>
