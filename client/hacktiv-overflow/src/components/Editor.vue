<template>
    <div>
        <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
    </div>
</template>

<script>
    import ClassicEditor from '@ckeditor/ckeditor5-build-classic';

    export default {
        name: 'editor',
        props: ['initValue'],
        data() {
            return {
                editor: ClassicEditor,
                editorData: this.initValue,
                editorConfig: {
                   
                }
            };
        },
        watch: {
            initValue(val){
                this.editorData = this.initValue
            }
        },
        methods : {
            emitData(){
                this.$emit('getdata', this.editorData)
            }
        }
    }
</script>