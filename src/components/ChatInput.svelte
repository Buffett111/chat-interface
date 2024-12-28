<script>
/**
	 * @type {(arg0: string) => void}
	 */
 export let onSendMessage; // Define a prop for the callback function

let input = '';

function sendMessage() {
    if (input.trim() !== '') {
    onSendMessage(input); // Call the callback function with the input value
    input = ''; // Clear the input field
    }
}
</script>

<div class="input-container">
<input
    type="text"
    bind:value={input}
    placeholder="Type your message...(max 500 characters)"
    on:keydown={(e) => e.key === 'Enter' && sendMessage()}
/>
<button on:click={sendMessage}>Send</button>
</div>

<style>
.input-container {
    display: flex;
    gap: 0.5rem;
    padding: 1rem;
    border-top: 1px solid #ddd;
    background-color: #fff;
}

input {
    flex: 1;
    padding: 0.8rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 8px;
}

button {
    padding: 0.8rem 1.2rem;
    background-color: #ff5722;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #e64a19;
}
</style>
  