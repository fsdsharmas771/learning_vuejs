<template>
    <div>
        <!-- mousemove event -->
        <h1 v-on:mousemove="getConsole()">Hello From Home Component</h1>
        <!-- onclick event -->
        <button v-on:click="getData('btn1')">Button 1</button>
        <button v-on:click="getData('btn2')">Button 2</button>
        <h2>{{count1}}</h2>
        <h2>{{count2}}</h2>
        <!-- two way binding and get input value -->
        <!-- v-model="variable name", is used to two way binding -->
        <input type="text" v-model="a"/>
        <h2>{{a}}</h2>
        <!-- get values of checkbox -->
        <label for="python">Python</label>
        <input type="checkbox" id="python" value="Python" v-model="technology"/>
        <label for="javascript">Javascript</label>
        <input type="checkbox" id="javascript" value="Javascript" v-model="technology" />
        <label for="java">Java</label>
        <input type="checkbox" id="java" value="Java" v-model="technology" />
        <h2>Technology Used: {{technology}}</h2>
        <!-- get values of radio button -->
        <label for="student">Student</label>
        <input type="radio" id="student" name="who" value="Student" v-model="who"/>
        <label for="developer">Developer</label>
        <input type="radio" id="developer" name="who" value="Developer" v-model="who" />
        <h2>I am :{{who}}</h2>
        <!-- conditional rendring or if else -->
        <h1 v-if="show">If show is true or condition is true</h1>
        <h1 v-else>If show is false or condition is false</h1>
        <button v-on:click="show=!show">Toggle</button>
        <!-- for loop and list/list of objects -->
        <!-- 1st is for list -->
        <h4>Technologies</h4>
        <ul>
            <li v-for="item in tech" :key="item">
                {{item}}
            </li>
        </ul>
        <!-- 2nd is of list of objects -->
        <h4>User Details</h4>
        <ul>
            <li v-for="item in users" :key="item">
                Name:{{item.name}}<br/>Email:{{item.email}}<br/><br/>
            </li>
        </ul>
        <!-- passing data prof parent to child component -->
        <Child name='Tarun' :users='users' :getName='getName' />
    </div>
</template>
<script>
import Child from './ChildComponent.vue'
export default {
    name: "Home",
    components:{
        Child,
    },
    data(){
        return{
            count1:0,
            count2:0,
            a:0,
            technology:[],
            who:null,
            show:true,
            tech:['MERN Stack','MEAN Stack','Fluter'],
            users:[{
                name:'Tarun',
                email:'Sharmas771@gmail.com'
            },
            {
                name:'Charul',
                email:'fsdsharmas771@gmail.com'
            }
            ]
        }
    },
    methods: {
        getData(a) {
            if(a=='btn1'){
                this.count1=this.count1+1;
            }else{
                this.count2=this.count2+1;
            }
        },
        getConsole(){
            console.log("h1 is hovered");
        },
        getName(n){
            alert(n);
        }
    },
};
</script>
<style scoped>
h1 {
    color: red;
}
</style>
