<template>
  <div class="chat-home">
    <chat-header />
    <chat-box />
    <chat-notify />
  </div>
</template>

<script>
// COMPONENTS
import ChatNotify from '@/components/ChatNotify'
import ChatBox from '@/components/ChatBox'

// HEADER
import ChatHeader from '@/components/ChatHeader'

export default {
  name: 'Home',
  components: {
    ChatHeader,
    ChatBox,
    ChatNotify
  }
}
</script>
<style lang="sass" scoped>
@import '@/sass/style.sass'
.chat-home
  width: 1300px
  height: 90vh
  top: calc((100% - 90vh) / 2)
  position: fixed
  margin-right: calc((100% - 1300px) / 2)
  margin-left: calc((100% - 1300px) / 2)
  background: white
  box-shadow: 0 0 10px 0 rgba(0,0,0,0.2)
  display: flex
  flex-flow: row
  justify-content: flex-start
  align-items: flex-start
  z-index: 1
  border-radius: $radius
  overflow: hidden
</style>
