<script setup lang="ts">
import Logo from "@/components/Logo.vue";
import { ref, computed } from "vue";

const input = ref("");
const output = computed(() => bin2dec(input.value));

const isBinary = (str: string) => /^[01]+$/.test(str);

const bin2dec = (str: string) => {
	if (!isBinary(str)) return 0;

	let len = str.length;
	let count = 0;
	while (len--) {
		const weight = 2 ** (str.length - len - 1);
		count += Number(str.charAt(len)) * weight;
	}
	return count;
};
</script>

<template>
	<Logo />
	<input
		class="binary"
		v-model="input"
		placeholder="Please enter 0 and 1 here..."
	/>
	<div v-if="input && !isBinary(input)" class="tips">
		Warning: Only "0" and "1" are allowed!
	</div>
	<div class="decimal">Output: {{ output }}</div>
</template>

<style scoped>
.binary {
	font-size: 24px;
	padding: 10px 20px;
	margin-bottom: 1em;
}
.decimal {
	font-size: 24px;
}
.tips {
	margin-bottom: 1em;
	color: red;
}
</style>
