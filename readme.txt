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


(to ask)
how to upload videos without them being too heavy
messy output when you write and submit too much text, how to solve it


word-wrap: break-word;
  overflow-wrap: break-word;
  white-space: pre-wrap;
