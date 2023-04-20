<template>
    <div class="info-container">
        <main-card></main-card>
        <side-card></side-card>
    </div>
</template>
<style scoped lang="scss">
.info-container {
    display: flex;
    font-family: 'Source Han Sans SC VF';
    font-style: normal;
    & > main-card {
        flex: 70%;
    }
    & > side-card {
        flex: 30%;
    }
    
}
</style>
  