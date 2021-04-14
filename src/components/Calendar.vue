<template>
  <p>Hello Unko</p>
</template>

<script>
import moment from "moment"

export default {
  //インスタンスが生成されてからマウント
  mounted(){
    //その月の最初に日を取得
    let date = moment().startOf("month")
    //日時を変数に代入
    const youbiNum = date.day()
    //ログで確認
    console.log(youbiNum)
  }
}

</script>