<template>
  <q-page class="">
    <div class = "step" v-for = "i in items" :key="i.n" :style="{top: i.top + 'px', left:i.left + '%'}">
        {{i.n}}
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      items: [
        {
          n: 'Hi'
        },
        {
          n: 'Ho'
        }
      ],
      per: ['和尚', '道士', '外星人', '刺客', '魔法師',
        '智者', '戰士', '修行人', '小偷',
        '修女', '超人', '漁夫', '農婦', '小女孩', '小男孩',
        '小肥蟲', '外星人',
        '電漿生物', '變形蟲',
        '蜘蛛人', '神奇寶貝',
        '秘密客',
        '幽靈', '知名藝人', '米老鼠', '空空道人',
        '假面超人',
        '魔術師', '小叮噹',
        '武林高手',
        '數學家',
        '櫻木花道', '宮城良田', '流川楓', '赤木剛憲', '三井壽',
        '小火龍', '傑尼龜', '皮卡丘',
        '幫派份子', '苦力怕',
        '微生物',
        '小太陽',
        '恐怖份子']
    }
  },
  methods: {
    start () {
      var vm = this
      this.items = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30].map(function (k, idx) {
        return {
          n: idx + ':' + vm.per[Math.floor(Math.random() * vm.per.length)],
          top: k * 55,
          left: 50 + 30 * Math.sin(k * 3.14 / 8 - 4 * 3.14 / 8)
        }
      })
    }
  },
  mounted () {
    this.start()
  }
}
</script>

<style type="text/css" scoped="">
  .step {
    position: absolute;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 3px solid black;
    text-align: center;
    justify-content: center;
    align-items: center;
    display: flex;
    background-color: white;
  }
</style>
