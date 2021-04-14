<template>
  <p>Hello Unko</p>
</template>

<script>
import moment from "moment";

export default {
  data() {
    return {
      currentDate: moment(),
    };
  },
  methods: {
    getStartDate() {
      let date = moment(this.currentDate);
      date.startOf("moment");
      const youbiNum = date.day();
      return date.subtract(youbiNum, "days");
    },
  },
  mounted() {
    console.log(this.getStartDate());
  },
  //インスタンスが生成されてからマウント
  // mounted() {
  //   //その月の最初に日を取得
  //   let date = moment().startOf("month");
  //   //日時を変数に代入
  //   const youbiNum = date.day();
  //   //ログで確認(日曜日が0)
  //   console.log(youbiNum);
  // },
};
</script>
