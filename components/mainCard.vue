<template>
    <div class="info-mainCard">
        <div class="info-menu">
            <span class="info-menu-items" v-for="(info, index) in info_display" :ref="`menu-${index}`" :key="index"
                @click="selectInfo(index)" :class="{ selected: index === infoIndex }">
                {{ info }}
            </span>
            <div class="dropdown">
                <button>
                    更多
                </button>
                <ul>
                    <li v-for="item_more in info_more" :key="item_more">
                        <a href="">{{ item_more }}</a>
                    </li>
                </ul>
            </div>
        </div>
        <div class="info-news-container">
            <div v-for="(item, index) in news" class="info-news-card" :key="index">
                <div class="info-news-card-title">
                    <span>{{ item.title }}</span>
                </div>
                <div class="info-news-card-preview">
                    <span>{{ item.preview }}</span>
                </div>
                <div class="info-news-card-detail">
                    {{ item.school }} · {{ item.time }} · {{ item.views }}次阅读
                </div>
                <div style="border-top: 1px solid #ccc;width:auto;margin-top: .5em;transform: translateX(-2em);">
                </div>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">
import { summaryType } from "../public/summaryType"

const news: summaryType[] = [
    {
        title: "郑州大学2023年高校专项计划招生简章",
        time: "2023-04-09 17:37",
        views: 2147,
        school: "郑州大学",
        preview: "郑州大学是国家“211工程”重点建设高校、世界一流大学建设高校和“部省合建”高校。根据《关于做好2023年重点高校招生专项计划工作的通知》....",
        image: "",
    },
    {
        title: "郑州大学2023年高校专项计划招生简章",
        time: "2023-04-09 17:37",
        views: 2147,
        school: "郑州大学",
        preview: "郑州大学是国家“211工程”重点建设高校、世界一流大学建设高校和“部省合建”高校。根据《关于做好2023年重点高校招生专项计划工作的通知》....",
        image: "",
    }, {
        title: "郑州大学2023年高校专项计划招生简章",
        time: "2023-04-09 17:37",
        views: 2147,
        school: "郑州大学",
        preview: "郑州大学是国家“211工程”重点建设高校、世界一流大学建设高校和“部省合建”高校。根据《关于做好2023年重点高校招生专项计划工作的通知》....",
        image: "",
    }, {
        title: "郑州大学2023年高校专项计划招生简章",
        time: "2023-04-09 17:37",
        views: 2147,
        school: "郑州大学",
        preview: "郑州大学是国家“211工程”重点建设高校、世界一流大学建设高校和“部省合建”高校。根据《关于做好2023年重点高校招生专项计划工作的通知》....",
        image: "",
    }, {
        title: "郑州大学2023年高校专项计划招生简章",
        time: "2023-04-09 17:37",
        views: 2147,
        school: "郑州大学",
        preview: "郑州大学是国家“211工程”重点建设高校、世界一流大学建设高校和“部省合建”高校。根据《关于做好2023年重点高校招生专项计划工作的通知》....",
        image: "",
    },
];



const info_display = [
    '综合评价录取',
    '强基计划',
    '艺术生',
    '体育生',
    '专项计划',
    '空军招飞',
]
const info_more = [
    '更多信息1',
    '更多信息2',
    '更多信息3',
    '更多信息4',
]
const topic_summary = [
    '2023 单独招生院校汇总',
    '2023 强基计划招生简章汇总'
    , '2023 单独招生院校汇总'
    , '2023 强基计划招生简章汇总'
    , '2023 单独招生院校汇总'
    , '2023 强基计划招生简章汇总'
]
const infoIndex = ref(-1);
const selectInfo = function (index: number) {
    infoIndex.value = index;
}
</script>

<style scoped lang="scss">
.info-mainCard {
    flex-direction: column;
}

.info-menu {
    text-align: center;
    display: flex;
    align-items: center;
    justify-content:flex-start;
    height: 51px;
    background: #F16E25;
    max-width: 900px;
    border-radius: 12px 12px 0px 0px;
    flex: 70%;
    &-items {
        margin: 0 1.2em;
        width: auto;
        height: 24px;
        font-weight: 400;
        font-size: 20px;
        line-height: 24px;
        /* identical to box height */
        color: #FFFFFF;
    }

    .selected {
        align-items: center;
        text-align: center;
        display: flex;
        height: 2em;
        
        background: #FFEADE;
        box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        border-radius: 6px;
        color: #4D5459;
    }

    .el-icon--right {
        left: -0.5em;
        top: 0.1em;
    }
}

.dropdown {
    position: relative;
    justify-content: center;
    align-items: center;
    margin-left: 2em;

    button {
        background-color: #F16E25;
        color: #fff;
        font-size: 20px;
        border: none;
        padding: 5px 10px;
        cursor: pointer;
    }

    ul {
        position: absolute;
        top: 2.3em;
        background: #FFFFFF;
        list-style: none;
        margin: 0;
        padding: 0;
        display: none;
        width: 7em;
        box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        border-radius: 6px;

        li {
            margin-bottom: 10px;
            font-size: 20px;
            text-align: center;
            justify-content: center;
            align-items: center;
            height: 30px;

            a {
                color: #333;
                text-decoration: none;
            }
        }
    }
}

.info-news-container {
    position: relative;
    display: flex;
    margin-top: 1em;
    flex-direction: column;
    justify-content: center;

    .info-news-card {
        left: 4%;
        position: relative;
        width: 80%;
        height: 10em;
        margin-top: 2em;

        &-title {
            font-size: 24px;
            line-height: 29px;
        }

        &-preview {
            margin-top: 1.5em;
            width: 74%;
            font-size: 16px;
            line-height: 19px;
            color: #8B8B8B;
        }

        &-detail {
            margin-top: 2em;
        }
    }
}
</style>
  