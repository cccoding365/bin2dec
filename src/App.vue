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

	<p class="user-stories">
		<em>User Stories</em><br />
		1. User can enter up to 8 binary digits in one input field<br />
		2. User must be notified if anything other than a 0 or 1 was entered<br />
		3. User views the results in a single output field containing the
		decimal (base 10) equivalent of the binary number that was entered
	</p>
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
.user-stories {
	margin-top: 5em;
	background-color: #3e3e3e;
	padding: 10px 20px;
	border-radius: 10px;
	font-size: 16px;
	line-height: 2;
	text-align: left;
}
</style>
