<script setup>

</script>

<template>
  <div class="load-wrap">
    <div class="loader loader--style3" title="2">
      <svg version="1.1" id="loader-1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
           x="0px" y="0px"
           width="60px" height="60px" viewBox="0 0 50 50" style="enable-background:new 0 0 50 50;"
           xml:space="preserve">
  <path fill="#000"
        d="M43.935,25.145c0-10.318-8.364-18.683-18.683-18.683c-10.318,0-18.683,8.365-18.683,18.683h4.068c0-8.071,6.543-14.615,14.615-14.615c8.072,0,14.615,6.543,14.615,14.615H43.935z">
    <animateTransform attributeType="xml"
                      attributeName="transform"
                      type="rotate"
                      from="0 25 25"
                      to="360 25 25"
                      dur="0.6s"
                      repeatCount="indefinite"/>
    </path>
  </svg>
    </div>

    <p class="loading-txt">LOADING CARDS...</p>
  </div>
</template>

<style scoped>
.load-wrap {
  margin-top: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.loading-txt {
  margin: 0;
  padding-left: 10px;
  color: #FF6700;
  font-size: 1.3rem;
  font-weight: 600;
  white-space: nowrap;
}

.loader {
  display: flex;
  align-items: center;
  text-align: center;
  height: 100px;
}

/*
  Set the color of the icon
*/
svg path,
svg rect {
  fill: #FF6700;
}
</style>