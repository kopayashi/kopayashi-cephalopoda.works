<template>
    <div class="px-4 text-left max-w-[650px] mx-auto ">
        <h3 class="mt-4 font-bold" :class="titleClass">{{ title }}</h3>
        <p class="mt-4" :class="contentClass" v-html="formattedContent"></p>
        <hr class="mt-2">
    </div>
</template>
<script>
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'InfoCard',
    props: {
        title: {
            type: String,
            required: true,
        },
        content: {
            type: String,
            required: true,
        },
        titleClass: {
            type: String,
        },
        contentClass: {
            type: String,
        },
    },
    computed: {
        // 改行コードを改行タグに変更
        formattedContent() {
            return this.content.replace(/\r?\n|\r/g, '</p><p class="mt-4">');
        }
    }
});
</script>
<style scoped>
</style>
