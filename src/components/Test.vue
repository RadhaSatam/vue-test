<template>
    <div class="test">
        <input type="text" v-model="title" /><br/>
        <h1 v-text="title"></h1>
        <p><span>Hello, {{user.firstName}}</span>
           <span v-if="showLName">{{user.lastName}}</span>
           <span v-else>S</span>
        </p>

        <!-- Loops -->
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>

        <!-- Events -->
        <button v-on:click="greet('Hello World!')">Ahoy!</button><br/>
        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit" />

        <br/><br/>

        <label>First Name: </label><input type="text" v-model="user.firstName" /><br/>
        <label>Last Name: </label><input type="text" v-model="user.lastName" /><br/>
        <h3>{{fullName}}</h3>
        <h4>{{msg}}</h4>
    </div>
</template>

<script>
export default {
    name: 'test',
    props: { 
        msg: {
            type: String,
            default: 'this is the default message'
        }
    },
    data () {
        return {
            title: 'Title',
            user: {
                firstName: 'John',
                lastName: 'Smith'
            },
            showLName: true,
            items: [
                { title: 'Item 1' },
                { title: 'Item 2' },
                { title: 'Item 3' },
                { title: 'Item 4' }
            ]
        }
    },
    methods: { 
        greet: function(greeting) {
            alert(greeting)
        },
        pressKey: function(e) {
            console.log(e.target.value)
        },
        enterHit: function() {
            console.log('enter was hit')
        }
    },
    computed: { 
        fullName: function() { 
            return this.user.firstName + ' ' + this.user.lastName
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none
    }
</style>
