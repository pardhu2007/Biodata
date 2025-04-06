<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Biodata Form with Profile Picture</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #eef2f3;
      margin: 0;
      padding: 40px;
    }

    .container {
      background: #fff;
      max-width: 800px;
      margin: auto;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
    }

    .form-section {
      display: flex;
      gap: 30px;
      flex-wrap: wrap;
    }

    .left {
      flex: 1;
      text-align: center;
    }

    .left img {
      width: 200px;
      height: 200px;
      object-fit: cover;
      border-radius: 50%;
      border: 2px solid #ccc;
      margin-bottom: 10px;
    }

    .right {
      flex: 2;
    }

    label {
      display: block;
      margin: 10px 0 5px;
    }

    input, textarea, select {
      width: 100%;
      padding: 8px;
      border-radius: 6px;
      border: 1px solid #ccc;
      margin-bottom: 15px;
    }

    input[type="submit"] {
      background-color: #28a745;
      color: white;
      font-size: 16px;
      border: none;
      cursor: pointer;
      transition: background 0.3s;
    }

    input[type="submit"]:hover {
      background-color: #218838;
    }

    @media(max-width: 768px) {
      .form-section {
        flex-direction: column;
        align-items: center;
      }

      .left, .right {
        width: 100%;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Biodata Form with Profile Picture</h2>
    <form id="biodataForm">
      <div class="form-section">
        <div class="left">
          <img id="profilePreview" src="https://via.placeholder.com/200" alt="Profile Picture Preview">
          <input type="file" accept="image/*" id="profilePic" onchange="previewImage(event)">
        </div>

        <div class="right">
          <label for="name">Full Name:</label>
          <input type="text" id="name" name="name" required>

          <label for="dob">Date of Birth:</label>
          <input type="date" id="dob" name="dob" required>

          <label for="gender">Gender:</label>
          <select id="gender" name="gender">
            <option value="male">Male</option>
            <option value="female">Female</option>
            <option value="other">Other</option>
          </select>

          <label for="email">Email:</label>
          <input type="email" id="email" name="email" required>

          <label for="phone">Phone Number:</label>
          <input type="tel" id="phone" name="phone" required>

          <label for="address">Address:</label>
          <textarea id="address" name="address" rows="3" required></textarea>

          <label for="education">Education:</label>
          <input type="text" id="education" name="education" required>

          <label for="skills">Skills:</label>
          <textarea id="skills" name="skills" rows="3"></textarea>

          <input type="submit" value="Submit">
        </div>
      </div>
    </form>
  </div>

  <script>
    function previewImage(event) {
      const reader = new FileReader();
      reader.onload = function(){
        const output = document.getElementById('profilePreview');
        output.src = reader.result;
      };
      reader.readAsDataURL(event.target.files[0]);
    }

    document.getElementById('biodataForm').addEventListener('submit', function(e) {
      e.preventDefault();
      alert("Form Submitted Successfully! (Demo purpose)");
    });
  </script>

</body>
</html>
