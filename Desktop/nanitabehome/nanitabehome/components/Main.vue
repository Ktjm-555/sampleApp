<template>
	<main>
        <div class="main_wrap">
            <slot></slot>
        </div>
    </main>
</template>
<style lang="scss">
html {
    position: relative;
    padding-bottom: 50px;
    min-height: 100vh;
    box-sizing: border-box;
    background-color: #FCF4EC;
}

main {
    width: 100%;

    .main_wrap {
        margin-right: auto;
        margin-left: auto;
        max-width: 925px;
        display: flex;


        .media {
            margin-top: 20px;
            display: block;

            .main_title {
                text-align: center;
                margin-bottom: 15px;
            }
        }
    }
}


@media screen and ( max-width:479px ) {
    main {
        width: 100%;

        .main_wrap {
            display: block;

            .media {
                margin: 5px;

            }
   
        }
    }

}

</style>