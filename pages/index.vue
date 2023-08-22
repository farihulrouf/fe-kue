<template>
  <div class="landing-page">
    <section class="landing-hero pt-5 px-6">
      <div class="header__bg"></div>
      <div class="container mx-auto relative">
        <Nav />
        <div class="flex items-center pt-10 px-5 md:px-8">
          <div class="w-1/2">
            <h1 class="text-5xl text-white mb-5">
              Ada <u class="hero-underline">Acara</u> <br />
              Ada <u class="hero-underline">Larissa</u> <br />
            </h1>
            <p class="text-white text-xl font-light mb-8">
              Lifestyle Bakery Dengan Varian Produk Terbanyak dan Jaminan<br />
              Kualitas Produk & Layanan.
            </p>
            <a
              href="#projects"
              class="bg-orange-button hover:bg-green-button text-white font-semibold px-12 py-3 text-xl rounded-full"
            >
              Produk larissa
            </a>
          </div>
          <div class="w-1/2 flex justify-center">
            <img src="/banner-laritta.png" alt="crowdfunding project" />
          </div>
        </div>
      </div>
    </section>
    <section class="container mx-auto pt-24 px-8 mt-8" id="features">
      <div class="w-full flex gap-2">
        <div class="w-1/3 bg-teal-500">
          <img src="donat-laritta.png" class="w-full" alt="promo" />
        </div>
        <div class="w-2/3 bg-orange-600">
          <img src="donat_larissa.png" class="w-full" alt="promo" />
          <div class="w-full flex">
            <img src="outlet-laritta.webp" alt="outleet" />
            <img src="promo.png" alt="outleet" />
          </div>
        </div>
      </div>

      <div class="flex justify-between items-center mb-10">
        <div class="w-auto">
          <h2 class="text-3xl text-gray-900 mb-8">
           
          </h2>
        </div>
      </div>
      <div
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6 mt-4 w-full"
      >
        <div class="p-6 bg-white border">
          <p class="text-center">
            <svg
              class="inline text-green-400 w-12 h-12 fill-current"
              xmlns="http://www.w3.org/2000/svg"
              enable-background="new 0 0 24 24"
              viewBox="0 0 24 24"
            >
              <g><rect fill="none" height="24" width="24" /></g>
              <g>
                <g />
                <g>
                  <circle cx="15.5" cy="9.5" r="1.5" />
                  <circle cx="8.5" cy="9.5" r="1.5" />
                  <path
                    d="M12,18c2.28,0,4.22-1.66,5-4H7C7.78,16.34,9.72,18,12,18z"
                  />
                  <path
                    d="M11.99,2C6.47,2,2,6.48,2,12c0,5.52,4.47,10,9.99,10C17.52,22,22,17.52,22,12C22,6.48,17.52,2,11.99,2z M12,20 c-4.42,0-8-3.58-8-8c0-4.42,3.58-8,8-8s8,3.58,8,8C20,16.42,16.42,20,12,20z"
                  />
                </g>
              </g>
            </svg>
          </p>

          <h2 class="font-semibold text-lg text-center text-gray-800 mt-2">
            Raja Pesanan
          </h2>

          <p class="mt-2 text-gray-800 text-center">
            Larissa Bakery berpengalaman menangani pesanan roti dalam jumlah
            besar (hingga 35.000 item sehari) sejak 2010. Berapapun jumlah
            pesanan Anda, Kami layani.
          </p>
        </div>
        <div class="p-6 bg-white border">
          <p class="text-center">
            <svg
              class="inline text-blue-400 w-12 h-12 fill-current"
              xmlns="http://www.w3.org/2000/svg"
              enable-background="new 0 0 24 24"
              viewBox="0 0 24 24"
            >
              <path d="M0 0h24v24H0V0z" fill="none" />
              <circle cx="15.5" cy="9.5" r="1.5" />
              <circle cx="8.5" cy="9.5" r="1.5" />
              <path
                d="M12 16c-1.48 0-2.75-.81-3.45-2H6.88c.8 2.05 2.79 3.5 5.12 3.5s4.32-1.45 5.12-3.5h-1.67c-.7 1.19-1.97 2-3.45 2zm-.01-14C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z"
              />
            </svg>
          </p>

          <h2 class="font-semibold text-lg text-center text-gray-800 mt-2">
            Fresh from Oven
          </h2>

          <p class="mt-2 text-gray-800 text-center">
            Seluruh produk pesanan selalu dibuat paling lama 24 jam sebelum
            waktu pengambilan pesanan. Roti kami tahan 2-3 hari dari pembelian
            Anda di outlet Laritta.
          </p>
        </div>
        <div class="p-6 bg-white border">
          <p class="text-center">
            <svg
              class="inline text-indigo-400 w-12 h-12 fill-current"
              xmlns="http://www.w3.org/2000/svg"
              enable-background="new 0 0 24 24"
              viewBox="0 0 24 24"
            >
              <path d="M0 0h24v24H0V0z" fill="none" />
              <path
                d="M11.99 2C6.47 2 2 6.47 2 12s4.47 10 9.99 10S22 17.53 22 12 17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm1-10.06L14.06 11l1.06-1.06L16.18 11l1.06-1.06-2.12-2.12L13 9.94zm-4.12 0L9.94 11 11 9.94 8.88 7.82 6.76 9.94 7.82 11l1.06-1.06zM12 17.5c2.33 0 4.31-1.46 5.11-3.5H6.89c.8 2.04 2.78 3.5 5.11 3.5z"
              />
            </svg>
          </p>

          <h2 class="font-semibold text-lg text-center text-gray-800 mt-2">
            Gratis Antar
          </h2>

          <p class="mt-2 text-gray-800 text-center">
            Laritta Bakery menyediakan layanan antar pesanan dalam kota
            (Surabaya & Sidoarjo), hingga ke luar kota kota (Malang, Batu,
            Gresik, Pasuruan, Mojokerto, Bangkalan, Sampang, Pamekasan, dan kota
            lain di Jawa Timur).
          </p>
        </div>
        <div class="p-6 bg-white border">
          <p class="text-center">
            <svg
              class="inline text-red-400 w-12 h-12 fill-current"
              xmlns="http://www.w3.org/2000/svg"
              enable-background="new 0 0 24 24"
              viewBox="0 0 24 24"
            >
              <path d="M0 0h24v24H0V0z" fill="none" />
              <path
                d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm3.5-9c.83 0 1.5-.67 1.5-1.5S16.33 8 15.5 8 14 8.67 14 9.5s.67 1.5 1.5 1.5zm-7 0c.83 0 1.5-.67 1.5-1.5S9.33 8 8.5 8 7 8.67 7 9.5 7.67 11 8.5 11zm3.5 2.5c-2.33 0-4.31 1.46-5.11 3.5h10.22c-.8-2.04-2.78-3.5-5.11-3.5z"
              />
            </svg>
          </p>

          <h2 class="font-semibold text-lg text-center text-gray-800 mt-2">
            Jaminan Kualitas
          </h2>

          <p class="mt-2 text-gray-800 text-center">
            Lara Bakery senantiasa menjaga kualitas produk dan layanan untuk
            pelanggan setia kami. Kami memberi garansi uang kembali hingga 100%
            jika Anda tidak puas dengan produk atau layanan kami.
          </p>
        </div>
      </div>
    </section>

    <section class="container mx-auto pt-24 px-6" id="projects">
      <div class="flex justify-between items-center">
        <div class="w-auto">
          <h2 class="text-3xl text-gray-900 mb-8">Our Products</h2>
        </div>
        <div class="w-auto mt-5">
          <a class="text-gray-900 hover:underline text-md font-medium" href=""
            >View All</a
          >
        </div>
      </div>
      <div class="grid grid-cols-3 gap-4 mt-3">
        <div
          v-for="product in products.data"
          :key="product.id"
          class="card-project w-full p-5 rounded-20"
        >
          <img
            :src="$axios.defaults.baseURL + '/' + product.image_url"
            alt=""
            class="rounded-xl w-full h-[300px]"
          />

          <div class="flex justify-between items-center">
            <div>
              <h1 class="mt-5 text-2xl font-semibold">{{ product.name }}</h1>
              <p class="mt-2">Rp {{ product.price.toLocaleString() }}</p>
            </div>
            <div>
              <button
                class="text-white text-md font-semibold bg-pink-600 py-2 px-4 rounded-lg shadow-md hover:shadow-lg transition duration-500 transform-gpu hover:scale-110"
                @click="
                  $router.push({
                    name: 'products-id',
                    params: { id: product.id },
                  })
                "
              >
                Buy Now
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="container mx-auto pt-24 px-8" id="testimonials">
      <div class="flex justify-between items-center mb-10">
        <div class="w-auto">
          <h2 class="text-3xl text-gray-900 mb-8">
            Apa yang di katakan <br />
            Customer kami
          </h2>
        </div>
      </div>
      <div
        class="grid mb-8 border border-gray-200 rounded-lg shadow-sm dark:border-gray-700 md:mb-12 md:grid-cols-2"
      >
        <figure
          class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 rounded-t-lg md:rounded-t-none md:rounded-tl-lg md:border-r dark:bg-gray-800 dark:border-gray-700"
        >
          <blockquote
            class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400"
          >
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
              Very easy this was to integrate
            </h3>
            <p class="my-4">
              If you care for your time, I hands down would go with this."
            </p>
          </blockquote>
          <figcaption class="flex items-center justify-center space-x-3">
            <img
              class="rounded-full w-9 h-9"
              src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/karen-nelson.png"
              alt="profile picture"
            />
            <div class="space-y-0.5 font-medium dark:text-white text-left">
              <div>Bonnie Green</div>
              <div class="text-sm text-gray-500 dark:text-gray-400">
                Developer at Open AI
              </div>
            </div>
          </figcaption>
        </figure>
        <figure
          class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 rounded-tr-lg dark:bg-gray-800 dark:border-gray-700"
        >
          <blockquote
            class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400"
          >
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
              Solid foundation for any project
            </h3>
            <p class="my-4">
              Designing with Figma components that can be easily translated to
              the utility classes of Tailwind CSS is a huge timesaver!"
            </p>
          </blockquote>
          <figcaption class="flex items-center justify-center space-x-3">
            <img
              class="rounded-full w-9 h-9"
              src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/roberta-casas.png"
              alt="profile picture"
            />
            <div class="space-y-0.5 font-medium dark:text-white text-left">
              <div>Roberta Casas</div>
              <div class="text-sm text-gray-500 dark:text-gray-400">
                Lead designer at Dropbox
              </div>
            </div>
          </figcaption>
        </figure>
        <figure
          class="flex flex-col items-center justify-center p-8 text-center bg-white border-b border-gray-200 rounded-bl-lg md:border-b-0 md:border-r dark:bg-gray-800 dark:border-gray-700"
        >
          <blockquote
            class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400"
          >
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
              Mindblowing workflow
            </h3>
            <p class="my-4">
              Aesthetically, the well designed components are beautiful and will
              undoubtedly level up your next application."
            </p>
          </blockquote>
          <figcaption class="flex items-center justify-center space-x-3">
            <img
              class="rounded-full w-9 h-9"
              src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/jese-leos.png"
              alt="profile picture"
            />
            <div class="space-y-0.5 font-medium dark:text-white text-left">
              <div>Jese Leos</div>
              <div class="text-sm text-gray-500 dark:text-gray-400">
                Software Engineer at Facebook
              </div>
            </div>
          </figcaption>
        </figure>
        <figure
          class="flex flex-col items-center justify-center p-8 text-center bg-white border-gray-200 rounded-b-lg md:rounded-br-lg dark:bg-gray-800 dark:border-gray-700"
        >
          <blockquote
            class="max-w-2xl mx-auto mb-4 text-gray-500 lg:mb-8 dark:text-gray-400"
          >
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
              Efficient Collaborating
            </h3>
            <p class="my-4">
              You have many examples that can be used to create a fast prototype
              for your team."
            </p>
          </blockquote>
          <figcaption class="flex items-center justify-center space-x-3">
            <img
              class="rounded-full w-9 h-9"
              src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/joseph-mcfall.png"
              alt="profile picture"
            />
            <div class="space-y-0.5 font-medium dark:text-white text-left">
              <div>Joseph McFall</div>
              <div class="text-sm text-gray-500 dark:text-gray-400">
                CTO at Google
              </div>
            </div>
          </figcaption>
        </figure>
      </div>
    </section>
    <div class="cta-clip -mt-20"></div>
    <CallToAction />
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const products = await $axios.$get('/api/v1/products')
    console.log(products)
    return { products }
  },
}
</script>

