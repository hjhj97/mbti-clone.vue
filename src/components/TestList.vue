<template>
	<div>
		<div v-for="i in 10" :key="i">
			<TestItem @click-checkbox="onClickCheckbox" />
		</div>
		<div>
			<router-link to="" class="next-btn">Next</router-link>
		</div>
	</div>
</template>

<script>
	import { ref } from 'vue';
	import TestItem from './TestItem.vue';

	export default {
		components: { TestItem },
		setup() {
			const selected = ref(0);
			const onClickCheckbox = (data) => {
				selected.value = data;
			};
			return {
				selected,
				//
				onClickCheckbox,
			};
		},
	};
</script>

<style></style>
