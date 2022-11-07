<template>
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
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
