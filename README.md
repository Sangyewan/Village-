<!DOCTYPE html>
<html>
<head>
  <title>Selected Items - Village Restaurant</title>
  <!-- CSS links -->
  <style>
    /* Add your CSS styles here */
  </style>
</head>
<body>
  <header>
    <h1>Selected Items</h1>
    <p>Items from Village Restaurant</p>
  </header>

  <main>
    <h2>Your Selected Items</h2>
    <ul id="selectedItemsList">
      <!-- Selected items will be displayed here -->
    </ul>
  </main>

  <footer>
    <a href="index.html">Back to Menu</a>
  </footer>

  <script>
    window.onload = function() {
      let selectedItems = localStorage.getItem('selectedItems');
      if (selectedItems) {
        selectedItems = JSON.parse(selectedItems);
        let selectedItemsList = document.getElementById('selectedItemsList');
        
        selectedItems.forEach(item => {
          let listItem = document.createElement('li');
          listItem.textContent = `${item.item} - Nu.${item.price}`;
          selectedItemsList.appendChild(listItem);
        });
      } else {
        let noItemsMessage = document.createElement('p');
        noItemsMessage.textContent = 'No items selected';
        document.getElementById('selectedItemsList').appendChild(noItemsMessage);
      }
    }
  </script>
</body>
</html>
