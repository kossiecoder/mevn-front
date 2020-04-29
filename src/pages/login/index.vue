<template>
    <div class="mt-4">
        <b-form @submit.prevent="onSubmit">
            <b-form-group label="Email address:">
                <b-form-input
                    v-model="form.email"
                    type="email"
                    required
                ></b-form-input>
            </b-form-group>

            <b-form-group label="Password:">
                <b-form-input
                    type="password"
                    v-model="form.password"
                    required
                ></b-form-input>
            </b-form-group>

            <b-button type="submit" variant="primary">Login</b-button>
        </b-form>
    </div>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					email: '',
                    password: ''
                }
            }
        },
        methods: {
            onSubmit() {

            }
        }
    }
</script>
