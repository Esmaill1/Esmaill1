<h1>
  Hi, I'm Mohamed <span id="typing"></span>
</h1>

<style>
#typing::after {
  content: " |";
  animation: blink 0.8s infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}
</style>

<script>
const words = ["Backend Developer", "Open Source Contributor", "Python Enthusiast"];
let i = 0;
let j = 0;
let currentWord = "";
let isDeleting = false;
const typingSpan = document.getElementById("typing");

function typeEffect() {
  currentWord = words[i];
  typingSpan.textContent = isDeleting 
    ? currentWord.substring(0, j--) 
    : currentWord.substring(0, j++);

  if (!isDeleting && j === currentWord.length + 1) {
    isDeleting = true;
    setTimeout(typeEffect, 1000);
    return;
  } else if (isDeleting && j === 0) {
    isDeleting = false;
    i = (i + 1) % words.length;
  }
  setTimeout(typeEffect, 120);
}
typeEffect();
</script>
