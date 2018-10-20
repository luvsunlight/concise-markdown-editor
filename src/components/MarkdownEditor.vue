<template>
    <div class="markdown-editor">
        <textarea 
            class="edit panel" 
            id="markdown-edit-panel"
            v-model="text"
            v-focus
            :placeholder="markdownHint"
        ></textarea>
        <div
            class="compiled panel markdown-body"
            v-html="compiledText"
        ></div>
        <slot/>
    </div>
</template>

<script>
import marked from "marked";
require("markdown.css/markdown.css");

export default {
    props: {
        className: String
    },
    data() {
        return {
            text: "# Hello",
            markdownHint: `Markdown Usage Example: 
            1. emphasize 
                ** InputText **
            2. blockquote
                > InputText 
            3. different title
                # InputText
                ## InputText
                ### InputText
            4. link
                [link description](link url)
            ...
            For more info, please visit website https://en.wikipedia.org/wiki/Markdown
            `
        };
    },
    methods: {
    },
    computed: {
        compiledText() {
            return marked(this.text, { sanitize: true });
        }
    },
    directives: {
        focus: {
            inserted: el => {
                el.focus();
            }
        }
    }
};
</script>

<style scoped>
.markdown-editor {
    display: flex;
}

.panel {
    flex: 1;
    min-height: 500px;
    padding: 20px;
}

.edit {
    border: none;
    outline: none;
    background: #f0f2f4;
    color: rgb(61, 83, 104);
    font-size: 16px;
    box-sizing: border-box;
    resize: none;
}

.compiled {
    border: 1px solid #ddd;
    text-align: left;
}

::-webkit-input-placeholder {
    color: #ccc;
    line-height: 20px;
    font-style: italic;
}
</style>   