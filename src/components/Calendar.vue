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
      //moment(this.currentDate)
      //でthis.currentDateのコピーを行う
      let date = moment(this.currentDate);
      date.startOf("moment");
      const youbiNum = date.day();
      return date.subtract(youbiNum, "days");
    },
    getEndDate() {
      let date = moment(this.currentDate);
      date.endOf("month");
      const youbiNum = date.day();
      return date.add(6 - youbiNum, "days");
    },
  },
  mounted() {
    console.log(this.getStartDate());
    console.log(this.getEndDate());
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
