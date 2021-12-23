<template>
    <div class="header">
        <div class="logo">
            <i class="fab fa-spotify"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: "Header",
}
</script>

<style scoped lang="scss">
@import '../style/generals.scss';

.header{
    background-color: $brand-primary-color;

    .logo{
        padding: 20px 40px;

        i{
            font-size: 50px;
            color: #1bd760;
        }
    }
}
</style>

