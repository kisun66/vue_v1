<template>
    <div>
        <h1>Welcome to {{title}}!</h1>
        <input type="text" v-model="input1"/>
        <button @click="getData">Click</button>
        <button @click="setData">Click</button>
        <button @click="showData">TableToggle</button>

        <select class="form-control" v-model="name">
            <option :key="i" :value="d.id" v-for="(d,i) in data">{{d.name}}</option>
        </select>

        <table class="table table-bordered" v-show="tableShow">
            <tr :key="i" v-for="(d,i) in data">
                <td>{{d.id}}</td>
                <td>{{d.name}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data() {
        return{
            title: "LeeSeungyoung",
            input1: "abc",
            data: [
                {id: "1", name: "홍길순"},
                {id: "2", name: "홍길동"},
                {id: "3", name: "홍길영"}
            ],
            name: "2",
            tableShow: false,
        } 
    },
    methods: {
        getData() {
            alert(this.input1);
        },
        setData() {
            this.input1 = "12345";
        },
        showData() {
            this.tableShow = false;
        },
    },
    watch: {
        input1() {
            console.log(this.input1);
        }
    },
    /*
    페이지 생성 시 생명주기
    */
    beforeCreate() {
        console.log("beforeCreate");
    },
    created() {
        console.log("created");
    },
    beforeMount() {
        console.log("beforeMount");
    },
    mounted() {
        console.log("mounted");
    },
    /*
    업데이트 생명주기
    */
    beforeUpdate() {
        console.log("beforeUpdate");
    },
    updated() {
        console.log("updated");
    }
}
</script>