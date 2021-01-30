<template>
    <h1>Editor component</h1>

    <ckeditor
        :editor="editor"
        v-model="editorData"
        :config="editorConfig"
    >
    </ckeditor>
</template>

<script>
import CKEditor from '@ckeditor/ckeditor5-vue';
import BalloonEditor from '@ckeditor/ckeditor5-editor-balloon/src/ballooneditor';
    import EssentialsPlugin from '@ckeditor/ckeditor5-essentials/src/essentials';
    import BoldPlugin from '@ckeditor/ckeditor5-basic-styles/src/bold';
    import ItalicPlugin from '@ckeditor/ckeditor5-basic-styles/src/italic';
    import LinkPlugin from '@ckeditor/ckeditor5-link/src/link';
    import ParagraphPlugin from '@ckeditor/ckeditor5-paragraph/src/paragraph';

export default {
    components: {
        ckeditor: CKEditor.component
    },
    data() {
        return {
            editor: BalloonEditor,
            editorData: '<p>Content of the editor</p>',
            editorConfig: {

                plugins: [
                        EssentialsPlugin,
                        BoldPlugin,
                        ItalicPlugin,
                        LinkPlugin,
                        ParagraphPlugin
                ],
                toolbar: {
                    items: [
                        'bold',
                        'italic',
                        'link',
                        'undo',
                        'redo'
                    ]
                }
            },
        }
    }
}
</script>
