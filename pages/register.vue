<template>
  <div class="h-screen w-full bg-[#010148]">
    <h1 class="text-white text-center text-2xl pt-10 font-bold">
      Dapatkan mobil klasikmu sekarang
    </h1>
    <form
      action=""
      class="mx-auto w-full flex justify-center items-center p-10 flex-col"
    >
      <div>
        <label for="name" class="text-white">Full Name</label>
        <input
          type="text"
          id="name"
          class="bg-transparent border-white border-2 text-white"
          placeholder="Enter your full name"
          v-model="name"
        />
      </div>
      <div class="mt-10 flex flex-col md:flex-row">
        <label for="country" class="text-white">Country</label>
        <select
          id="country"
          name="country"
          class="bg-transparent border-white border-2 text-white"
          v-model="selectedCountry"
        >
          <option
            v-for="country in country"
            :value="country.countryCode"
            :key="country.countryCode"
          >
            {{ country.countryName }}
          </option>
        </select>
        <label for="city" class="text-white">City</label>
        <select
          id="city"
          name="city"
          class="bg-transparent border-white border-2 text-white"
          v-model="selectedCity"
          :disabled="!selectedCountry"
        >
          <option v-for="city in filteredCities" :value="city.cityCode">
            {{ city.cityName }}
          </option>
        </select>
      </div>
      <button
        type="submit"
        @click.prevent="submitForm"
        class="bg-gray-400 text-white w-fit px-2 py-3 mt-10"
      >
        Register Now
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "RegisterPage",
  data() {
    return {
      name: "",
      selectedCountry: "",
      selectedCity: "",
      country: [
        {
          countryName: "Malaysia",
          countryCode: "MSY",
        },
        {
          countryName: "Indonesia",
          countryCode: "IDN",
        },
      ],
      city: [
        {
          cityName: "Jakarta",
          cityCode: "JKT",
          countryCode: "IDN",
        },
        {
          cityName: "Penang",
          cityCode: "PEN",
          countryCode: "MSY",
        },
        {
          cityName: "Bandung",
          cityCode: "BDO",
          countryCode: "IDN",
        },
        {
          cityName: "Kuala Lumpur",
          cityCode: "KLP",
          countryCode: "MSY",
        },
      ],
    };
  },
  computed: {
    filteredCities() {
      if (!this.selectedCountry) {
        return [];
      }
      return this.city.filter(
        (city) => city.countryCode === this.selectedCountry
      );
    },
  },
  methods: {
    submitForm() {
      if (!this.name) {
        alert("Anda belum mengisi nama");
        return;
      } else if (!this.selectedCountry) {
        alert("Anda belum memilih negara");
        return;
      } else if (!this.selectedCity) {
        alert("Anda belum memilih kota");
        return;
      } else {
        alert(this.selectedCity);
      }
    },
  },
};
</script>
