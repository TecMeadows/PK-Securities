<template>
  <div>
    <div class="bg-black">
      <div class="p-0 container-small bg-white">
        <div class="pt-5 padd-wwd">
          <h5 style="font-size:12px;margin-bottom: 25px">
            <nuxt-link style="color: #B71C1C" to="/">HOME</nuxt-link> / WHAT WE DO
          </h5>
          <h1 class="text-center" style="color:#454545">What we do</h1>
          <p class="text-center col-head" style>PK Security Services</p>
        </div>
        <div style="background-color:#f3f3f3">
          <div style="padding:20px 30px">
            <div class="row mt-4">
              <div class="col-12 col-sm-3 bg-white" style="border-bottom: 2px solid #9b1013" v-for="p in security" :key="p.id">
                <div style="padding:5px 3px 3px">
                  <div>
                    <p class="text-header">{{p.title}}</p>
                    <p class="text-sub">
                      {{p.content}}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="pt-5 bg-white">
          <p class="text-center col-head" style>PK Services</p>
          <div style="background-color:#fff">
            <div style="padding:20px 30px">
              <div class="row mt-4">
                <div
                  class="col-12 col-sm-3"
                  style="background-color:#f8f8f8;border-bottom: 2px solid #9b1013"
                  v-for="p in services" :key="p.id"
                >
                  <div style="padding:5px 3px 3px">
                  <div>
                    <p class="text-header">{{p.title}}</p>
                    <p class="text-sub">
                      {{p.content}}
                    </p>
                  </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["services"]),
    ...mapState(["security"])
  },

  mounted() {
    this.$store.dispatch("getAllServices");
    this.$store.dispatch("getAllSecurity");
  }
};
</script>

<style>
.padd-wwd {
  padding: 50px;
}

.col-head {
  color: #5b5b5b;
  opacity: 0.6;
  font-weight: bold;
  font-size: 19px;
}

.text-header {
  font-style: normal;
  line-height: 1.13;
  letter-spacing: normal;
  text-align: center;
  color: #737373;
  opacity: 0.54;
  font-size: 19px;
  margin-top: 20px
}

.text-sub {
  margin-top: 0;
  margin-bottom: 1rem;
  line-height: 28px;
  font-size: 13px;
  text-align: center;
}
</style>
