<template lang="pug">
    #search
        input( type="text" placeholder="Search Facebook" )
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#search {
  position: relative;

  &::after {
    content: "\f002";
    font-family: "Font Awesome 5 Free";
    position: absolute;
    height: 100%;
    left: 16px;
    top: 0;
    font-weight: 900;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #969696;
  }

  input {
    height: 40px;
    border-radius: 90px;
    background: #353535;
    border: none;
    width: 240px;
    position: relative;
    padding-left: 35px;
    font-weight: 400;

    &:focus {
      font-weight: 300;
    }

    &::placeholder {
      font-size: 15px;
      color: #969696;
    }
  }
}
</style>
