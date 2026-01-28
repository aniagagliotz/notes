<script>
  const form = document.getElementById('outer-circle');
  const textarea = document.getElementById('textinput');
  const output = document.getElementById('output');

  // Load saved content on page load
  const savedText = JSON.parse(localStorage.getItem('savedText')) || [];
  savedText.forEach(text => addText(text));

  form.addEventListener('submit', e => {
    e.preventDefault();

    const value = textarea.value.trim();
    if (!value) return;

    addText(value);

    // Save to localStorage
    savedText.push(value);
    localStorage.setItem('savedText', JSON.stringify(savedText));

    textarea.value = '';
  });

  function addText(text) {
    const p = document.createElement('p');
    p.textContent = text; // text-only (safe)
    output.appendChild(p);
  }
</script>

(for me to remember)
<p>
<img src="Isrif.jpeg" style="top: 60px; left:280px;" onclick="toggleDiv('text-i')">
<div class="textbox" id="text-i" style="top:150px; left:300px;"> 
<span id="fa" class="fa-text"> إصرف ما في الجيب يأتيك ما في الغيب</span> -> ISRIF MA FI AL-JAYB, YA'TI MA FI AL-GHAYB
<br>by Ameer
<br><br>
Spend and God will send.
An Arab proverb that invites one not to be 
stingy or overly anxious about 
future finances, trusting that one’s 
needs will be met.
</div>
</p>

(to ask)
how to upload videos without them being too heavy
messy output when you write and submit too much text, how to solve it