<template>
	<div>
		<Test />
	</div>
</template>

<script lang="ts">
import { defineComponent, h } from 'vue';

const Test = defineComponent({
	data() {
		return {
			text: 'default text',
		};
	},

	// Does not work!
	beforeMount() {
		this.text = 'component is about to be mounted';
	},

	// Works!
	/*
	mounted() {
		this.text = 'component mounted';
	},
  */

	render() {
		return h('span', {
			innerHTML: this.text,
		});
	},
});

export default {
	components: {
		Test,
	},
};
</script>
