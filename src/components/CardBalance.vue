<template>
    <div class="card">
      <div class="card__title">{{ balance.title }}</div>
      <div class="card__price" :class="myClass" >{{ balance.sum }} ₽ <span class="card__price-plan">/{{ balance.sum_plan}}</span></div>
    </div>
</template>

<script>
export default {
  name: "CardComponent.vue",
  data() {
    return {
    }
  },
  props: ['balance'],
  computed:{
    // eslint-disable-next-line vue/return-in-computed-property
    myClass(){
      if(this.balance.sum_plan > this.balance.sum_plan) {
        return 'text-danger';
      }
      return 'text-danger';
    }
  }

}
</script>

<style scoped lang="scss">

.card{
  align-items: center;
    padding: 24.11px 20px 0px 13.75px;
    width: 10.783vw;
    min-height: 103px;
    background: #FFFFFF;
    cursor: pointer;
     box-shadow: 0px 3.4364px 13.7456px rgba(130, 150, 180, 0.32);
     border-radius: 13px;
  transition: 0.5s;

  &__title{
    font-family: 'Cera Pro';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #6E6E6E;
  }
  &__price{
    margin-top: 6.87px;
    font-family: 'Cera Pro';
    font-style: normal;
    font-weight: 500;
    font-size: 26px;
    line-height: 27px;
    color: #39B8BA;
  }
  &__price-plan{
    font-size: 16px;
    line-height: 17px;
    color: #6E6E6E;
  }
}
.card:hover{
  background-color: #F2F3F3;
}
@media (max-width: 1024px) {
  .card{
    width: 28vw;
    min-height: 152.09px;
    border-radius: 20.3179px;
    &__title{
      font-size: 23.6053px;
      line-height: 30px;
    }
    &__price{
      font-size: 38.3586px;
      line-height: 41px;
    }
  }
}
@media (max-width: 360px) {
  .card{
    width: 100%;
    height: 14vh;
  }
}

</style>