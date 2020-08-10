<template>
  <div>
    <h1>dd</h1>　　
    <!--通过 ：settings="hotSettings" 来定义结构，数据，以及属性等-->
    <hot-table :settings="hotSettings"></hot-table>
  </div>
</template>

<script>
import { HotTable } from '@handsontable/vue';
import 'handsontable/dist/handsontable.full.css';
export default {
  data () {
    return {
      hotSettings: {　　　　　　//定义数据
        data: [
          ["2016-01-01", 'BMW', 11, 12,],
          ["2017-01-01", 'BMW', 11, 14,],
          ["2018-01-01", 'BMW', 15, 12,]
        ],　　　　　　//定义表结构
        colHeaders: [
          "问题序号", "问题类型", "定性法规", "问题金额"
        ],　　　　　　//定义属性
        columns: [
          {
            type: 'date',   //时间格式

            dateFormat: 'YYYY-MM-DD',

            correctFormat: true,

            defaultDate: '1900-01-01'
          },
          {
            type: 'dropdown', //下拉选择

            source: ['BMW', 'Chrysler', 'Nissan', 'Suzuki', 'Toyota', 'Volvo'],

            strict: false   //是否严格匹配
          },
          {},
          {
            colHeaders: '问题金额',
            type: 'numeric', //定义值的类型为数字类型
          }
        ],
      },

    }
  },
  components: {
    HotTable
  }
}
</script>