<!DOCTYPE html><html>
<head>
  <title>ADI AUTO TECH NIG LTD | Book & Pay</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head><body style="font-family: Arial; margin:0; background:#f5f5f5;"><!-- HEADER --><div style="background:black; color:white; padding:20px; text-align:center;">
  <h1>ADI AUTO TECH NIG LTD</h1>
  <p>Professional Auto Repair Services in Lagos</p>
</div><!-- BOOKING FORM --><div style="background:white; padding:20px; margin:20px;">
  <h2>Book a Service</h2>  <form id="bookingForm" action="https://formspree.io/f/mzdozajq" method="POST"><input type="text" id="name" name="name" placeholder="Your Name" required style="width:100%; padding:10px; margin:5px;"><br>

<input type="email" id="email" name="email" placeholder="Your Email" required style="width:100%; padding:10px; margin:5px;"><br>

<input type="tel" name="phone" placeholder="Phone Number" required style="width:100%; padding:10px; margin:5px;"><br>

<textarea name="issue" placeholder="Describe your issue" style="width:100%; padding:10px; margin:5px;"></textarea><br>

<button type="submit" style="background:black; color:white; padding:12px; width:100%;">
  Submit Booking
</button>

  </form>
</div><!-- SERVICES --><div style="background:#fff; padding:20px; margin:20px;">
  <h2>Service Pricing</h2>  <!-- Diagnostics -->  <div style="border:1px solid #ddd; padding:15px; margin:10px;">
    <h3>Engine Diagnostics</h3>
    <p>₦7,000</p>
    <button onclick="pay(700000, 'Diagnostics')" style="background:green; color:white; padding:10px; width:100%;">Pay Now</button>
  </div>  <!-- Full Service -->  <div style="border:1px solid #ddd; padding:15px; margin:10px;">
    <h3>Full Car Servicing</h3>
    <p>₦15,000</p>
    <button onclick="pay(1500000, 'Full Service')" style="background:green; color:white; padding:10px; width:100%;">Pay Now</button>
  </div>  <!-- Electrical -->  <div style="border:1px solid #ddd; padding:15px; margin:10px;">
    <h3>Electrical Repairs</h3>
    <p>₦10,000</p>
    <button onclick="pay(1000000, 'Electrical')" style="background:green; color:white; padding:10px; width:100%;">Pay Now</button>
  </div>  <!-- Home Service -->  <div style="border:1px solid #ddd; padding:15px; margin:10px;">
    <h3>Home Service (Mobile Repair)</h3>
    <p>₦20,000</p>
    <button onclick="pay(2000000, 'Home Service')" style="background:green; color:white; padding:10px; width:100%;">Pay Now</button>
  </div>  <!-- Custom -->  <div style="border:1px solid #ddd; padding:15px; margin:10px;">
    <h3>Major Repairs</h3>
    <p>Contact for price</p>
    <a href="https://wa.me/2348138908282">
      <button style="background:black; color:white; padding:10px; width:100%;">
        Contact on WhatsApp
      </button>
    </a>
  </div></div><!-- CONTACT --><div style="text-align:center; padding:20px;">
  <p>📞 08138908282</p>
  <p>📍 Lagos, Nigeria</p>
</div><!-- PAYSTACK --><script src="https://js.paystack.co/v1/inline.js"></script><script>
function pay(amount, service){
  var name = document.getElementById("name").value;
  var email = document.getElementById("email").value;

  if(!name || !email){
    alert("Please fill your name and email before payment");
    return;
  }

  var handler = PaystackPop.setup({
    key: 'YOUR_PUBLIC_KEY_HERE',
    email: email,
    amount: amount,
    currency: "NGN",
    metadata: {
      custom_fields: [
        {
          display_name: "Customer Name",
          variable_name: "customer_name",
          value: name
        },
        {
          display_name: "Service",
          variable_name: "service",
          value: service
        }
      ]
    },
    callback: function(response){
      alert('Payment successful! Reference: ' + response.reference);
    },
    onClose: function(){
      alert('Payment cancelled');
    }
  });

  handler.openIframe();
}
</script></body>
</html>
