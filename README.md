<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Event Registration</title>
  <style>
    * { box-sizing: border-box; font-family: Arial, sans-serif; }
    body { background-color: #f4f6f8; display: flex; justify-content: center; padding: 40px 15px; }
    .card { background: white; width: 100%; max-width: 480px; padding: 25px; border-radius: 10px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
    h2 { margin-top: 0; color: #1e293b; text-align: center; }
    .form-group { margin-bottom: 16px; }
    label { display: block; margin-bottom: 6px; font-weight: bold; color: #475569; }
    input, select { width: 100%; padding: 10px; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 14px; }
    input:focus, select:focus { outline: none; border-color: #2563eb; }
    button { width: 100%; padding: 12px; background-color: #2563eb; color: white; border: none; border-radius: 6px; font-size: 16px; font-weight: bold; cursor: pointer; }
    button:hover { background-color: #1d4ed8; }
    #successMessage { display: none; background: #dcfce7; color: #166534; padding: 15px; border-radius: 6px; text-align: center; margin-top: 15px; }
  </style>
</head>
<body>

  <div class="card">
    <h2>Event Registration</h2>
    
    <form id="registrationForm">
      <div class="form-group">
        <label for="fullName">Full Name</label>
        <input type="text" id="fullName" required placeholder="John Doe">
      </div>

      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" required placeholder="john@example.com">
      </div>

      <div class="form-group">
        <label for="ticketType">Ticket Type</label>
        <select id="ticketType" required>
          <option value="">Select a ticket</option>
          <option value="General Admission">General Admission</option>
          <option value="VIP Pass">VIP Pass</option>
          <option value="Student">Student</option>
        </select>
      </div>

      <button type="submit">Register Now</button>
    </form>

    <div id="successMessage">
      🎉 Registration successful! We sent a confirmation email.
    </div>
  </div>

  <script>
    document.getElementById('registrationForm').addEventListener('submit', function(e) {
      e.preventDefault();
      
      const name = document.getElementById('fullName').value;
      const email = document.getElementById('email').value;
      const ticket = document.getElementById('ticketType').value;

      console.log('Registration Data:', { name, email, ticket });

      // Hide form and show confirmation
      document.getElementById('registrationForm').style.display = 'none';
      document.getElementById('successMessage').style.display = 'block';
    });
  </script>

</body>
</html>
