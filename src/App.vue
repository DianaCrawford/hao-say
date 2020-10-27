<template>
  <div id="app">
    <!-- <img alt="Vue logo" height="50" width="50" src="./assets/logo.png"> -->
    <div>
      <!-- <img id="dog" height="50" width="50" src="./assets/dog.png" style="vertical-ali"> -->
      <textarea id="uSay" rows="20" cols="100" v-model="uSay" placeholder="Type what u say"></textarea>
    </div>

    <div>
      <button @click="u2hao()">👇↓</button>
      <button @click="hao2u()">👆↑</button>
    </div>

    <div>
      <!-- <img id="hao" height="50" width="50" src="./assets/hao.png" style=""> -->
      <textarea id="haoSay" rows="20" cols="100" v-model="haoSay" placeholder="Type what hao said"></textarea>
    </div>
  </div>
</template>

<script>
import * as zeroWidthLib from "zero-width-lib";

export default {
  name: "App",
  data: () => {
    return {
      uSay: "",
      haoSay: "",
      haoSaid:
        "我在青年时期就读过西游记、马可波罗游记、左丘明、我的故乡、纳楚克道尔基、吉檀迦利、园丁集、飞鸟集、新月集、泰戈尔、三国演义、水浒传、老子、孔子、墨子、孟子、庄子、伏尔泰、孟德斯鸠、狄德罗、卢梭、圣西门、蒙田、傅立叶、拉封丹、萨特、司汤达、莫里哀、大仲马、雨果、巴尔扎克、福楼拜、乔治桑、莫泊桑、小仲马、冉阿让、罗曼罗兰、羊脂球、卡西莫多、席勒、歌德、海涅、莱布尼兹、黑格尔、康德、费尔巴哈、马克思、海德格尔、马尔库塞。我还读过，托马斯潘恩常识、联邦党人文集、梭罗、惠特曼、马克吐温、杰克伦敦、海明威老人与海、简奥斯丁、华滋华斯、狄更斯 猫、福尔摩斯、卡尔马克思、弗里德里希恩格斯、拜伦、雪莱、萧伯纳、培根、克伦威尔、约翰洛克、托马斯莫尔、亚当斯密、李约瑟、阿诺德汤因比、双城记、雾都孤儿、简爱、鲁滨孙漂流记、汤显祖牡丹亭、南柯记、紫钗记、邯郸记、莎士比亚 威尼斯商人、仲夏夜之梦、罗密欧与朱丽叶、第十二夜、李尔王、奥赛罗、麦克白斯，谢谢大家。"
    };
  },
  methods: {
    u2hao() {
      if (this.uSay) {
        this.haoSay = zeroWidthLib.encode(this.haoSaid, this.uSay);
      } else {
        return "";
      }
      // console.log(this.uSay);
    },
    hao2u() {
      if (this.haoSay) {
        this.uSay = zeroWidthLib.decode(this.haoSay);
      } else {
        return "";
      }
      // console.log(this.uSay);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img {
    vertical-align: top;
    margin-right: 20px;
}
button {
    margin-top: 5px;
    margin-bottom: 10px;
    margin-left: 320px;
}
</style>
