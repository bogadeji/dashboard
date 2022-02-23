<template>
    <div class="analysis-card flow">
        <div class="title flex">
            <p class="fw-bold line-clamp" >{{ data.description }}</p>
            <img src="~/static/icons/dot.svg" alt="" />
        </div>
        <div class="flex data">
            <div class="data flow">
                <p class="fs-700 fw-bolder value">{{ data.value }}</p>
                <p class="fs-200 growth-rate line-clamp" v-if="data.growthRate">
                    <span :class="{ fall: data.growthRate < 0, rise: data.growthRate > 0 }" class="growth-rate fw-bold">
                        <span v-if="data.growthRate < 0"><img src="~/static/icons/fall.svg" alt="" /></span>
                        <span v-if="data.growthRate > 0"><img src="~/static/icons/rise.svg" alt="" /></span>
                        {{ Math.abs(data.growthRate)}}%
                    </span> vs last month</p>
            </div>
            <div class="chart">
                <img src="~/static/chart/rise.svg" alt="" v-if="data.growthRate > 0" />
                <img src="~/static/chart/fall.svg" alt="" v-if="data.growthRate < 0"/>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'AnalyticsCard',
    props: {
        data: {
            type: Object,
            default: {}
        }
    }
}
</script>
<style scoped>
    .analysis-card {
        color: hsla(221, 43%, 11%, 1);
        border-radius: 8px;
        padding: 1.5rem;
        border: 1px solid #EAECF0;
        box-shadow: 0px 1px 3px rgba(16, 24, 40, 0.1), 0px 1px 2px rgba(16, 24, 40, 0.06);
    }
    .title {
        justify-content: space-between;
    }
    .title p {
        margin: 0;
    }
    .title img {
        justify-content: flex-end;
    }
    .analysis-card {
    border-radius: 8px;
    padding: 1.5rem;
    border: 1px solid #EAECF0;
    box-shadow: 0px 1px 3px rgba(16, 24, 40, 0.1), 0px 1px 2px rgba(16, 24, 40, 0.06);
  }
  .data {
      justify-content: space-between;
  }
  .growth-rate {
      color: hsla(220, 13%, 46%, 1);
  }
  .rise {
      color: hsla(155, 96%, 24%, 1);
  }
  .fall {
      color: hsla(4, 76%, 40%, 1)
  }
</style>