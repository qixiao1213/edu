<template>
    <div class="info-sideCard">
        <div class="info-topicSummary">
            <div class="info-topicSummary-titleBox">
                <span class="info-topicSummary-titleBox-title">专题汇总</span>
                <div class="info-topicSummary-titleBox-rectangle"></div>
            </div>
            <div class="info-topicSummary-itemsBox">
                <div class="info-topicSummary-itemsBox-items" v-for="(summary, index) in topic_summary" :key="index">
                    <div class="info-topicSummary-itemsBox-items-circle">
                        <div>{{ index + 1 }}</div>
                    </div>
                    <div class="info-topicSummary-items-item">{{ summary }}</div>
                </div>
            </div>

        </div>
        <div class="info-placeholder"></div>
    </div>
</template>
<script setup lang="ts">
const topic_summary = [
    '2023 单独招生院校汇总',
    '2023 强基计划招生简章汇总'
    , '2023 单独招生院校汇总'
    , '2023 强基计划招生简章汇总'
    , '2023 单独招生院校汇总'
    , '2023 强基计划招生简章汇总'
]
</script>
<style lang='scss' scoped>
.info-sideCard {
    display: flex;
    flex-direction: column;
    align-items: center;
    width:500px;
    .info-topicSummary {
        position: relative;
        box-sizing: border-box;
        min-height: 25em;
        border: 2px solid rgba(241, 110, 37, 0.3);
        border-radius: 12px;
        justify-content: center;
        width: 80%;
        &-titleBox {
            position: relative;
            top: 1.2em;
            left: 1.2em;
            width: 96px;
            height: 29px;

            &-title {
                color: #484848;
                font-weight: 700;
                font-size: 24px;
                line-height: 29px;
            }

            &-rectangle {
                width: 109px;
                height: 20px;
                background: #fa8b4a8e;
                transform: translateY(-1em);
            }

        }

        &-itemsBox {
            display: flex;
            position: relative;
            flex-direction: column;
            top: 2em;
            left: 1em;

            &-items {
                display: flex;
                flex-direction: row;

                margin-top: 1.5em;

                &-circle {
                    position: relative;
                    width: 26px;
                    height: 26px;
                    margin-right: 1em;;
                    background: #FFAB7C;
                    border-radius: 13px;
                    font-size: 18px;
                    line-height: 22px;
                    /* identical to box height */

                    text-align: center;

                    color: #000000;
                }

                &-item {
                    font-weight: 400;
                    font-size: 16px;
                    line-height: 19px;
                    color: #000000;
                }
            }
        }
    }

    .info-placeholder {
        margin-top: 5em;
        height: 117px;
        width: 80%;
        background-color: #911e1e;
    }
}
</style>