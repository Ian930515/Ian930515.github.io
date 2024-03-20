<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random String Generator</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
  <style>
    .blockquote {
      border: 1px solid #ccc;
      padding: 10px;
    }
  </style>
</head>
<body>
  <div id="container" tabindex="0" class="blockquote text-nowrap"></div>

  <script>
    window.onload = function() {
      var container = document.getElementById('container');
      container.textContent = generateRandomString(0, 2); // Generate 0 to 2 random characters initially
      
      window.addEventListener("keyup", function(e) {
        var str = container.textContent;
        if (e.key === str.charAt(0)) { // If typed character matches the first character
          container.textContent = str.substring(1); // Remove the matched character
        } else {
          container.textContent += generateRandomString(1, 3); // Add 1 to 3 random characters
        }
      });

      function generateRandomString(minLength, maxLength) {
        var length = Math.floor(Math.random() * (maxLength - minLength + 1)) + minLength;
        var result = '';
        var characters = 'abcdefghijklmnopqrstuvwxyz';
        for (var i = 0; i < length; i++) {
          result += characters.charAt(Math.floor(Math.random() * characters.length));
        }
        return result;
      }
    };
  </script>
</body>
</html>
