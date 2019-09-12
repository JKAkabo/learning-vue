<template>
    <div id="employee-form">
        <form @submit.prevent="handleSubmit">
            <label>Employee Name</label>
            <input type="text" v-model="employee.name" ref="first" />
            <label>Employee Email</label>
            <input type="email" v-model="employee.email" />
            <button type="submit">Add employee</button>
        </form>
    </div>
</template>

<script>
export default {
    name: 'employee-form',
    data: () => {
        return {
            employee: {
                name: '',
                email: ''
            }
        }
    },
    methods: {
        handleSubmit() {
            this.$emit('add:employee', this.employee);
            this.$refs.first.focus();
        }
    }
}
</script>

<style scoped>

</style>
