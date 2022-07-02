<template>
    <header class="header">
        <h1 class="header__title">Добавление товара</h1>
        <select class="header__select">
            <option value="default" selected>По умолчанию</option>
            <option value="min">По цене min</option>
            <option value="max">По цене max</option>
            <option value="name">По наименованию</option>
        </select>
      </header> 
</template>

<style lang="scss" scoped>
    .header {
  display: flex;
  justify-content: space-between;
  
  &__title {
    color: #3F3F3F;
    line-height: 35px;
    font-weight: 600;
    font-size: 28px;
    margin: 0;
    padding: 0;
    @media (max-width: 1270px) {
      font-size: 24px;
    }
  }
  &__select {
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    border: none;
    background-color: #FFFEFB;
    padding: 10px 16px;
    color: #B4B4B4;
    font-size: 12px;
  }
}
</style>