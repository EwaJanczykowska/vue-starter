<template>
	<div>
		<label>Zaloguj się e-mailem</label>
		<input type="email" v-model="typedEmail">
		<button @click="enter()">{{ buttonLabelToDisplay }}</button>
	</div>
</template>

<script>
    export default {
        props: ['buttonLabel'],
        data() {
            return {
                typedEmail: ''
            }
        },
        methods: {
            enter() {
                this.$emit('login', this.typedEmail);
            }
        },
        /*mounted() {
            if (!this.buttonLabel) {
                this.buttonLabel = 'Zaloguj się';
            }
        },*/
        computed: {
            buttonLabelToDisplay() {
                return this.buttonLabel || 'Zaloguj się';
            }
        }
    }
</script>