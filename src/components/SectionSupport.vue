<template>
  <div class="section">
    <div class="section__container">
      <h5 class="section__title">
        Проекты поддержки
      </h5>
      <div class="section__cards">
        <CardSupport v-for="(support, index) in supports"
                :key="support.id"
                 :index="index"
              :support="support">
            {{ support.title }}
        </CardSupport>

      </div>
      <div class="section__more">
        <button-more  @click="loadMore"></button-more>
      </div>
    </div>
  </div>
</template>

<script>
import ButtonMore from "@/components/ButtonMore";
import CardSupport from "@/components/CardSupport"
export default {
  name: 'SectionBalance',
  components: {
    CardSupport,
    ButtonMore,
  },
  data() {
    return {
      lengthCards: 6,
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
        {
          title: "Тинькоф",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
        {
          title: "Сельхозбанк",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
        {
          title: "Открытие",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
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
        {
          title: "Тинькоф",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
        {
          title: "Сельхозбанк",
          progress: 25,
          burning_count: 33,
          inwork_count: 58,
          time_fakt: "04:43"
        },
        {
          title: "Открытие",
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
      if (this.lengthCards > this.support.length) return;
      this.lengthCards = this.lengthCards + 6;
    },
  },
  computed: {
    supports() {
      return this.support.slice(0, this.lengthCards);
    },
  },
}

</script>

<style lang="scss">
@font-face {
  font-family: 'Cera Pro';
  src: local('CeraPro-Medium'), local('CeraPro-Medium'),
  url('@/assets/CeraPro-Medium.woff') format('woff');
  font-weight: 500;
}
.section{
  padding-left: 5px;
  padding-right: 5px;
  &__container{
    max-width: 1300px;
    width: 100%;
    margin: 0 auto;
  }
  &__title{
    font-weight: 500;
    font-size: 26px;
    line-height: 32px;
    color: #333333;
    font-family: 'Cera Pro';
  }
  &__cards{
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(1, 1fr);
    gap: 12px 12px;
    margin-top: 49px;
  }
  &__more{
    display: flex;
    justify-content: center;
    margin-top: 49px;
  }
}
@media (max-width: 1024px) {
  .section{
    &__title{
      font-size: 38.3586px;
      line-height: 47px;
    }
    &__cards{
      grid-template-columns: repeat(3, 1fr);
      grid-column-gap: 12px;
      grid-row-gap: 12px;

      margin-top: 72px;
      gap: 18px 0px;
    }
    &__more{
      margin-top: 72.29px;
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
      grid-template-columns: repeat(1, 1fr);
      gap: 24px 0;
    }
    &__more{
      margin-top: 46px;
    }
  }
}

</style>
