<template>
    <div class="mt-4">
        <b-form @submit.prevent="onSubmit">
            <ValidationProvider
                name="Name"
                rules="email"
                v-slot="{ errors }"
            >
                <b-form-group label="Name:">
                    <b-form-input
                        v-model="form.name"
                        type="text"
                        required
                    ></b-form-input>
                </b-form-group>
                <span>{{ errors[0] }}</span>
            </ValidationProvider>

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

            <b-form-group label="Confirm Password:">
                <b-form-input
                    type="password"
                    v-model="form.passwordConfirm"
                    required
                ></b-form-input>
            </b-form-group>

            <b-button type="submit" variant="primary">Sign Up</b-button>
        </b-form>
    </div>
</template>

<script>
    import axios from 'axios';
    import { ValidationProvider } from 'vee-validate';
	export default {
        components: {
            ValidationProvider
        },
		data() {
			return {
				form: {
					email: '',
					password: '',
					passwordConfirm: '',
                    name: ''
				}
			}
		},
		methods: {
			async onSubmit() {
          try {
              await axios.post('http://localhost:3000/auth/signup', {
                  email: this.form.email,
                  password: this.form.password,
                  name: this.form.name
              })

              this.$router.push({ path: '/login' })
          } catch (err) {
              console.log(err);
          }
			}
		}
	}
</script>
