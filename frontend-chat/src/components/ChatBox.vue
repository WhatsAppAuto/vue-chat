<template>
  <section class="chat-box">
    <header class="chat-box__header">
      <section class="chat-box__header-user">
        <img :src="`${baseURL}img/chat.png`" alt="Friend">
        <h2>Tio Mark</h2>
      </section>

      <nav class="chat-box__header-options">
        <ul class="chat-box__header-options-ul">
          <li><span class="fas fa-paperclip"></span></li>
        </ul>
      </nav>
    </header>

    <article class="chat-box__content"
      :style="{ 'background-image': `url(${baseURL}img/background-chat.png)` }">
      <section class="chat-box__conversation">
        <div class="chat-box__message">
          <p class="chat-box__message-text"> Escrevi alguma coisa aqui </p>
        </div>

        <div class="chat-box__message chat-box__message-receive">
          <p class="chat-box__message-text"> Escrevi outra coisa </p>
        </div>

        <div class="chat-box__message">
          <p class="chat-box__message-text">
            Escrevi alguma coisa aqui só pra ocupar espaço e ver até onde vai a largura desse texto
          </p>
        </div>
      </section>
    </article>

    <section class="chat-box__form">
      <input type="text" placeholder="Type a message">
      <button><span class="fas fa-chevron-right"></span></button>
    </section>
  </section>
</template>

<script>
import basePath from '@/utils/baseURL'

export default {
  computed: {
    baseURL () {
      return basePath.path
    }
  }
}
</script>

<style lang="sass" scoped>
@import '@/sass/style.sass'

.chat-box
  width: calc(100% - 400px)
  display: flex
  flex-flow: column
  position: relative
  .chat-box__header
    width: calc(100% - 40px)
    padding: 10px 20px
    height: 50px
    display: flex
    flex-flow: row
    justify-content: space-between
    align-items: center
    background: #ececec
    border-top-right-radius: $radius
    box-shadow: 10px 1px 10px 0 rgba(0, 0, 0, 0.22)
    z-index: 1
    .chat-box__header-user
      display: flex
      flex-flow: row
      justify-content: flex-start
      align-items: center
      img
        width: 50px
        border-radius: 50%
      h2
        font-size: 16px
        margin-left: 10px
        font-weight: 100
    .chat-box__header-options
      margin-right: 20px
      .chat-box__header-options-ul
        li
          list-style: none
          cursor: pointer
          span
            font-size: 20px
            color: $iconColor
  .chat-box__content
    width: 100%
    height: calc(90vh - 70px)
    background-repeat: no-repeat
    background-size: 100%
    background-color: #fff
    display: flex
    justify-content: flex-start
    align-items: flex-start
    .chat-box__conversation
      width: 100%
      height: calc(100% - 80px)
      display: flex
      flex-flow: column
      justify-content: flex-end
      align-items: flex-start
      .chat-box__message
        width: calc(100% - 40px)
        padding: 0 20px
        align-self: flex-end
        display: flex
        justify-content: flex-end
        .chat-box__message-text
          align-self: flex-end
          max-width: 60%
          background-color: $messageBackgroundColor
          padding: 10px
          border-radius: $radius
          border-top-right-radius: 0
          color: $messageTextColor
          position: relative
          font-size: 15px
          margin: 5px 0
          box-shadow: 0 0 10px rgba(0,0,0,0.2)
          text-align: left
          &::after
            content: ''
            position: absolute
            top: 0
            right: -10px
            width: 0
            border: 10px solid
            border-color: $messageBackgroundColor transparent transparent transparent
      .chat-box__message-receive
        justify-content: flex-start
        .chat-box__message-text
          background-color: #fff
          border-top-left-radius: 0
          &::after
            content: ''
            right: unset
            left: -10px
            width: 0
            border-color: #fff transparent transparent transparent
  .chat-box__form
    position: absolute
    bottom: 20px
    width: 100%
    display: flex
    justify-content: center
    align-items: center
    input
      width: calc(80% - 20px)
      height: calc(50px - 20px)
      padding: 10px
      border: 1px solid #ccc
      border-radius: $radius
      box-shadow: 0 0 10px 0 rgba(0,0,0,0.2)
      color: $inputTextColor
      &::placeholder
        color: $iconColor
    button
      width: 50px
      height: 50px
      border-radius: $radius
      border: none
      background: $primaryColor
      margin-left: 10px
      cursor: pointer
      span
        color: white

</style>
