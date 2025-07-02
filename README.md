<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Dog Image</title>
</head>
<body>
  <h2>Here's a Random Dog for You!</h2>
  <img id="dogImage" src="" alt="Cute dog" style="max-width: 400px; display: block; margin-bottom: 10px;">
  <button onclick="fetchDogImage()">Get Another Dog</button>

  <script>
    async function fetchDogImage() {
      try {
        const res = await fetch("https://dog.ceo/api/breeds/image/random");
        if (!res.ok) throw new Error(`HTTP error! Status: ${res.status}`);
        
        const { message } = await res.json();
        document.getElementById("dogImage").src = message;
      } catch (err) {
        console.error("Error fetching dog image:", err);
      }
    }


    fetchDogImage();
  </script>
</body>
</html>
