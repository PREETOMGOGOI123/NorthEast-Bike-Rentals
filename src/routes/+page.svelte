<script>

    import '../app.css';
    
    // Dummy motorcycle listings
    const availableMotorcycles = [
      {
        id: "M001",
        name: "Royal Enfield Himalayan",
        image: "https://images.unsplash.com/photo-1609174470568-ac0c96458a67?q=80&w=2071&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "1500/day",
        type: "Adventure",
        status: "Available",
        location: "XYZ",
        cc: "411cc",
        features: ["All-Terrain", "ABS", "Digital Navigation"]
      },
      {
        id: "M002",
        name: "Hero XPulse 200",
        image: "https://images.unsplash.com/photo-1648131728440-14d0225c16c3?q=80&w=1976&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "1000/day",
        type: "Adventure",
        status: "Available",
        location: "XYZ",
        cc: "200cc",
        features: ["Off-Road Ready", "LED Headlamp", "Turn-by-Turn Navigation"]
      },
      {
        id: "M003",
        name: "City Commutes",
        image: "https://images.unsplash.com/photo-1724992638710-3e365cafc968?q=80&w=2140&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "500/day",
        type: "City Commuter",
        status: "Available", 
        location: "XYZ",
        cc: "125cc",
        features: ["Economic", "Comfortable", "Low Maintenance"]
      },
      {
        id: "M004",
        name: "Scooters",
        image: "https://images.unsplash.com/photo-1591517487866-e7c7bf9896fb?q=80&w=1935&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        price: "400/day",
        type: "City Commuter",
        status: "Available",
        location: "XYZ",
        cc: "125cc",
        features: ["Economic", "Easy to Ride", "Storage Space"]
      }
    ];
  </script>
  
  <!-- Navbar -->
  <div class="navbar bg-base top-0 z-50 mb-10 mt-5 px-10">
    <div class="navbar-start">
      <!-- svelte-ignore a11y_missing_attribute -->
      <a class="btn btn-ghost normal-case text-3xl font-black logo italic " href="/">NE RENTALS</a>
    </div>
    <div class="navbar-center lg:flex">
      <p class="btn btn-outline"> ☎️ +91 8011127009</p>
    </div>
    <div class="navbar-end">
      <ul class="menu menu-horizontal px-1 gap-10">
        <li><a href="#list-bikes" class="btn ">List Your Bike</a></li>
        <li><a href="#available" class="btn">Rent Now</a></li>
      </ul>
    
    </div>
  </div>
  
  <!-- Hero Section -->
  <div class="hero min-h-[70vh] relative" style="background-image: url('https://images.pexels.com/photos/8425811/pexels-photo-8425811.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1'); background-size: cover; background-position: center;">
    <div class="hero-overlay bg-opacity-60"></div>
    <div class="hero-content text-center text-neutral-content">
      <div class="max-w-md">
        <h1 class="text-5xl font-bold text-white mb-8">Motorcycle Rentals</h1>
        <p class="py-6 text-white text-lg">Rent your dream motorcycle or share yours with passionate riders.</p>
        <div class="flex gap-4 justify-center">
          <a href="#available" class="btn btn-primary btn-lg">View Available Bikes</a>
          <a href="YOUR_GOOGLE_FORM_LINK_FOR_LISTING" class="btn btn-secondary btn-lg">List Your Bike</a>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Available Motorcycles Section -->
  <section id="available" class="my-32 bg-base-100">
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
                <a href="https://docs.google.com/forms/d/e/1FAIpQLScrUsH_h5nD6IIERLW_fNccs0zTxMm-y2fqeXJGc6Nd1HeaEw/viewform?usp=sharing" target="_blank" class="btn btn-primary">Rent Now</a>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
  
  
  
  <!-- List Your Motorcycle Section -->
  <section id="list-bikes" class="py-24 bg-base-100" style="background-image: url('https://images.unsplash.com/photo-1558981285-6f0c94958bb6'); background-size: cover; background-position: center;">
    <div class="bg-opacity-90 bg-base-100 py-16">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-3xl font-bold mb-6">Own a Motorcycle?</h2>
        <p class="mb-8 text-lg">Turn your motorcycle into an income source. List it on our platform and earn when you're not riding.</p>
        <div class="space-y-4">
          <a href="https://docs.google.com/forms/d/e/1FAIpQLSdKIbe2jaNimeFkye20axD8ac4UpeJ5wq9BDq6jCmdXc8yoWA/viewform?usp=sharing" target="_blank" class="btn btn-primary btn-lg">List Your Motorcycle</a>
          <p class="text-sm opacity-75">* All listings are verified and insured</p>
        </div>
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
  
  <!-- Contact Section -->
  <section id="contact" class="py-16 bg-base-200">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl font-bold mb-8">Contact Us</h2>
      <div class="max-w-md mx-auto">
        <div class="card bg-base-100 shadow-xl">
          <div class="card-body">
            <p class="mb-4">📞 Call/WhatsApp: +91 8011127009</p>
            <p class="mb-4">📧 Email: rental.northeast@gmail.com</p>
            <p>📍 Location: Guwahati, Assam, India</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Footer -->
  <footer class="footer footer-center p-10 bg-base-200 text-base-content">
    <div>
      <p class="font-bold">
        NE RENTALS <br/>Your Journey, Our Motorcycles
      </p> 
      <p>© 2024 MotoRent - All rights reserved</p>
    </div> 
  </footer>
  
  <style>
    .logo {
      background: url(https://images.unsplash.com/photo-1626931609213-d18aa1313402?q=80&w=2075&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D);
      -webkit-background-clip: text;
      background-clip: text;
      color: #000;
      -webkit-text-fill-color: transparent;
      text-fill-color: transparent;
      background-size: cover;
      background-position: center;
    }
  </style>