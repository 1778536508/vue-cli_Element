<template>
  <div>


    <row>
      <div class="col-md-4">
        <el-tree
          :data="data2"
          node-key="id"
          show-checkbox
          :default-expanded-keys="[2, 3]"
          :default-checked-keys="[5]"
          :props="defaultProps">
        </el-tree>
      </div>
      <div class="col-md-8">
        <va-textarea-group
        title="请输入短信内容："
        rowCount="20">
        </va-textarea-group>
        <el-row type="flex" justify="right">
          <el-col :span="6">
            <el-button type="primary" label="right" plain>发送</el-button>
          </el-col>
        </el-row>
      </div>
    </row>
  </div>
</template>

<script>
  import VATextareaGroup from '../components/VATextareaGroup'
  export default {
    data: function () {
      return {
        data2: [{
          id: 1,
          label: '一级 1',
          children: [{
            id: 4,
            label: '二级 1-1',
            children: [{
              id: 9,
              label: '三级 1-1-1'
            }, {
              id: 10,
              label: '三级 1-1-2'
            }]
          }]
        }, {
          id: 2,
          label: '一级 2',
          children: [{
            id: 5,
            label: '二级 2-1'
          }, {
            id: 6,
            label: '二级 2-2'
          }]
        }, {
          id: 3,
          label: '一级 3',
          children: [{
            id: 7,
            label: '二级 3-1'
          }, {
            id: 8,
            label: '二级 3-2'
          }]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      }
    },
    components: {
      'va-textarea-group': VATextareaGroup
    }
  }
</script>

<style scoped>

</style>
