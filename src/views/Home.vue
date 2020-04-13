<template>
<div class="HOME">
  <header>
    <img alt="Vue logo" src="../assets/logo.png" class="img">
    <!-- 1250 -->
    <div class="c1250">
      <section v-for="(prod, index) in prods" :key="index" @click="chooseProd(index)">
        <span v-if="chooseId === index" class="chooseProd">{{ prod }}</span>
        <span v-else>{{ prod }}</span>
      </section>
    </div>
    <!-- <1250 -->
    <el-dropdown class="m1250">
      <el-button type="primary">
        {{ prods[chooseId] }}<i class="el-icon-arrow-down el-icon--right"></i>
      </el-button>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item divided v-for="(prod, index) in prods" :key="index" @click.native="chooseProd(index)">
          <span v-if="chooseId === index" class="chooseProd">{{ prod }}</span>
          <span v-else>{{ prod }}</span>
        </el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>
  </header>
  <article>
    <aboutUs v-if="chooseId === 0"></aboutUs>
    <carousel v-else-if="chooseId === 1" :chooseId="chooseId" :navs="navs1"></carousel>
    <carousel v-else-if="chooseId === 2" :chooseId="chooseId" :navs="navs2"></carousel>
    <carousel v-else-if="chooseId === 3" :chooseId="chooseId" :navs="navs3"></carousel>
    <carousel v-else-if="chooseId === 4" :chooseId="chooseId" :navs="navs4"></carousel>
    <carousel v-else-if="chooseId === 5" :chooseId="chooseId" :navs="navs5"></carousel>
    <carousel v-else-if="chooseId === 6" :chooseId="chooseId" :navs="navs6"></carousel>
    <bottom-content v-else />
  </article>
</div>
</template>

<script>
import bottomContent from '../components/bottom.vue';
import aboutUs from '../components/aboutUs.vue';
import carousel from '../components/carousel.vue';
import { prods } from '../tool/common';
export default {
  name: 'Home',
  components: {
    bottomContent,
    aboutUs,
    carousel
  },
  data () {
    return {
      prods: prods,
      chooseId: 0,
      navs1: [
        '0 区域电动阀系列 | Motorized Zone Valves',
        '1 FST01.A 系列二线电动阀 | Series Motorized Valve 2 Wires',
        '2 FST6200 系列二线电动阀 | Series Motorized Valve 2 Wires',
        '3 DYH5168 系列三线电动阀 | Series Motorized Valve 3 Wires',
        '4 FST2200 系列动态平衡电动二通阀 | Series Dynamic Balancing Motorized 2way Valve',
      ],
      navs2: [
        '0 电动球阀系列 | Motorized Ball Valves',
        '1 FST07.A2HT 系列智能电动球阀 | FST07.A2HT Series Intelligent Motorized Ball Valve',
        '2 FST07.AX1 系列三线电动球阀 | FST07.AX1 Series 3 Wires Motorized Ball Valve',
        '3 FST07.A4 系列智能电动球阀 | FST07.A4 Series Intelligent Motorized Ball Valve',
        '4 FST07.A5 系列智能电动球阀 | FST07.A5 Series Intelligent Motorized Ball Valve',
      ],
      navs3: [
        '0 电动调节阀 | Motorized Modulating Valves',
        '1 ST3X3 系列电动调节阀 | ST3X3 Series Motorized Modulating Valve',
        '2 ST3X2 系列电动调节阀 | ST3X2 Series Motorized Modulating Valve',
        '3 ST7X2 系列电动调节阀 | ST7X2 Series Motorized Modulating Valve'
      ],
      navs4: [
        '1 水力平衡阀系列 | Hydraulic Balancing Valves',
        '2 STVA2050 系列静态平衡阀 | STVA2050 Series Static Balance Valve',
        '3 STVB4025 系列静态平衡阀 | STVB4025 Series Static Balance Valve',
        '4 ST3X6 系列电动动态平衡调节阀 | ST3X6 Series Motorized Static Balance Modulating Valve',
        '5 ST7X6 系列电动动态平衡调节阀 | ST8X1 Series Motorized Butterfly Valve',
        '6 ST8X1 系列电动蝶阀 | ST8X1 Series Motorized Butterfly Valve',
        '7 STFL 系列动态平衡阀 | STFL Series Dynamic Balance Valve'
      ],
      navs5: [
        '0 温控器 | 5. Thermostats',
        '1 SH108 Series Thermostat',
        '2 SH8023 Series Thermostat',
        '3 SH2008 Series Thermostat'
      ],
      navs6: [
        '0 楼宇自控配件 | 6. Building Automatic Control System Accessories',
        '1 ST3500 系列数字比例积分温控器 | ST3500 Series Digital Proportional Integral Control Box',
        '2 ST3800 系列压差控制箱 | ST3800 Series Differential Pressure Control Box',
        '3 SST-01 系列水流开关 | SST-01 Series Flow Switch'
      ],
    }
  },
  mounted () {
  },
  methods: {
    chooseProd (index) {
      this.chooseId = index;
      console.log(this.chooseId);
    }
  }
}
</script>

<style lang="scss" scoped>
.HOME {
  width: 100%;
  header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: bottom;
    .img {
      height: 3rem;
      width: auto;
    }
    .c1250 {
      display: none;
    }
    @media screen and (min-width: 1250px) {
      .c1250 {
        display: flex;
        section {
          padding: 20px;
          font-size: 18px;
          letter-spacing: 2px;
          font-weight:500;
          transition: all .5s;
          .chooseProd {
            font-weight: bold;
            padding-bottom: 10px;
          }
          .chooseProd::after {
            content: "";
            display: block;
            position: relative;
            top: 10px;
            left: 10%;
            width: 80%;
            height: 2px;
            background: black;
            animation: bottomLine 1s;
          }
        }
        section:hover {
          cursor: pointer;
          animation: tdAnimation .3s;
        }
      }
      .m1250 {
        display: none;
      }
    }
    @media screen and (max-width: 1250px){
      .m1250 {
        margin: .6rem;
      }
    }
  }
}
.el-dropdown {
  vertical-align: top;
}
.el-dropdown + .el-dropdown {
  margin-left: 15px;
}
.el-icon-arrow-down {
  font-size: 12px;
}
@keyframes tdAnimation {
  0% {
    position: relative;
    bottom: 0px;
  }
  50% {
    position: relative;
    bottom: 5px;
  }
  100% {
    position: relative;
    bottom: 0px;
  }
}
@keyframes bottomLine {
  0% {
    width: 0%;
  }
  100% {
    width: 80%;
  }
}
</style>
