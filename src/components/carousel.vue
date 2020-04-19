<template>
  <section>
    <nav>
      <p v-for="(nav, index) in navs" :key="index">
        <button v-if="navIndex === index" style="color: #343434;">{{ nav }}</button>
        <button @click="chooseProd(index)" v-else>{{ nav }}</button>
      </p>
    </nav>
    <el-dropdown class="select" style="margin-top: 1rem;">
      <el-button type="primary">
        产品选择<i class="el-icon-arrow-down el-icon--right"></i>
      </el-button>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item divided v-for="(prod, index) in navs" :key="index" @click.native="chooseProd(index)">
          <span v-if="chooseId === index" class="chooseProd">{{ prod }}</span>
          <span v-else>{{ prod }}</span>
        </el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>
    <div class="out">
      <!-- 1 -->
      <div v-if="showIndex.toString() === [1, 0].toString()">
        <img :src="m00">
        <p v-for="(word, index) in items00" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [1, 1].toString()">
        <img :src="m01">
        <p style="text-align:center">{{ title01 }}</p>
        <el-table
          :data="items01"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [1, 2].toString()">
        <img :src="m02">
        <p style="text-align:center">{{ title02 }}</p>
        <el-table
          :data="items02"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [1, 3].toString()">
        <img :src="m03">
        <p style="text-align:center">{{ title03 }}</p>
        <el-table
          :data="items03"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [1, 4].toString()">
        <img :src="m04">
        <p style="text-align:center">{{ title04 }}</p>
        <el-table
          :data="items04"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <!-- 2 -->
      <div v-if="showIndex.toString() === [2, 0].toString()">
        <img :src="m10">
        <p v-for="(word, index) in items10" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [2, 1].toString()">
        <img :src="m11">
        <p style="text-align:center">{{ title11 }}</p>
        <el-table
          :data="items11"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [2, 2].toString()">
        <img :src="m12">
        <p style="text-align:center">{{ title12 }}</p>
        <el-table
          :data="items12"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [2, 3].toString()">
        <img :src="m13">
        <p style="text-align:center">{{ title13 }}</p>
        <el-table
          :data="items13"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [2, 4].toString()">
        <img :src="m14">
        <p style="text-align:center">{{ title14 }}</p>
        <el-table
          :data="items14"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <!-- 3 -->
      <div v-if="showIndex.toString() === [3, 0].toString()">
        <p v-for="(word, index) in items10" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [3, 1].toString()">
        <img :src="m21">
        <p style="text-align:center">{{ title21 }}</p>
        <el-table
          :data="items21"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [3, 2].toString()">
        <img :src="m22">
        <p style="text-align:center">{{ title22 }}</p>
        <el-table
          :data="items22"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [3, 3].toString()">
        <img :src="m23">
        <p style="text-align:center">{{ title23 }}</p>
        <el-table
          :data="items23"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <!-- 4 -->
      <div v-if="showIndex.toString() === [4, 0].toString()">
        <img :src="m30">
        <p v-for="(word, index) in items30" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [4, 1].toString()">
        <img :src="m31">
        <p style="text-align:center">{{ title31 }}</p>
        <el-table
          :data="items31"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [4, 2].toString()">
        <img :src="m32">
        <p style="text-align:center">{{ title32 }}</p>
        <el-table
          :data="items32"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [4, 3].toString()">
        <img :src="m33">
        <p style="text-align:center">{{ title33 }}</p>
        <el-table
          :data="items33"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [4, 4].toString()">
        <img :src="m34">
        <p style="text-align:center">{{ title34 }}</p>
        <el-table
          :data="items31"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [4, 5].toString()">
        <img :src="m35">
        <p style="text-align:center">{{ title35 }}</p>
        <el-table
          :data="items35"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [4, 6].toString()">
        <img :src="m36">
        <p style="text-align:center">{{ title36 }}</p>
        <el-table
          :data="items36"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <!-- 5 -->
      <div v-if="showIndex.toString() === [5, 0].toString()">
        <p v-for="(word, index) in items40" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [5, 1].toString()">
        <img :src="m41">
        <p style="text-align:center">{{ title41 }}</p>
        <p style="font-weight: bold">Features</p>
        <p v-for="item in feature41" :key="item.id">
          {{ item }}
        </p>
        <p style="font-weight: bold">Technical specications</p>
        <p v-for="item in specications41" :key="item.id">
          {{ item }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [5, 2].toString()">
        <img :src="m42">
        <p style="text-align:center">{{ title42 }}</p>
        <p style="font-weight: bold">Features</p>
        <p v-for="item in feature42" :key="item.id">
          {{ item }}
        </p>
        <p style="font-weight: bold">Technical specications</p>
        <p v-for="item in specications42" :key="item.id">
          {{ item }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [5, 3].toString()">
        <img :src="m43">
        <p style="text-align:center">{{ title43 }}</p>
        <p style="font-weight: bold">Features</p>
        <p v-for="item in feature43" :key="item.id">
          {{ item }}
        </p>
        <p style="font-weight: bold">Technical specications</p>
        <p v-for="item in specications43" :key="item.id">
          {{ item }}
        </p>
      </div>
      <!-- 6 -->
      <div v-if="showIndex.toString() === [6, 0].toString()">
        <img :src="m50">
        <p v-for="(word, index) in items50" :key="index">
          {{ word }}
        </p>
      </div>
      <div v-if="showIndex.toString() === [6, 1].toString()">
        <img :src="m51">
        <p style="text-align:center">{{ title51 }}</p>
        <el-table
          :data="items51"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [6, 2].toString()">
        <img :src="m52">
        <p style="text-align:center">{{ title52 }}</p>
        <el-table
          :data="items52"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
      <div v-if="showIndex.toString() === [6, 3].toString()">
        <img :src="m53">
        <p style="text-align:center">{{ title53 }}</p>
        <el-table
          :data="items53"
          stripe
          style="width: 95%;margin-left: 5%;">
          <el-table-column
            prop="title"
            label="技术参数 | Technical specifications"
            width="360">
          </el-table-column>
          <el-table-column
            prop="chinese"
            label="中文"
            width="360">
          </el-table-column>
          <el-table-column
            prop="english"
            width="360"
            label="English">
          </el-table-column>
        </el-table>
      </div>
    </div>
  </section>
</template>
<script>
import { items00, items01, title01, items02, title02, items03, title03, items04, title04 } from '../tool/items0';
import { items10, items11, title11, items12, title12, items13, title13, items14, title14 } from '../tool/items1';
import { items20, items21, title21, items22, title22, items23, title23 } from '../tool/items2';
import { items30, items31, title31, items32, title32, items33, title33, items34, title34, items35, title35, items36, title36 } from '../tool/items3';
import { items40, feature41, feature42, feature43, specications41, specications42, specications43, title41, title42, title43 } from '../tool/items4';
import { items50, items51, items52, items53, title51, title52, title53 } from '../tool/items5';
export default {
  props: {
    navs: Array,
    chooseId: Number
  },
  data () {
    return {
      navIndex: 0,
      // 0
      items00,
      items01,
      title01,
      items02,
      title02,
      items03,
      title03,
      items04,
      title04,
      // 1
      items10,
      items11,
      title11,
      items12,
      title12,
      items13,
      title13,
      items14,
      title14,
      // 2
      items20,
      items21,
      title21,
      items22,
      title22,
      items23,
      title23,
      // 3
      items30,
      items31,
      items32,
      items33,
      items34,
      items35,
      items36,
      title31,
      title32,
      title33,
      title34,
      title35,
      title36,
      // 4
      items40,
      title41,
      title42,
      title43,
      feature41,
      feature42,
      feature43,
      specications41,
      specications42,
      specications43,
      // 5
      items50,
      items51,
      items52,
      items53,
      title51,
      title52,
      title53,
      m00: require('../../public/m1/m1.jpg'),
      m01: require('../../public/m1/FST01.A.jpg'),
      m02: require('../../public/m1/FST6200.jpg'),
      m03: require('../../public/m1/FST5168.jpg'),
      m04: require('../../public/m1/FST2200.jpg'),
      m10: require('../../public/m2/m2.jpg'),
      m11: require('../../public/m2/FST07.A2HT.jpg'),
      m12: require('../../public/m2/FST07.AX1.jpg'),
      m13: require('../../public/m2/FST07.A4.jpg'),
      m14: require('../../public/m2/FST07.A5.jpg'),
      m21: require('../../public/m3/ST3X3.jpg'),
      m22: require('../../public/m3/ST3X2.jpg'),
      m23: require('../../public/m3/ST7X2.jpg'),
      m30: require('../../public/m4/m4.jpg'),
      m31: require('../../public/m4/STVA2050.jpg'),
      m32: require('../../public/m4/STVB4025.jpg'),
      m33: require('../../public/m4/ST3X6.jpg'),
      m34: require('../../public/m4/ST7X6.jpg'),
      m35: require('../../public/m4/ST8X1.jpg'),
      m36: require('../../public/m4/STFL.jpg'),
      m41: require('../../public/m5/SH108.jpg'),
      m42: require('../../public/m5/SH8023.jpg'),
      m43: require('../../public/m5/SH2008.jpg'),
      m50: require('../../public/m6/m6.jpg'),
      m51: require('../../public/m6/ST3500.jpg'),
      m52: require('../../public/m6/ST3800.jpg'),
      m53: require('../../public/m6/SST-01.jpg'),
    }
  },
  computed: {
    showIndex () {
      return [this.chooseId, this.navIndex]
    }
  },
  methods: {
    chooseProd (index) {
      this.navIndex = index;
    }
  }
}
</script>
<style lang="scss" scoped>
@media screen and (min-width: 700px) {
  section {
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
    nav {
      position: relative;
      margin-top: 5%;
      width:20%;
      display: inline-block;
      word-break: break-all;
      line-height: 2rem;
      animation: fade-in .5s;
      button {
        text-align: left;
        position: relative;
        border: none;
        outline: none;
        background-color: white;
        color: rgba(black, .3);
        cursor: pointer;
        font-size: 16px;
        letter-spacing: 2px;
        animation: down 2s;
      }
    }
    nav::before {
      content: '';
      position: absolute;
      top: 1rem;
      right: -2rem;
      width: 4px;
      height: 100%;
      background-color: rgba(46, 153, 207, $alpha: .5);
      animation: up 1s;
    }
    .select {
      display: none;
    }
    .out {
      // position: absolute;
      // top: 10%;
      // right: 10%;
      display: inline-block;
      width: 60%;
      height: 50%;
      margin-top: 3rem;
      overflow: hidden;
      animation: upload 1.2s;
      div {
        width: 100%;
        height: 100%;
        padding-right: 20px;
        overflow: auto;
        overflow-x: hidden;
        display: flex;
        p{
          display: none;
          line-height: 40px;
          text-align: left;
          font-size: 16px;
          letter-spacing: 2px;
        }
        img {
          height: 10rem;
          width: auto;
        }
      }
    }
  }
}
@media screen and (max-width: 700px) {
section {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: flex-start;
  nav {
    display: none;
  }
  .select {
    width: 100%;
  }
  .out {
    // position: absolute;
    // top: 10%;
    // right: 10%;
    display: inline-block;
    width: 100%;
    height: 50%;
    margin-top: 1rem;
    overflow: hidden;
    animation: upload 1.2s;
    div {
      width: 100%;
      height: 100%;
      overflow: auto;
      overflow-x: hidden;
      text-align: center;
      p{
        width: 95%;
        margin-left: 3%;
        line-height: 40px;
        text-align: left;
        font-size: 14px;
        letter-spacing: 2px;
      }
      img {
        height: 10rem;
        width: auto;
      }
    }
  }
}
}
@keyframes fade-in {
  0% {opacity: 0;}
  40% {opacity: 0;}
  100% {opacity: 1;}
}
@keyframes up {
  0% {
    top: 8rem;
    opacity: 1;
  }
  100% {
    top: 1rem;
  }
}
@keyframes upload {
  0% {
    top: 20%;
    opacity: 0;
  }
  100% {
    top: 10%;
    opacity: 1;
  }
}
@keyframes down {
  0% {
    top: -4rem;
    opacity: 0;
  }
  100% {
    top: 0rem;
    opacity: 1;
  }
}
</style>
