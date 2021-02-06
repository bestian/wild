<template>
  <q-page class="flex">
    <div class = "step" v-for = "(i, idx) in items" :key="i.n" @click = "check(now, idx)" :class = "{active: now == idx, dis: now !== idx}">
        <span v-html = "i.n"></span>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      now: 0,
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
    check (n, idx) {
      if (this.now === idx) {
        this.now += this.items[idx].fun
      }
      if (this.now >= this.items.length) {
        alert('You Win!')
        this.now = 0
      }
    },
    start () {
      var vm = this
      this.items = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30].map(function (k, idx) {
        var f = idx % 3 === 1 ? Math.floor(Math.random() * 5) : 0
        if (f === 0) {
          f = 1
        }
        var n = idx % 3 === 1 ? idx + ':<br/>' + '遇到' + vm.per[Math.floor(Math.random() * vm.per.length)] + '<br/>' + (f >= 0 ? '向前' : '向後') + f + '步' : idx
        return {
          fun: f,
          n: n,
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

  .flex {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .step {
    width: 10%;
    height: 100px;
    border-radius: 5px;
    border: 3px solid black;
    text-align: center;
    justify-content: center;
    align-items: center;
    display: flex;
    background-color: white;
  }

  .active {
    background-color: #cfc;
  }

  .dis {
    background-color: white;
    opacity: 1;
    cursor: not-allowed;
  }

  .container {
  display: flex;
  display: -webkit-flex;
  flex-wrap: wrap;
  -webkit-flex-wrap: wrap;
  }

.step:nth-child(1) { order: 0; }
.step:nth-child(2) { order: 1; }
.step:nth-child(3) { order: 2; }
.step:nth-child(4) { order: 3; }
.step:nth-child(5) { order: 4; }
.step:nth-child(6) { order: 5; }
.step:nth-child(7) { order: 6; }
.step:nth-child(8) { order: 7; }
.step:nth-child(9) { order: 8; }
.step:nth-child(10) { order: 9; }
.step:nth-child(11) { order: 19; }
.step:nth-child(12) { order: 18; }
.step:nth-child(13) { order: 17; }
.step:nth-child(14) { order: 16; }
.step:nth-child(15) { order: 15; }
.step:nth-child(16) { order: 14; }
.step:nth-child(17) { order: 13; }
.step:nth-child(18) { order: 12; }
.step:nth-child(19) { order: 11; }
.step:nth-child(20) { order: 10; }
.step:nth-child(21) { order: 20; }
.step:nth-child(22) { order: 21; }
.step:nth-child(23) { order: 22; }
.step:nth-child(24) { order: 23; }
.step:nth-child(25) { order: 24; }
.step:nth-child(26) { order: 25; }
.step:nth-child(27) { order: 26; }
.step:nth-child(28) { order: 27; }
.step:nth-child(29) { order: 28; }
.step:nth-child(30) { order: 29; }
.step:nth-child(31) { order: 30; }
</style>
