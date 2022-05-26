<template>
  <div class="section">
    <div class="section__container">
      <h5 class="section__title">
        Информация о балансах
      </h5>
      <div class="section__cards">
        <CardBalance   v-for="(balance, index) in balancess"
                         :key="balance.id"
                         :index="index"
                         :balance="balance">
          {{ balances.title }} - {{ balances.sum }} {{ balances.sum_plan}}
        </CardBalance>

      </div>
      <div class="section__more">
        <button-more  @click="loadMore"></button-more>
      </div>
    </div>
  </div>
</template>

<script>
import CardBalance from '@/components/CardBalance'
import ButtonMore from "@/components/ButtonMore";
export default {
  name: 'SectionBalance',
  components: {
    ButtonMore,
    CardBalance,
  },
  data() {
    return {
      lengthCards: 6,
      balances: [
        {
          title: "Сбербанк", sum: 10000, sum_plan: null,
        },
        { title: "Росбанк", sum: 2000, sum_plan: 5000,
        },
        { title: "ВТБ", sum: 100000, sum_plan: 5000,
        },
        { title: "Тинькоф", sum: 100000, sum_plan: 5000,
        },
        { title: "Сельхозбанк", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
        { title: "Открытие", sum: 100000, sum_plan: 5000,
        },
      ],
      support: [
        {
          title: "Сбербанк",
          progress: 25,
          burning_count: 3,
          inwork_count: 58,
          time_fakt: "02:30"
        },
        {
          title: "Росбанк",
          progress: 90,
          burning_count: 7,
          inwork_count: 8,
          time_fakt: "07:20"
        },
        {
          title: "ВТБ",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
      ],

    }
  },
  methods: {
    loadMore() {
      if (this.lengthCards > this.balances.length) return;
      this.lengthCards = this.lengthCards + 6;
    },
  },
  computed: {
    balancess() {
      return this.balances.slice(0, this.lengthCards);
    },
  },
}

</script>

<style scoped lang="scss">
@font-face {
  font-family: 'Cera Pro';
  src: local('CeraPro-Medium'), local('CeraPro-Medium'),
  url('@/assets/CeraPro-Medium.woff') format('woff');
  font-weight: 500;
}
.section{
  &__container{
    max-width: 1300px;
    width: 100%;
    margin: 0 auto;
    border-bottom: 2px solid #DFDCDC;
    padding-bottom: 70px;
  }
  &__title{
    font-weight: 500;
    font-size: 26px;
    line-height: 32px;
    color: #333333;
    font-family: 'Cera Pro';
  }
  &__cards{
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
    gap: 11.55px 12px;
  }
  &__more{
    margin-top: 49px;
    display: flex;
    justify-content: center;
  }
}
@media (max-width: 1024px) {
  .section{
    &__container{
      max-width: 100%;
      border-bottom: none;
      padding-bottom: 0px;
    }
     &__cards {
       margin-top: 72px;
     }
    &__title{
      font-size: 38.3586px;
      line-height: 47px;
    }
    &__cards{
      gap: 18px;
    }
  }
}
@media (max-width: 360px) {
  .section{
    &__title{
      font-size: 24px;
      line-height: 47px;
      text-align: center;
    }
    &__cards{
      display: flex;
      justify-content: flex-start;
      flex-wrap: wrap;
      gap: 24px 0;
    }
  }
}

</style>
