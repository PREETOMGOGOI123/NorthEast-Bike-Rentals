<script>

    import '../app.css';
    
    // Dummy motorcycle listings
    const availableMotorcycles = [
      {
        id: "M001",
        name: "Royal Enfield Classic 350",
        image: "https://images.unsplash.com/photo-1725591783170-2cb5566dded3?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "1000/day",
        type: "Cruiser",
        status: "Available",
        location: "Guwahati",
        cc: "350cc",
        features: ["Electric Start", "ABS", "Digital-Analog Console"]
      },
      {
        id: "M002",
        name: "KTM Duke 390",
        image: "https://images.unsplash.com/photo-1449426468159-d96dbf08f19f",
        price: "1500/day",
        type: "Sport",
        status: "Available",
        location: "Guwahati",
        cc: "373cc",
        features: ["ABS", "Quick Shifter", "TFT Display"]
      },
      {
        id: "M003",
        name: "Bajaj Pulsar N160",
        image: "https://images.unsplash.com/photo-1697683051952-fa8fb6283949?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "800/day",
        type: "Sport Commuter",
        status: "Available",
        location: "Guwahati",
        cc: "160cc",
        features: ["LED Lights", "ABS", "Digital Console"]
      },
      {
        id: "M004",
        name: "Honda CB350",
        image: "https://images.unsplash.com/photo-1558981403-c5f9899a28bc",
        price: "1200/day",
        type: "Modern Classic",
        status: "Available",
        location: "Guwahati",
        cc: "350cc",
        features: ["Traction Control", "ABS", "Bluetooth Connectivity"]
      }
    ];
  </script>
  
  <!-- Navbar -->
  <div class="navbar bg-neutral sticky top-0 z-50 shadow-lg">
    <div class="navbar-start">
      <!-- svelte-ignore a11y_missing_attribute -->
      <a class="btn btn-ghost text-neutral-content normal-case text-xl ">🏍️ MotoRent</a>
    </div>
    <div class="navbar-center hidden lg:flex">
      <ul class="menu menu-horizontal px-1 gap-10">
        <li><a href="#list-yours" class="btn btn-outline text-blue-500">List Your Bike</a></li>
        <li><a href="#available" class="btn btn-secondary btn-outline text-secondary-content">Rent Now</a></li>
      </ul>
    </div>
    <div class="navbar-end">
    </div>
  </div>
  
  <!-- Hero Section -->
  <div class="hero min-h-[70vh] relative" style="background-image: url('https://images.pexels.com/photos/8425811/pexels-photo-8425811.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1'); background-size: cover; background-position: center;">
    <div class="hero-overlay bg-opacity-60"></div>
    <div class="hero-content text-center text-neutral-content">
      <div class="max-w-md">
        <h1 class="text-5xl font-bold text-white mb-8">Motorcycle Rentals in Guwahati</h1>
        <p class="py-6 text-white text-lg">Rent your dream motorcycle or share yours with passionate riders.</p>
        <div class="flex gap-4 justify-center">
          <a href="#available" class="btn btn-primary btn-lg">View Available Bikes</a>
          <a href="YOUR_GOOGLE_FORM_LINK_FOR_LISTING" class="btn btn-secondary btn-lg">List Your Bike</a>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Available Motorcycles Section -->
  <section id="available" class="py-16 bg-base-100">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12">Available Motorcycles</h2>
      
      <!-- Motorcycle Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {#each availableMotorcycles as bike}
          <div class="card bg-base-100 shadow-xl hover:shadow-2xl transition-shadow duration-300">
            <figure class="relative h-64">
              <img src={bike.image} alt={bike.name} class="w-full h-full object-cover" />
              <div class="absolute top-4 right-4">
                <span class="badge badge-success">{bike.status}</span>
              </div>
            </figure>
            <div class="card-body">
              <h3 class="card-title">
                {bike.name}
                <div class="badge badge-secondary">{bike.type}</div>
              </h3>
              <div class="space-y-2">
                <p class="text-primary font-bold text-xl">₹{bike.price}</p>
                <p class="text-sm">📍 {bike.location}</p>
                <p class="text-sm">🔧 {bike.cc}</p>
                <div class="flex flex-wrap gap-2 mt-2">
                  {#each bike.features as feature}
                    <span class="badge badge-outline">{feature}</span>
                  {/each}
                </div>
              </div>
              <div class="card-actions justify-end mt-4">
                <a href="#available" class="btn btn-primary">Rent Now</a>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
  
  <!-- How It Works Section -->
  <section id="how-it-works" class="py-16 bg-base-200">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12">How It Works</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body">
            <div class="text-4xl mb-4">🏍️</div>
            <h3 class="text-xl font-bold mb-4">1. Choose Your Ride</h3>
            <p>Browse our collection of motorcycles and select your preferred ride.</p>
          </div>
        </div>
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body">
            <div class="text-4xl mb-4">📝</div>
            <h3 class="text-xl font-bold mb-4">2. Submit Request</h3>
            <p>Fill out our simple form with your details and rental duration.</p>
          </div>
        </div>
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body">
            <div class="text-4xl mb-4">🔑</div>
            <h3 class="text-xl font-bold mb-4">3. Ride Away</h3>
            <p>Complete the verification and enjoy your ride!</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- List Your Motorcycle Section -->
  <section id="list-yours" class="py-16 bg-base-100" style="background-image: url('https://images.unsplash.com/photo-1558981285-6f0c94958bb6'); background-size: cover; background-position: center;">
    <div class="bg-opacity-90 bg-base-100 py-16">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-3xl font-bold mb-6">Own a Motorcycle?</h2>
        <p class="mb-8 text-lg">Turn your motorcycle into an income source. List it on our platform and earn when you're not riding.</p>
        <div class="space-y-4">
          <a href="YOUR_GOOGLE_FORM_LINK_FOR_LISTING" class="btn btn-primary btn-lg">List Your Motorcycle</a>
          <p class="text-sm opacity-75">* All listings are verified and insured</p>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Contact Section -->
  <section id="contact" class="py-16 bg-base-200">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl font-bold mb-8">Contact Us</h2>
      <div class="max-w-md mx-auto">
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body">
            <p class="mb-4">📞 Call/WhatsApp: +91 8011127009</p>
            <p class="mb-4">📧 Email: contact@motorent.com</p>
            <p>📍 Location: Guwahati, Assam</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Footer -->
  <footer class="footer footer-center p-10 bg-base-200 text-base-content">
    <div>
      <p class="font-bold">
        MotoRent <br/>Your Journey, Our Motorcycles
      </p> 
      <p>© 2024 MotoRent - All rights reserved</p>
    </div> 
  </footer>
  
  <style>

  </style>