<style lang="scss">
.header__bg {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  width: 100%;
  height: 600px;
  background-image: url('/auth-background.svg');
  background-position: top left;
  background-repeat: no-repeat;
  background-color: #ee3123;
  transform: skewY(-6deg);
  transform-origin: top left;
}

.cta-clip {
  position: relative;
  top: 200px;
  bottom: 0;
  right: 0;
  left: 0;
  width: 100%;
  height: 300px;
  background-position: top right;
  background-size: 300px;
  background-repeat: no-repeat;
  background-color: #fff;
  transform: skewY(4deg);
  transform-origin: bottom right;
}

.call-to-action {
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-size: 450px;
}

.card-project {
  transition: all 0.3s ease 0s, opacity 0.5s cubic-bezier(0.5, 0, 0, 1) 1ms;
  max-height: 485px;
  overflow: hidden;

  .button-cta {
    opacity: 0;
    transition: all 300ms ease;
  }

  &:hover {
    box-shadow: 0 4px 25px 0 rgba(0, 0, 0, 0.15);

    .button-cta {
      opacity: 1;
      transition: all 300ms ease;
    }

    .progress-bar,
    .progress-info {
      opacity: 0;
      height: 0px;
      margin: 0px;
      padding: 0px;
      transition: all 300ms ease;
    }
  }
}

footer {
  z-index: inherit;
}

.hero-underline {
  text-decoration-color: #1abc9c;
}

.testimonial-user {
  opacity: 0.4;
  &.active {
    opacity: 1;
    border: 5px solid #fff;
    box-shadow: 0 0 0 1px #3b41e3;
  }
}
</style>
