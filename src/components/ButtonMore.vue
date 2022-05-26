<template>
  <button class="btn">Показать еще</button>
</template>

<script>
export default {
  name: 'button-more'
}
</script>

<style scoped>
.btn {
  background-color: #39B8BA;
  color: white;
  border-radius: 16px;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  font-family: 'Cera Pro';
  width: 150px;
  height: 36px;
  border: none;
  cursor: pointer;
  transition: 0.8s;
}
.btn:hover{
  background-color: #07e5e8;

}
@media (max-width: 1024px) {
  .btn{
    font-size: 26px;
    line-height: 35px;
    width: 221px;
    height: 53px;
    border-radius: 23.6053px;
  }
}
@media (max-width: 360px) {
  .btn{
    font-size: 16px;
    line-height: 35px;
    width: 100%;
  }
}


</style>