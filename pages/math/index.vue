<template>
  <div>
    <h1>数学公式</h1>
    <p>备注: α, β, γ, δ, ε, ζ, η, θ, ι, κ, λ, μ, ν, ξ, ο, π, ρ, σ, τ, υ, φ, χ, ψ, ω</p>
    <ul class="gsList">
        <li v-for="(item, index) in mathList" :key="index">
            <h2 class="title">{{ item.name }}</h2>
            <p>{{ item.description }}</p>
            <p v-for="(v, i) in item.content" :key="i" v-html="v"></p>
            <!-- <canvas :id="'canvas'+index" width="300" height="200"></canvas> -->
        </li>
    </ul>
  </div>
</template>
<script>
export default {
  layout: 'index',
  name: 'math',
  data() {
    return {
        mathList: [
            {
                name: '空间中两点的距离',
                description: '点P1到点P2的距离计算公式',
                content: [
                    '|P<sub>1</sub>P<sub>2</sub>| = (X<sub>2</sub> - X<sub>1</sub>)<sup>2</sup> + (Y<sub>2</sub> - Y<sub>1</sub>)<sup>2</sup> + (Z<sub>2</sub> - Z<sub>1</sub>)<sup>2</sup>'
                ]
            },
            {
                name: '向量',
                description: '有大小有方向的量称为向量',
                content: [
                    '|AB| 或 |a| 称为向量的模',
                    '共线,共面',
                    '加法: OA+OB = OC (平行四边形法则) (三角形法则)',
                    '减法: OA-OB = BA',
                    '向量与数的乘法: λ大于0方向相同, λ小于0方向相反, 延长λ倍',
                ]
            }
        ]
    };
  },
  head: {
    title: "数学",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "数学公式",
      },
    ],
  },
  mounted() {
  },
  methods: {
  },
};
</script>

<style scoped>
.gsList {
    list-style: none;
    padding: 0;
    margin: 0;
}
.gsList li {
    background-color: #fff;
    margin: 20px 0;
    padding: 10px;
    box-shadow: 0px 0px 1px #ccc;
    border-radius: 5px;
}
.gsList li .title {
    font-weight: bold;
    color: #333;
}
</style>
