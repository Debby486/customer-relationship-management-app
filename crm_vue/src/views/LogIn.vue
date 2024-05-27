<template>
    <div class="container">
        <div class="columns">
            <div class="column is-4 is-offset-4">
                <h1 class="title">Log in</h1>

                <form>
                    <div class="field">
                        <label for="">Email</label>
                        <div class="control">
                            <input type="email" name="email" class="input" v-model="username">
                        </div>
                    </div>
                    <div class="field">
                        <label for="">Password</label>
                        <div class="control">
                            <input type="password" name="password1" class="input" v-model="password">
                        </div>
                    </div>
                    <div
                        v-if="errors.length"
                        class="notification is-danger"
                    >
                        <p v-for="error in errors" :key="error">
                            {{ error }}
                        </p>
                    </div>
                    <div class="field">
                        <div class="control">
                            <button class="button is-success">Submit</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name:'LogIn',
        data() {
            return {
                username: '',
                password: '',
                errors: []
            }
        },

        methods: {
            submit() {
                axios.defaults.headers.common['Authorization'] = ''
                localStorage.removeItem('token')

                const formData = {
                        username: this.username,
                        password: this.password
                    }
            }
        }
    }
</script>