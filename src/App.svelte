<script>
    import ChatInput from './components/ChatInput.svelte';
    import ChatMessage from './components/ChatMessage.svelte';
  
    let messages = [
      { user: '小菊(Hinagiku)', text: '首先，我想了解你這次寒假的規劃想要做什麼？', isMine: false }
    ];
  
    function addMessage(newMessage) {
      messages = [...messages, { user: 'You', text: newMessage, isMine: true }];
    }
  </script>
  
  <main class="chat-container">
    <div class="chat-messages">
      {#each messages as message}
        <ChatMessage {message} />
      {/each}
    </div>
    <ChatInput onSendMessage={addMessage} />
  </main>
  
  <style>
    @import './app.css';
  </style>
  