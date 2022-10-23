<script lang="ts">

export default {
    data() {
        return{
            username:"jaehyun",
            HtmlString:'<div style="color:red;">abcd</div>',
            userid:'default',
            n1:0,
            n2:0,
            city:'064',
            arr:['bb'],
            radiov:'ee',
        }
    },
    methods:{
        e(){
            console.log(this.userid)
        },
        c(){
            this.userid="j"
        }
    }
}
</script>


<template>
    <div>
        <div>{{username}}</div>
        <br>
        <div v-html="HtmlString"></div>
        <br>
         <input type="text" v-model="userid">
         <button @click="e">enter</button>
         <button @click="c">change</button>
         <br>
         <input type="text" v-model.number="n1">+
         <input type="text" v-model.number="n2">=
         <span>{{n1+n2}}</span>
         <br><br>
         <select v-model="city">
            <option value=""></option>
            <option value="02">Seoul</option>
            <option value="051">Busan</option>
            <option value="064">Jeju</option>
         </select>
         <br><br>
         <div>
            <input type="checkbox" id="a" value="aa" v-model="arr">
            <label for="a">aaaaaaaaa</label>
         </div>
         <div>
            <input type="checkbox" id="b" value="bb" v-model="arr">
            <label for="b">bbbbbbbbb</label>
         </div><div>
            <input type="checkbox" id="c" value="cc" v-model="arr">
            <label for="c">cccccccccc</label>
         </div>
         <div>{{arr}}</div>
         <br>
         <div>
            <input type="radio" id="q" value="qq" v-model="radiov">
            <label for="q">qqqqqqqqqq</label>
         </div>
         <div>
            <input type="radio" id="w" value="ww" v-model="radiov">
            <label for="w">wwwwwwwwww</label>
         </div><div>
            <input type="radio" id="e" value="ee" v-model="radiov">
            <label for="e">eeeeeeee</label>
         </div>
         <div>{{radiov}}</div>
    </div>
</template>

<style scoped>

</style>