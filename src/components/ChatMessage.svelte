<script>
    export let message;
  </script>
  
  <div class="message-container {message.isMine ? 'mine' : 'theirs'}" style="justify-content: {message.isMine ? 'flex-end' : 'flex-start'};">
    <span class="text" style="background-color: {message.isMine ? '#ffe6cc' : '#fff'};">{message.text}</span>
  </div>
  
  <style>
    .message-container {
      display: flex;
      margin: 0.5rem 0;
    }
  
    .text {
      display: inline-block; /* 確保背景只包裹文字 */
      padding: 0.8rem;
      border-radius: 10px;
      max-width: 60%; /* 設定最大寬度，避免訊息過寬 */
      word-wrap: break-word; /* 長字自動換行 */
      word-break: break-word;
      color: #333;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* 為訊息增加層次感 */
    }
  </style>
  