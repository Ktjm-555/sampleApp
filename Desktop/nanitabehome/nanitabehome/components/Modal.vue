<script>

export default {
props: {
    isActive: Boolean,
    todayRecipeTitle: String,
    todayRecipeUrl: String,
    todayRecipeImg: String,

}

}
</script>
<template>
    <div class="modal" :class="{'is-active' : isActive}">
        <div class="modal-background"></div>
        <div class="modal-card">
            <header class="modal-card-head">
                <p class="modal-card-title">๐ดๆฌๆฅใฏใใ้ฃในใ๐</p>
                <button class="delete" aria-label="close" @click="$emit('closeResModal'); $emit('clickOk')"></button>
            </header>
            <section class="modal-card-body">
                <div class="content">
                    <h2 v-if="isActive">{{ todayRecipeTitle }}</h2>
                    <img v-if="isActive" class="modal_img" :src="todayRecipeImg">
                    <h3>ไฝใๆนใฏใใกใ๐ป</h3>
                    <a v-if="isActive" target="_blank" :href="todayRecipeUrl" >{{ todayRecipeUrl }}</a>
                </div>
            </section>
            <footer class="modal-card-foot">
                <button class="button is-warning is-rounded"  @click="$emit('closeResModal'); $emit('clickOk')">้ใใ</button>
            </footer>
        </div>
    </div>
</template>
<style lang="scss">
.modal {
    animation-name: fade;
    animation-duration: 0.5s;

    @keyframes fade {
        0%{
            opacity: 0;
        }
        100%{
            opacity: 1;
        }
    }

    .modal-card {
        text-align: center;


        .modal_img {
            width: 200px;
            height: 200px;
            object-fit: cover;
            margin: 0 auto;
            display: block;
        }

    }

    .button {
        margin: 0;
    }
}
</style>