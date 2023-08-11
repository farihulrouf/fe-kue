<template>
    <div class="product-page">
      <section class="dashboard-header pt-5">
        <div class="container mx-auto relative">
          <Navbar />
        </div>
      </section>
      <section class="container mx-auto pt-8 px-6">
        <div class="flex justify-between items-center">
          <div class="w-full mr-6">
            <h2 class="text-4xl text-gray-900 mb-2 font-medium">Dashboard</h2>
          </div>
        </div>
        <div class="flex justify-between items-center">
          <div class="w-3/4 mr-6">
            <h3 class="text-2xl text-gray-900 mb-4">Transaction Details</h3>
          </div>
          <div class="w-1/4 text-right">
           <!--
            <nuxt-link
              :to="{
                name: 'admin-transactions-id-edit',
                params: { id: transactions.data.id },
              }"
              class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-1 rounded inline-flex items-center"
            >
              Edit
            </nuxt-link>
            -->
            <button
              @click="save"
              class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-1 rounded inline-flex items-center"
            >
              Save
            </button>
  
          </div>
        </div>
        <div class="block mb-2">
          <div class="w-full lg:max-w-full lg:flex mb-4">
            <div
              class="w-full border border-gray-400 bg-white rounded p-8 flex flex-col justify-between leading-normal"
            >
              <div>
                <div class="text-gray-900 font-bold text-xl mb-2">
                   Rp {{ transactions.data.amount }}
                </div>
                <button class="text-gray-700 bg-yellow-400 px-4 py-1">
                    {{ transactions.data.status }}
                </button>
             
               
              
       
                <!--
                <p class="text-sm font-bold flex items-center mb-1 mt-4">
                  Goal Amount
                </p>
                <p class="text-4xl text-gray-700 text-base">
                  {{ new Intl.NumberFormat().format(product.data.price) }}
                </p>
                -->
              </div>
            </div>
          </div>
        </div>

        <!--
        <div class="flex justify-between items-center">
          <div class="w-2/4 mr-6">
            <h3 class="text-2xl text-gray-900 mb-4 mt-5">Gallery</h3>
          </div>
          <div class="w-2/4 text-right">
            <input
              type="file"
              ref="file"
              @change="selectFile"
              class="border p-1 rounded overflow-hidden"
            />
            <button
              @click="upload"
              class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-2 rounded inline-flex items-center"
            >
              Upload
            </button>
          </div>
        </div>
        -->
     
      </section>
      <div class="cta-clip -mt-20"></div>
      <section class="call-to-action bg-purple-progress pt-64 pb-10"></section>
      <Footer />
    </div>
  </template>
  
  <script>
  export default {
    middleware: 'auth',
    async asyncData({ $axios, params }) {
      const transactions = await $axios.$get('/api/v1/transactions/' + params.id)
   //   const product = await $axios.$get('/api/v1/products/' + params.id)
     /* const transactions = await $axios.$get(
        '/api/v1/products/' + params.id + '/transactions'
      )
      */
     // console.log("test data",product)
      return { transactions }
    },

    methods:{

    async save() {
        try {
          let response = await this.$axios.$put(
            '/api/v1/transactions/' + this.$route.params.id,
            {
              status: "paid",
            }
          )
          //console.log(response)
          this.$router.push({ path: '/admin/transactions' })

        } catch (err) {
          console.log(err)
        }
        
      },
    },

    data() {
      return {
        selectedFiles: undefined,
      }
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
  