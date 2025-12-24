<script>
  // Svelte 5 (pakai state biasa untuk tampilan)
  let products = [
    {
      id: 1,
      name: "Sepatu Sneakers",
      price: "Rp 450.000",
      image: "https://picsum.photos/400/300?1"
    },
    {
      id: 2,
      name: "Jaket Hoodie",
      price: "Rp 350.000",
      image: "https://picsum.photos/400/300?2"
    },
    {
      id: 3,
      name: "Tas Ransel",
      price: "Rp 280.000",
      image: "https://picsum.photos/400/300?3"
    },
    {
      id: 4,
      name: "Jam Tangan",
      price: "Rp 520.000",
      image: "https://picsum.photos/400/300?4"
    }
  ];
</script>

<section class="min-h-screen bg-gray-100 p-6">
  <h1 class="text-3xl font-bold text-center mb-8">
    🛒 E-Commerce Store
  </h1>

  <!-- Grid Produk -->
  <div class="grid gap-6 
              sm:grid-cols-2 
              md:grid-cols-3 
              lg:grid-cols-4">
    {#each products as product}
      <div class="bg-white rounded-2xl shadow-md overflow-hidden 
                  hover:shadow-xl transition duration-300">
        
        <img
          src={product.image}
          alt={product.name}
          class="h-48 w-full object-cover"
        />

        <div class="p-4">
          <h2 class="text-lg font-semibold">
            {product.name}
          </h2>

          <p class="text-gray-600 mt-1">
            {product.price}
          </p>

          <button
            class="mt-4 w-full bg-blue-600 text-white py-2 rounded-xl
                   hover:bg-blue-700 transition">
            Tambah ke Keranjang
          </button>
        </div>
      </div>
    {/each}
  </div>
</section>

