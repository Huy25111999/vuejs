<template>
<<<<<<< HEAD
  <div class="wrapper">
      Vue Ant Design
    <div class="wrapper-header">
      <a-button type ="primary" @click="showModal">Thêm mới</a-button>
      <a-modal v-model:visible="visible" title="Basic modal" @ok="handleOk">
        <p>contauer 1</p>
        <p>contauer 1</p>
        <p>contauer 1</p>
      </a-modal>
    </div>
    <a-table :data-source = "dataSource" :columns = "columns"> 

      <template #bodyCell="{column, record}">
        <template v-if="column.key ==='name'">{{record.name}}</template>
        <template v-else-if="column.key ==='tags'">{{record.tags}}</template>
        <template v-else-if="column.key ==='action'">
          <span>
            <a>Thêm</a>
            <a>Sửa</a>
            <a>Xoá</a>
          </span>
        </template>
      </template>

    </a-table>
  </div>

</template>

<script>  
import { defineComponent, ref } from 'vue';
  const dataSource = [
      {
            key: '1',
            name: 'Mike',
            age: 32,
            address: '10 Downing Street',
            phone:'034895394',
          },
          {
            key: '2',
            name: 'John',
            age: 42,
            address: '10 Downing Street',
            phone:'0489454',
          }
      ]
  const columns = [
            {
              title: 'Họ tên',
              dataIndex: 'name',
              key: 'name',
            },
            {
              title: 'Tuổi',
              dataIndex: 'age',
              key: 'age',
            },
            {
              title: 'Địa chỉ',
              dataIndex: 'address',
              key: 'address',
            },
            {
              title: 'Số điện thoại',
              dataIndex: 'phone',
              key: 'phone',
            },
            {
              title: 'Hành động',
              dataIndex: 'action',
              key: 'action',
            },
      ]

  export default defineComponent({
    data(){
      const visible = ref(false);
      const showModal = ()=>{
        visible.value = true;
      }
      const handleOk = e =>{
        console.log('---------',e);
        visible.value= false
      }
      return {
        visible,
        showModal,
        handleOk,
        dataSource, columns
      }
    }
  });
=======
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
>>>>>>> 6c37927 (form)
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
<<<<<<< HEAD

=======
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
>>>>>>> 6c37927 (form)
</style>
