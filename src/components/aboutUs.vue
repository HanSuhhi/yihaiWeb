<template>
  <section>
    <p>{{ content[0] }}</p>
    <p>{{ content[1] }}</p>
    <p>{{ content[2] }}</p>
    <p>{{ content[3] }}</p>
  </section>
</template>

<script>
export default {
  data () {
    return {
      content: [
        'About Us',
        'Established in September 2009, Xuzhou Sanhe(Santrol) Automatic Control Equipment Co., Ltd. specializes in the research, development, production and sale of valves, microcomputer temperature controllers, humidity controllers, integrated motor protectors, etc. More than 200 kinds of products enjoy high reputation in China.',
        'Our company has more than 80 employees, of which more than 75% are employees with college degree or above; the company has an area of more than 2,600 square meters, 7 standardized production lines, and an annual production and assembly capacity of more than 350,000 units (sets ), Has professional production and testing equipment, and has a standard inspection and testing standards. The company is an ISO9001: 2008 quality management system certification unit.',
        'We are committed to becoming an expert in the field of energy efficiency management and automatic control. It provides industrial optimization by providing interconnected technologies and solutions. Since the establishment of the company, it has delivered more than 6 million units / sets of products to domestic and foreign markets. These products are serving many industries: freezing and refrigeration, chemical industry, boiler manufacturing, machinery manufacturing, fire protection (building control), etc.',
        '"Contact sincerity, enjoy richness together" is our business philosophy and common pursuit of us. "Pursuing excellent quality" is a magic weapon for our marketing and service. We sincerely cooperates with you to create a better tomorrow!',
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
  overflow: hidden;
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
  @media screen and (max-width: 700px){
    p {
      width: 90%;
      margin: .4rem;
      word-break:normal;
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
