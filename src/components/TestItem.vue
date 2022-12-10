<template>
	<div>
		<div>
			<h1>Question {{ i }}</h1>
			<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat, omnis.</p>
		</div>
		<div class="ans-container">
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === -3 }" @click="onClickCheckbox(-3)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === -2 }" @click="onClickCheckbox(-2)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === -1 }" @click="onClickCheckbox(-1)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === 0 }" @click="onClickCheckbox(0)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === 1 }" @click="onClickCheckbox(1)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === 2 }" @click="onClickCheckbox(2)"></span>
			</div>
			<div class="ans-item">
				<p>모름</p>
				<span class="checkbox" :class="{ on: check === 3 }" @click="onClickCheckbox(3)"></span>
			</div>
		</div>
	</div>
</template>

<script>
	import { ref } from 'vue';

	export default {
		emits: ['click-checkbox'],
		setup(props, { emit }) {
			const check = ref();

			const onClickCheckbox = (val) => {
				check.value = val;
				emit('click-checkbox', val);
			};
			return {
				check,
				//
				onClickCheckbox,
			};
		},
	};
</script>

<style scoped>
	.ans-container {
		display: flex;
	}
	.ans-container .ans-item {
		display: flex;
		flex-direction: column;
	}
	.ans-container .ans-item .checkbox {
		width: 2rem;
		height: 2rem;
		border-radius: 50%;
		background: #eee;
	}
	.ans-container .ans-item .checkbox.on {
		background: orange;
	}
</style>
