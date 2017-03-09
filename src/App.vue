<template>
<div>
    <label>姓名：</label>
    <input type="text" v-model="form.name.value">
    <span v-if="form.name.valid">正确</span>
    <span v-else>正确</span>
    <br>
    <label>年龄：</label>
    <input type="number" v-model="form.age.value"><br>
    <label>性别：</label>
    <select v-model="form.gender.value">
            <option value="">请选择</option>
            <option value="male">男</option>
            <option value="female">女</option>
        </select><br>
    <button type="button" @click="submit">添加</button>
</div>
</template>
<script>
export default {
    data() {
        return {
            form: {
                name: {
                    value: '',
                    valid: false
                },
                age: {
                    value: '',
                    valid: false
                },
                gender: {
                    value: '',
                    valid: false
                }
            }
        }
    },
    methods: {
        submit() {
            const formDate = {
                name : this.form.name.value,
                age : this.form.age.value,
                gender : this.form.gender.value
            }
            fetch('http://localhost:3000/user', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(formDate)
            }).then(() => {
                alert("添加成功")
            }).catch(response => {
                console.log(response);
            })
        }
    },
    computed: {
        'form.name.valid': function() {
            return this.form.name.value.length > 10 ? false : true
        }
    }
}
</script>
<style>

</style>
