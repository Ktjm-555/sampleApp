<script>
export default {
    props: {
        recipeRankingList: Array,
    }
}
</script>
<template>
    <aside class="box side">
        <h2>週間楽天レシピランキング</h2>
        <div class="side_box" v-for="item in recipeRankingList" :key="recipeRankingList">
            <article class="media">
                <div class="media-left">
                    <figure class="image image_box is-64x64">
                        <img :src="item.foodImageUrl" alt="Image">
                    </figure>
                </div>
                <div class="media-content">
                    <div class="content">
                        <p>
                        {{ item.rank }}位<br>
                        <a target="_blank" :href="item.recipeUrl">{{ item.recipeTitle }}</a>
                        <br>
                        </p>
                    </div>
                </div>
            </article>
        </div>
        <div class="information">
            提供：<a href="https://recipe.rakuten.co.jp/">楽天レシピ</a>
        </div>
    </aside>
</template>
<style lang="scss">
.side {
    // margin: 20px 0px 20px 30px;
    margin: 20px;
    width: 350px;
    height: 675px;

    h2 {
        text-align: center;
    }

    .side_box {

        .media {
            display: flex;
            width:fit-content;
            margin-top: 15px;
            height: 100px;



            .media-left {
                min-width: 60px;

                .image_box {
                    display: flex;
                    padding-left: 5px;
                }
            }
        }

        p {
            font-size: 15px;
            display: block;
            padding: 0 5px;
        }

        img {
            display: block;
        }
    }

    .information {
        margin-top: 10px;
        text-align: center;
    }
}

@media screen and ( max-width:479px ) {
    .main_wrap {

        .side {
            box-sizing: border-box;
            margin: 5px;
            width: 99%;
            height: 100%;
            
        }
    }
}
</style>
