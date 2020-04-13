<template>
  <section>
    <p>联系方式 Contact Us</p>
    <p v-for="(word, index) in content" :key="index">
      {{ word }}
    </p>
  </section>
</template>

<script>
export default {
  data () {
    return {
      content: [
        'Xuzhou Sanhe Automatic Control Equipment CO.,LTD',
        'Address: No.18 Minyuan RD, Minying Industrial Park Tongshan Economic Development Area, Xuzhou, Jiangsu, China',
        'Contact: info@santrolair.com',
        'Cell: +86 186 5220 1936'
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  @media screen and (min-width: 1250px) {
    p {
      width: 50%;
      text-align: left;
      font-size: 18px;
      letter-spacing: 2px;
      line-height: 30px;
      animation: fade-in .5s;
    }
  }
  @media screen and (max-width: 1250px) {
    p {
      width: 80%;
      text-align: left;
      font-size: 18px;
      letter-spacing: 2px;
      line-height: 30px;
      animation: fade-in .5s;
    }
  }
  @media screen and (max-width: 500px){
    p {
      width: 100%;
      margin: .4rem;
      text-align: left;
      font-size: 14px;
      letter-spacing: 2px;
      line-height: 30px;
      animation: fade-in .5s;
    }
  }
  p:nth-of-type(1) {
    animation: fade-in .7s;
    font-weight: bold;
  }
  p:nth-of-type(2) {
    animation: fade-in .9s;
  }
  p:nth-of-type(3) {
    animation: fade-in 1.1s;
  }
  p:nth-of-type(4) {
    animation: fade-in 1.3s;
  }
  p:nth-of-type(5) {
    animation: fade-in 1.5s;
  }
}
@keyframes fade-in {
  0% {opacity: 0;}
  40% {opacity: 0;}
  100% {opacity: 1;}
}
</style>
