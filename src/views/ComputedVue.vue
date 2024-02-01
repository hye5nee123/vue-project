<template>
    <div>
        <h1>{{ `${this.lastName} ${this.firstName}` }}</h1>
        <h1>{{ `${fullName}` }}</h1>
    </div>
    <input type="text" v-model="lastName">
    <input type="text" v-model="firstName">
</template>
<script>
export default {
    data() {
        return {
            firstName: 'kildong',
            lastName: 'Hong'
        }
    },
    computed: {
        fullName() {
            return `${this.lastName} ${this.firstName}`
        }
    },
    watch: {  //변경이전, 이후.
        firstName(curr,bef){
            console.log(curr,bef);
        }
    }
}
</script>