<template>
  <div class="card">
    <div class="card__border" :class="danger">
      <div class="card__title">{{ support.title }}</div>

      <div class="card__content">
        <div class="card__wrapper-count">
          <div class="card__inwork">{{ support.inwork_count}}</div>
          <span class="card__burning">{{ support.burning_count}}
          <svg class="card__burning--svg" width="9" height="11" viewBox="0 0 9 11" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M7.98628 5.74801C7.20128 3.70801 4.40628 3.59801 5.08128 0.633007C5.13128 0.413007 4.89628 0.243007 4.70628 0.358007C2.89128 1.42801 1.58628 3.57301 2.68128 6.38301C2.77128 6.61301 2.50128 6.82801 2.30628 6.67801C1.40128 5.99301 1.30628 5.00801 1.38628 4.30301C1.41628 4.04301 1.07628 3.91801 0.931277 4.13301C0.591277 4.65301 0.246277 5.49301 0.246277 6.75801C0.436277 9.55801 2.80128 10.418 3.65128 10.528C4.86628 10.683 6.18128 10.458 7.12628 9.59301C8.16628 8.62801 8.54628 7.08801 7.98628 5.74801ZM3.34628 8.26301C4.06628 8.08801 4.43628 7.56801 4.53628 7.10801C4.70128 6.39301 4.05628 5.69301 4.49128 4.56301C4.65628 5.49801 6.12628 6.08301 6.12628 7.10301C6.16628 8.36801 4.79628 9.45301 3.34628 8.26301Z" fill="#FC6E6A"/>
</svg>
 </span>
        </div>
        <div class="card__wrapper-special">
          <div class="card__progressbar">
            <span class="card__progressbar--fill" :class="dangerFill" style="width: 40%"></span>
          </div>
          <div class="card__time">{{ support.time_fakt}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardSupport.vue",
  props: ['support', 'support.progress'],
  data() {
    return {
    }
  },
  computed:{
    // eslint-disable-next-line vue/return-in-computed-property
    danger(){
      if((this.support.inwork_count < 20)) {
        return 'card__border--danger';
      }
    },
    dangerFill(){
      if((this.support.inwork_count < 10)) {
        return 'card__progressbar--fill-danger';
      }
      else {
        return null
      }
    }
  }

}
</script>

<style scoped lang="scss">
.card{
  padding: 18px 24.04px 19.18px 13.75px;
  width: 10.783333333333331vw;
  min-height: 103px;
  background: #FFFFFF;
  box-shadow: 0px 3.4364px 13.7456px rgba(130, 150, 180, 0.32);
  border-radius: 13px;
  cursor: pointer;
  transition: 0.5s;
  &__border{
    border-left: 3px solid #39B8BA;
    padding: 7px 20px 10px 7px;
    min-height: 65px;
    &--danger{
      border-left: 3px solid #FC6E6A;
    }
  }
  &__title{
    font-family: 'Cera Pro';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #6E6E6E;
  }
  &__content{
    display: flex;
    justify-content: space-between;
    align-items: start;
    margin-top: 7px;
  }
  &__wrapper-count{
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  &__inwork{
    font-family: 'Cera Pro';
    font-weight: 500;
    font-size: 42px;
    line-height: 17px;
    color: #242532;
  }
  &__burning{
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    font-family: 'Cera Pro';
    font-weight: 500;
    font-size: 26px;
    padding-left: 4px;
    line-height: 17px;
    color: #FC6E6A;
    &--svg{
      padding-top: 2.87px;
    }
  }
  &__wrapper-special{
    padding-left: 16px;
  }
  &__progressbar{
    height: 10.62px;
    border-radius: 16px;
    width: 3.8671875vw;
    position: relative;
    background-color: #EFEFEF;
    &--fill{
      width: 100%;
      border-radius: 16px;
      display: block;
      height: 100%;
      background-color: #39B8BA;
      position: relative;
    }
    &--fill-danger{
      background-color: red;
    }
  }
  &__time{
    padding-top: 8px;
    font-family: 'Cera Pro';
    font-weight: 500;
    font-size: 18px;
    line-height: 20px;
    color: #909090;
  }
}
.card:hover{
  background-color: #F2F3F3;
}
@media (max-width: 1024px) {
  .card{
    width: 29.830078124999996vw;
    display: flex;
    align-items: center;
    min-height: 152.09px;
    border-radius: 20.3179px;
    padding: 27.02px 36.71px 28.58px 20.32px;
    &__title{
      font-size: 23.6502px;
      line-height: 30px;
    }
    &__content{
      margin-top: 10px;
    }
    &__border{
      border-left: 4px solid #39B8BA;
      padding: 7px 20px 0px 7px;
      min-height: 96.79px;
      &--danger{
        border-left: 3px solid #FC6E6A;
      }
    }
    &__inwork{
      font-size: 62.0818px;
      line-height: 25px;
    }
    &__burning{
      font-size: 38.4316px;
      line-height: 25px;
      &--svg{
        width: 11.82px;
        height: 15.15px;
      }
    }
    &__wrapper-special{
      padding-left: 23.65px;
    }
    &__progressbar{
      width: 10.71875vw;
      height: 15.69px;
    }
    &__time{
      font-size: 26.6065px;
      line-height: 30px;
    }
  }
}
@media (max-width: 360px) {
  .card{
    width: 100%;
    padding: 8px 20px 0px 20px;
    height: 14vh;
    &__progressbar{
      width: 30.278vw;
      height: 15.69px;
    }
    &__border{
      border-left: 4.43442px solid #39B8BA;
      padding: 15px 20px 0px 7px;
      min-height: 96.79px;
      &--danger{
        border-left: 3px solid #FC6E6A;
      }
    }
  }

}

</style>