# Sha-does-hair
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Braid Style Price Builder</title>
<style>
  body { font-family: Arial, sans-serif; max-width: 600px; margin: 2rem auto; padding: 1rem; }
  label { display: block; margin: 0.5rem 0 0.2rem; }
  select { width: 100%; padding: 0.4rem; margin-bottom: 1rem; }
  #totalPrice { font-size: 1.5rem; font-weight: bold; margin-top: 1rem; }
</style>
</head>
<body>

<h1>Braid Style Price Builder</h1>

<form id="priceForm">

  <label for="blockSize">Block Size</label>
  <select id="blockSize" required>
    <option value="300">Extra Small</option>
    <option value="250">Small</option>
    <option value="200" selected>Smedium</option>
    <option value="150">Medium</option>
    <option value="100">Large</option>
    <option value="80">Jumbo</option>
  </select>

  <label for="length">Length</label>
  <select id="length" required>
    <option value="0">Shoulder</option>
    <option value="50">Mid Back</option>
    <option value="100">Waist Length</option>
    <option value="150">Bum Length</option>
    <option value="200">Knee Length</option>
  </select>

  <label for="style">Style</label>
  <select id="style" required>
    <option value="50">Knotless</option>
    <option value="30">Twist</option>
    <option value="100">Locs</option>
  </select>

  <label for="colour">Colour</label>
  <select id="colour" required>
    <option value="0">1 Colour</option>
    <option value="30">Colour Mix</option>
  </select>

  <label for="hairLength">Hair Length</label>
  <select id="hairLength" required>
    <option value="50">Short</option>
    <option value="0" selected>Normal Length</option>
  </select>

  <label for="curls">Curls</label>
  <select id="curls" required>
    <option value="20">Bottom Curls Only</option>
    <option value="40">Boho/Goddess Curls Only</option>
    <option value="60">Both Bottom + Boho</option>
  </select>

  <label for="curlMethod">Curl Method</label>
  <select id="curlMethod" required>
    <option value="0">Client Brings Curls</option>
    <option value="10">I Curl the Hairpiece</option>
    <option value="30">I Use My Own Curls</option>
  </select>

</form>

<div id="totalPrice">Total Price: R0</div>

<script>
  const form = document.getElementById('priceForm');
  const totalPriceDisplay = document.getElementById('totalPrice');

  function calculatePrice() {
    const blockSize = Number(form.blockSize.value);
    const length = Number(form.length.value);
    const style = Number(form.style.value);
    const colour = Number(form.colour.value);
    const hairLength = Number(form.hairLength.value);
    const curls = Number(form.curls.value);
    const curlMethod = Number(form.curlMethod.value);

    const total = blockSize + length + style + colour + hairLength + curls + curlMethod;

    totalPriceDisplay.textContent = `Total Price: R${total}`;
  }

  form.addEventListener('change', calculatePrice);
  window.addEventListener('load', calculatePrice);
</script>

</body>
</html>
