<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <style>

        #app p {
            color: red;
        }

        #app a {
            color: blue;
        }

        #app span {
            color: blueviolet;
        }

    </style>

</head>
<body>

<div id="app">
    {{hello}}
    <p v-bind:title="message">
        {{message}}
    </p>
    <a v-if="seen">现在你看到我了，我是第三个练习</a>
    <p v-for="title in list">
        {{ title.name }}
    </p>
    <button v-on:click="updateMessage">修改第二个练习Message的内容</button>
    <br/> <br/>
    <span>{{input_value}}</span>
    <input v-model="input_value">
</div>

<script>
    var app = new Vue({
        el: '#app',
        data: {
            hello: '第一个练习：Hello Vue!',
            message: '第二个练习：页面加载于 ' + new Date().toLocaleString(),
            seen: true,
            list: [{name: '学习JavaScript'}, {name: '学习Vue'}, {name: '把第四个练习做成功'}],
            input_value: '第六个练习,数据双向绑定'
        },
        methods: {
            updateMessage: function () {
                this.message = "如果你看到这个内容，就说明你把第五个练习做成功了"
            }
        }
    })
</script>
</body>
</html>
