<template>
    <div>
        <label>姓名：</label>
        <input type="text" v-model="form.name"><br>
        <label>年龄：</label>
        <input type="number" v-model="form.age"><br>
        <label>性别：</label>
        <select v-model="form.gender">
            <option value="">请选择</option>
            <option value="male">男</option>
            <option value="female">女</option>
        </select><br>
        <button type="button" @click="submit">添加</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            form:{
                name:'',
                age:'',
                gender:''
            }
        }
    },
    methods:{
       submit(){
           alert(`输入的姓名：${ this.form.name }，输入的年龄：${ this.form.age }，选择的性别：${ this.form.gender }`)
       }
   }
}
</script>

<style>
</style>
