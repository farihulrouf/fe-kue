<template>
  <div class="project-page">
    <section class="dashboard-header pt-5">
      <div class="container mx-auto relative">
        <Navbar />
      </div>
    </section>
    <section class="container mx-auto pt-8">
      <div class="flex justify-between items-center mb-6">
        <div class="w-3/4 mr-6 mx-6">
          <h2 class="text-4xl text-gray-900 mb-2 font-medium">Dashboard</h2>
          <ul class="flex mt-2">
            <li class="mr-6">
              <nuxt-link class="text-gray-500 hover:text-gray-800" to="/admin">
                Your Products
              </nuxt-link>
            </li>
            <li class="mr-6">
              <a class="text-gray-800 font-bold" href="#">
                Your Transactions
              </a>
            </li>
          </ul>
        </div>
      </div>
      <hr />
      <div class="block mb-2">
        <div
          class="w-full lg:max-w-full lg:flex mb-4 mt-6"
          v-for="transaction in transactions.data"
          :key="transaction.id"
        >
          <!-- start  -->
          <div
            class="mx-6 w-full border-gray-500 border rounded-sm text-gray-700 mb-0.5 h-30"
          >
            <div class="flex p-3 border-l-8 border-indigo-700">
              <div class="space-y-1 border-r-2 pr-3">
                <div class="text-sm leading-5 font-semibold">
                  <span class="text-xs leading-4 font-normal text-gray-500">
                    Invoice #</span
                  >
                  LTC{{ transaction.id }}
                </div>
                <div class="text-sm leading-5 font-semibold">
                  <span class="text-xs leading-4 font-normal text-gray-500 pr">
                    INV #</span
                  >
                  109{{ transaction.id }}
                </div>
                <div class="text-sm leading-5 font-semibold">
                  {{ transaction.created_at }}
                </div>
              </div>
              <div class="w-2/3">
                <div class="ml-3 space-y-1 border-r-2 pr-3">
                  <div class="text-base leading-6 font-normal font-semibold">
                    {{ transaction.product.name }}
                  </div>

                  <div class="text-sm leading-4 font-normal">
                    <span class="text-xs leading-4 font-normal text-gray-500">
                      Description</span
                    >
                    {{ transaction.product.description }}
                  </div>
                </div>
              </div>
              <div class="border-r-2 pr-3">
                <div>
                  <div
                    class="ml-3 my-3 border-gray-200 border-2 bg-gray-300 p-1 w-32"
                  >
                    <div class="uppercase text-xs leading-4 font-medium">
                      Rp
                    </div>
                    <div
                      class="text-center text-sm leading-4 font-semibold text-gray-800"
                    >
                      Rp
                      {{ new Intl.NumberFormat().format(transaction.amount) }}
                    </div>
                  </div>
                </div>
              </div>
              <div>
                <div
                  v-if="transaction.status === 'pending'"
                  class="tml-3 my-5 bg-yellow-600 p-1 w-20"
                >
                  <div
                    class="uppercase text-xs leading-4 font-semibold text-center text-yellow-100"
                  >
                    {{ transaction.status }}
                  </div>
                </div>
                <div v-else class="tml-3 my-5 bg-teal-600 p-1 w-20">
                  <div
                    class="uppercase text-xs leading-4 font-semibold text-center text-yellow-100"
                  >
                    {{ transaction.status }}
                  </div>
                </div>
              </div>
              <div>
                <nuxt-link :to="'/admin/transactions/' + transaction.id">
                  <button
                    class="text-gray-100 rounded-sm my-5 ml-2 focus:outline-none bg-gray-500"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-6 w-6"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M19 9l-7 7-7-7"
                      />
                    </svg>
                  </button>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="cta-clip -mt-20"></div>
    <section class="call-to-action bg-purple-progress pt-64 pb-10"></section>
    <Footer />
  </div>
</template>

<script>
export default {
  //http://localhost:8080/api/v1/transactionsall
  middleware: 'auth',
  async asyncData({ $axios }) {
    const transactions = await $axios.$get('/api/v1/transactionsall')
    return { transactions }
  },
}
</script>

<style lang="scss">
.dashboard-header {
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-color: #3b41e3;
  background-size: 250px;
  height: 100px;
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
