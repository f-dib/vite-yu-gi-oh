<script>
export default {
    name: 'AppNav',
}
</script>

<template>
    <div class="my_nav">
        <div class="my_img_box">
            <img class="img_fluid img_obj" src="../../public/img/yu-gi-oh.png" alt="">
        </div>
        <h1>Yu-Gi-Oh Api</h1>
    </div>
</template>

<style lang="scss">
    .my_nav{
        display: flex;
        align-items: center;
        gap: 20px;

        padding: 30px;

        background-color: white;
        color: black;

        .my_img_box {
            width: 60px;
            height: 30px;

            .img_obj{
                height: 100%;
                object-fit: cover;
            }
        }
    }
</style>