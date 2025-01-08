<script setup lang="ts">
import { ref } from "vue";

const frontList = [{
	name: 'Python',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/640px-Python-logo-notext.svg.png'
},
{
	name: 'JavaScript',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/1200px-Unofficial_JavaScript_logo_2.svg.png'
},
{
	name: 'TypeScript',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png'
},
{
	name: 'Kotlin',
	image: 'https://itproger.com/img/tests/1567591805.svg'
},
{
	name: 'React',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/React.svg/1200px-React.svg.png'
},
{
	name: 'Ionic',
	image: 'https://www.wonderpush.com/wp-content/uploads/2019/09/ionic.png'
},
{
	name: 'Vue',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png'
},

{
	name: 'Vite',
	image: 'https://vitejs.dev/logo-with-shadow.png'
}]

const backList = [{
	name: 'Java',
	image: 'https://education.oracle.com/file/general/p-80-java.png'
},
{
	name: 'Python',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/640px-Python-logo-notext.svg.png'
},
{
	name: 'Rust',
	image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Rust_programming_language_black_logo.svg/2048px-Rust_programming_language_black_logo.svg.png'
},
{
	name: 'Docker',
	image: 'https://www.docker.com/wp-content/uploads/2023/05/symbol_blue-docker-logo.png'
},
{
	name: 'Node.js',
	image: 'https://miro.medium.com/v2/resize:fit:800/1*v2vdfKqD4MtmTSgNP0o5cg.png'
},
{
	name: 'Vitest',
	image: 'https://vitest.dev/logo-shadow.svg'
}]

const dataList = [{
	name: 'PostgreSQL',
	image: 'https://upload.wikimedia.org/wikipedia/commons/2/29/Postgresql_elephant.svg'
},
{
	name: 'Firebase',
	image: 'https://www.npmjs.com/npm-avatar/eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdmF0YXJVUkwiOiJodHRwczovL3MuZ3JhdmF0YXIuY29tL2F2YXRhci80ODk2NWRhMmM3NTM5MGU4YzQ4NjA1OGMyODJiMzVjZD9zaXplPTQ5NiZkZWZhdWx0PXJldHJvIn0.6DscqHBxt8ExFrTU-ok22ZG5PhY4hYWjHduL7B80klw'
}]

const nameTech = ref<string>("front");

function changeValue(type: string) {
  nameTech.value = type;
}
</script>

<template>
	<div class="home-style">
	  <div class="grid-tech-type">
		<div
		  class="tech-type-name"
		  :class="{ selected: nameTech === 'front' }"
		  @click="changeValue('front')"
		>
		  Front-end
		</div>
		<div
		  class="tech-type-name"
		  :class="{ selected: nameTech === 'back' }"
		  @click="changeValue('back')"
		>
		  Back-end
		</div>
		<div
		  class="tech-type-name"
		  :class="{ selected: nameTech === 'data' }"
		  @click="changeValue('data')"
		>
		  Database
		</div>
	  </div>
	  <div v-if="nameTech === 'front'" class="techs-grid">
		<div v-for="tech in frontList" :key="tech.name" class="tech-item">
		  <div class="image-display">
			<img :src="tech.image" :alt="tech.name" width="110" class="tech-image" />
			<h2 class="tech-name">{{ tech.name }}</h2>
		  </div>
		</div>
	  </div>
	  <div v-if="nameTech === 'back'" class="techs-grid">
		<div v-for="tech in backList" :key="tech.name" class="tech-item">
			<div class="image-display">
			  <img :src="tech.image" :alt="tech.name" width="110" class="tech-image" />
			  <h2 class="tech-name">{{ tech.name }}</h2>
			</div>
		  </div>
	  </div>
	  <div v-if="nameTech === 'data'" class="techs-grid">
		<div v-for="tech in dataList" :key="tech.name" class="tech-item">
			<div class="image-display">
			  <img :src="tech.image" :alt="tech.name" width="110" class="tech-image" />
			  <h2 class="tech-name">{{ tech.name }}</h2>
			</div>
		  </div>
	  </div>
	</div>
  </template>
  
  <style scoped>
  .home-style {
	background-color: #fafafa;
	display: flex;
	flex-direction: column;
	width: 100%;
	height: 100%;
	color: #000;
  }
  
  .grid-tech-type {
	display: grid;
	grid-template-columns: auto auto auto;
	width: 100%;
  }
  
  .tech-type-name {
	border: 1px solid #000;
	font-size: 20px;
	padding: 5px;
	display: flex;
	justify-content: center;
	align-items: center;
	cursor: pointer;
	background-color: #fff;
	transition: background-color 0.3s ease;
  }
  
  .tech-type-name:hover {
	background-color: #f0f0f0;
  }
  
  .tech-type-name.selected {
	background-color: #8fa6bc;
	color: #fff;
  }
  
  .techs-grid {
	display: grid;
	gap: 10px;
	grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
	padding: 20px;
	max-height: 100%;
	overflow-y: auto;
  }
  
  .image-display {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	box-sizing: border-box;
	text-align: center;
  }
  
  .tech-image {
	display: block;
	width: 110px;
	height: auto;
	transition: transform 0.3s ease;
  }
  
  .image-display:hover .tech-image {
	transform: scale(1.20);
  }
  
  .tech-name {
	margin-top: 10px;
	font-size: 1rem;
	color: #000;
	opacity: 0;
	transition: opacity 0.3s ease;
  }
  
  .image-display:hover .tech-name {
	opacity: 1;
  }
  </style>
  