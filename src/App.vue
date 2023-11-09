<script setup lang="ts">
import Logo from "@/components/Logo.vue";
import { ref, computed } from "vue";

const output = computed(() => (binary.value ? binary.value : 0));
const binary = ref();

const bin2dec = () => {
	console.log(111);

	// output.value = binary.value
};
</script>

<template>
	<Logo />
	<div class="decimal">Output: {{ output }}</div>
	<input
		class="binary"
		v-model="binary"
		placeholder="Please enter 0 and 1 here..."
		@change="bin2dec"
	/>
</template>

<style scoped>
.binary {
	font-size: 24px;
	padding: 10px 30px;
}
.decimal {
	font-size: 24px;
	margin-bottom: 1em;
}
</style>
