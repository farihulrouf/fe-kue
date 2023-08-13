<template>
  <div class="project-page">
    <section class="project-header pt-5 px-6">
      <div class="container mx-auto relative">
        <Nav />
      </div>
    </section>
    <section class="container project-container mx-auto -mt-56 px-6">
      <div class="flex mt-3">
        <div class="w-3/4 mr-6 flex-col flex justify-center items-center">
           <h2 class="text-3xl text-white mb-8 ">Paket Hosting: {{ product.data.name }}</h2>
           <div class="flex gap-4 text-white mt-4 mb-4">
              <div class="text-white p-4 px-6 bg-teal-500 rounded-xl">
                <!--  <div id="{{ val }}">, use <div :id="val">. -->
                  <input type="radio" id="one" v-bind:value=product.data.pricetwo*12  v-model="picked" />
                  <label class="text-2xl" for="one">1 year</label>
                  <p class="text-2xl">Rp {{ product.data.pricetwo.toLocaleString() }}</p>
                  <p class="text-[11px] text-center">Month</p>
              </div>
              <div class="text-white p-4 px-6 bg-teal-500 rounded-xl">
                  <input type="radio" id="two" v-bind:value=product.data.pricetree*24 v-model="picked" />
                  <label for="two" class="text-2xl">2 years</label>
                  <p class="text-2xl">Rp {{  product.data.pricetree.toLocaleString() }}</p>
                  <p class="text-[11px] text-center">Month</p>
              </div>
              <div class="text-white p-4 px-6 bg-teal-500 rounded-xl">
                  <input type="radio" id="month" v-bind:value=product.data.price v-model="picked" />
                  <label class="text-2xl" for="month">1 bulan</label>
                  <p class="text-2xl">Rp {{  product.data.price.toLocaleString() }}</p>
                  <p class="text-[11px] text-center">Month</p>
              </div>
              
          </div>
          
        </div>
        <div class="w-1/4">
          <div
            class="bg-white w-full p-5 border border-gray-400 rounded-20 sticky"
            style="top: 15px"
          >
            <h3>{{ product.data.name }}</h3>
            <!--
              <div class="flex mt-3">
                <div class="w-1/4">
                  <img
                    :src="
                      $axios.defaults.baseURL + '/' + product.data.user.image_url
                    "
                    alt=""
                    class="w-full inline-block rounded-full"
                  />
                </div>
                <div class="w-3/4 ml-5 mt-1">
                  <div class="font-semibold text-xl text-gray-800">
                    {{ product.data.user.name }}
                  </div>
                  <div class="font-light text-md text-gray-400">
                    {{ product.data.backer_count }} backer
                  </div>
                </div>
              </div>
              -->
            <h4 class="mt-5 font-semibold">What will you get:</h4>
            <ul class="list-check mt-3">
              <li v-for="perk in product.data.perks" :key="perk">
                {{ perk }}
              </li>
            </ul>
            <template v-if="this.$store.state.auth.loggedIn">
             

              <input
                type="number"
                class="border border-gray-500 block w-full px-6 py-3 mt-4 rounded-full text-gray-800 transition duration-300 ease-in-out focus:outline-none focus:shadow-outline"
                placeholder="Amount in Rp"
                value="0"
                v-model.number="transaction.amount"
                @keyup.enter="fund"
              />
              

              <button
                @click="fund"
                class="mt-3 button-cta block w-full bg-orange-button hover:bg-green-button text-white font-medium px-6 py-3 text-md rounded-full"
              >
                Buy Now
              </button>
            </template>
            <template v-else>
              <button
                @click="$router.push({ path: '/login' })"
                class="mt-3 button-cta block w-full bg-orange-button hover:bg-green-button text-white font-medium px-6 py-3 text-md rounded-full"
              >
                Sign in to Fund
              </button>
            </template>
          </div>
        </div>
      </div>
    </section>

    <section class="w-3/4 px-6 -mt-20 flex justify-center items-center">
      <div class="flex flex-col justify-center w-1/2">
        <div class="flex items-center gap-2 mt-4 mb-4">
          <input type="text" placeholder="Type name domain" class="border p-2 w-full rounded-lg px-6" />
        </div>

        <div class="mt-4 mb-4 border p-4">
          {{ product.data.short_description }}
        </div>

        <h2 class="text-3xl text-black mt-6">Total Bayar Rp {{ transaction.amount = picked }}</h2>
      </div>
    </section>
    <div class="cta-clip -mt-20"></div>
    <CallToAction />
    <Footer />
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  async asyncData({ $axios, params }) {
    const product = await $axios.$get('/api/v1/products/' + params.id)
    return { product }
  },
  data() {
    return {
      picked: 'one',
      checked: true,
      default_image: '',
      transaction: {
        amount: 0,
        product_id: Number.parseInt(this.$route.params.id),
      },
    }
  },
  methods: {
    /*
    axios({
  method: 'post',
  url: '/user/1',
  data: {
    firstName: 'Renat',
    lastName: 'Galyamov'
  }
})
*/
  
    async fund() {
      try {
        let response = await this.$axios.$post(
          '/api/v1/transactions',
          this.transaction
        )
        window.location = response.data.payment_url
        console.log(response)
      } catch (err) {
        console.log(err)
      }
    },
    changeImage(url) {
      this.default_image = url
    },
  },
  mounted() {
    this.default_image =
      this.$axios.defaults.baseURL + '/' + this.product.data.image_url
  },
}
</script>

<style lang="scss">
.project-header {
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-color: #3b41e3;
  background-size: 250px;
  height: 350px;
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

.list-check {
  li {
    background: url('/icon-checklist.svg') no-repeat left 8px;
    padding: 6px 0px 3px 28px;
  }
}

.item-thumbnail:hover {
  background-color: #ff872e;
  border-radius: 20px;
  &:after {
    position: absolute;
    top: 38%;
    left: 41%;
    content: url('/icon-thumbnail-hover.svg');
  }
  img {
    opacity: 0.3;
  }
}
</style>
