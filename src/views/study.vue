<template>
  <div>
     <text  @click='recordStart' style='fontSize: 50px'>我是recordStart按钮</text>
     <text  @click='recordStop' style='fontSize: 50px'>我是recordStop按钮</text>
     <text  @click='toOpus' style='fontSize: 50px'>我是toOpus按钮</text>
     <text  @click='readBytes' style='fontSize: 50px'>我是toOpus按钮</text>
  </div>
</template>

<script>
  const RecordVoice = weex.requireModule("RecordVoice");
  const Media = weex.requireModule("Media");
  const link = weex.requireModule("LinkModule");
  const globalEvent = weex.requireModule('globalEvent');
  const navigator =  weex.requireModule('navigator');
  const FileModule =  weex.requireModule('FileModule');
  export default {
    data() {
      return {
      }
    },
    created() {
        var that = this
        globalEvent.addEventListener("androidback", function (e) {
            navigator.close()
        });
    },
    methods: {
        readBytes(){
            link.getSdcardAppDir([], (src)=> {
                FileModule.readBytes(src + "/weex_test_voice.amr", (res) => {
                    this.$alert(typeof res[0]);
                }, () => {})
            }, (err) => {

            })
        },
        recordStart(){
            link.getSdcardAppDir([], (src)=> {
                RecordVoice.recordStart([{"savePath": src + "/weex_test_voice.amr"}], () => {
                }, () => {
                });
            }, (err) => {

            })
        },
        recordStop(){
            RecordVoice.recordStop([], (res) => {}, (err) => {})
        },
        toOpus(){
            link.getSdcardAppDir([], (src)=> {
                Media.toOpus([{"input": src + "/weex_test_voice.amr", "output": src + "/weex_test_voice.opus"}], (res) => {}, (err) => {})
            }, (err) => {

            })
        }
    }
  }
</script>

<style lang="css" src="../css/common.css"></style>
<style>
</style>