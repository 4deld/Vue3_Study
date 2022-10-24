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
            bindtest:'never changed',
            bind2:'',
            cities:[
                {title:'Seoul',code:'02'},
                {title:'Busan',code:'011'},
                {title:'Geo',code:'097'},
            ],
            drinklist:[
                {
                    drinkid:1,
                    name:'Coke',
                    price:1500,
                    qty:1
                },
                {
                    drinkid:2,
                    name:'Milk',
                    price:1000,
                    qty:54
                },
                {
                    drinkid:3,
                    name:'juice',
                    price:1900,
                    qty:14
                },

            ],
            active:true,
            style1:{
                color:'red',
                fontSize:'30px'
            }
        }
    },
    methods:{
        e(){
            console.log(this.userid)
        },
        c(){
            this.userid="j"
        },
        b(){
            console.log(this.bindtest)
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
         <br>
         <input type="text" :value="bindtest">
         <button @click="b">enter</button>
         <br>
         <input type="text" v-model="bind2">
         <button :disabled="bind2===''">search</button>
         <br>
         <br>
         <select>
            <option value=""></option>
            <option :value="city.code" :key="city.code" v-for="city in cities">
                {{city.title}}
            </option>
         </select>
         <br><br>
         <table>
            <thead>
                <th>Name</th>
                <th>Price</th>
                <th>Number</th>
                <th>Sum</th>
            </thead>
            <tbody>
                <tr v-for="drink in drinklist">
                    <td>{{drink.name}}</td>
                    <td>{{drink.price}}</td>
                    <td><input type="number" v-model.number="drink.qty"></td>
                    <td>{{drink.price*drink.qty}}</td>
                </tr>
            </tbody>
         </table>
         <br>
         <br>
         <div :class="{ 'a---a' : active,'b':true}">Class Binding</div>
         <br>
         <div :style="style1">AAA</div>
         <button @click="style1.color='blue'">Change color</button>
    </div>
</template>

<style scoped>
.a---a{
    background-color: green;
}
.b{
    color: yellow;
}
</style>