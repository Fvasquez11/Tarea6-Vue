<script>
export default {
  data() {
    return {
      cars: [
        {
          brand: "Chevrolet",
          model: "Sonic",
          year: 2016,
          fuel: "Bencina",
          gearbox: "Manual",
        },
        {
          brand: "Chevrolet",
          model: "Traverse",
          year: 2020,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
        {
          brand: "Citroen",
          model: "C3 Aircross",
          year: 2021,
          fuel: "Bencina",
          gearbox: "Manual",
        },
        {
          brand: "Citroen",
          model: "C5 Crosstourer",
          year: 2014,
          fuel: "Diesel",
          gearbox: "Automatica",
        },
        {
          brand: "Fiat",
          model: "Panda City Cross",
          year: 2017,
          fuel: "Bencina",
          gearbox: "Manual",
        },
        {
          brand: "Fiat",
          model: "Fullback",
          year: 2016,
          fuel: "Diesel",
          gearbox: "Automatica",
        },
        {
          brand: "Fiat",
          model: "Uno",
          year: 2010,
          fuel: "Bencina",
          gearbox: "Manual",
        },
        {
          brand: "Honda",
          model: "Odyssey",
          year: 2020,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
        {
          brand: "Honda",
          model: "Pilot",
          year: 2018,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
        {
          brand: "Honda",
          model: "Passport",
          year: 2018,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
        {
          brand: "Kia",
          model: "Telluride",
          year: 2022,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
        {
          brand: "Kia",
          model: "Forte",
          year: 2021,
          fuel: "Bencina",
          gearbox: "Manual",
        },
        {
          brand: "Mahindra",
          model: "Thar",
          year: 2010,
          fuel: "Diesel",
          gearbox: "Manual",
        },
        {
          brand: "Mahindra",
          model: "Bolero",
          year: 2011,
          fuel: "Diesel",
          gearbox: "Manual",
        },
        {
          brand: "Mazda",
          model: "CX-9",
          year: 2016,
          fuel: "Bencina",
          gearbox: "Automatica",
        },
      ],

      fields: [
        { key: "brand", label: "Marca", sortable: true },
        { key: "model", label: "Modelo", sortable: true },
        { key: "year", label: "Año", sortable: true },
        { key: "fuel", label: "Combustible", sortable: true },
        { key: "gearbox", label: "Transmisión", sortable: true },
      ],

      brands: [
        { value: null, text: "Marca" },
        { value: "Chevrolet", text: "Chevrolet" },
        { value: "Citroen", text: "Citroen" },
        { value: "Fiat", text: "Fiat" },
        { value: "Honda", text: "Honda" },
        { value: "Kia", text: "Kia" },
        { value: "Mahindra", text: "Mahindra" },
        { value: "Mazda", text: "Mazda" },
      ],

      Fuels: [
        { value: null, text: "Combustible" },
        { value: "Bencina", text: "Bencina" },
        { value: "Diesel", text: "Diesel" },
      ],

      gearboxs: [
        { value: null, text: "Transmisión" },
        { value: "Manual", text: "Manual" },
        { value: "Automatica", text: "Automática" },
      ],

      filters: false,
      keyword: "",
      selectedBrand: "",
      year: "",
      selectedGearbox: "",
      selectedFuel: "",
    };
  },
  computed: {
    filteredCars: function () {
      if (this.filters) {
        return this.cars.filter(
          (cars) =>
            (!cars.model
              .toLowerCase()
              .trim()
              .indexOf(this.keyword.toLowerCase().trim()) ||
              !cars.brand
                .toLowerCase()
                .trim()
                .indexOf(this.keyword.toLowerCase().trim()) ||
              !cars.gearbox
                .toLowerCase()
                .trim()
                .indexOf(this.keyword.toLowerCase().trim()) ||
              !cars.fuel
                .toLowerCase()
                .trim()
                .indexOf(this.keyword.toLowerCase().trim())) &&
            !cars.brand.indexOf(this.selectedBrand) &&
            !cars.gearbox.indexOf(this.selectedGearbox) &&
            !cars.fuel.indexOf(this.selectedFuel)
        );
      } else {
        return this.cars.filter(
          (cars) =>
            !cars.model
              .toLowerCase()
              .trim()
              .indexOf(this.keyword.toLowerCase().trim()) ||
            !cars.brand
              .toLowerCase()
              .trim()
              .indexOf(this.keyword.toLowerCase().trim()) ||
            !cars.gearbox
              .toLowerCase()
              .trim()
              .indexOf(this.keyword.toLowerCase().trim()) ||
            !cars.fuel
              .toLowerCase()
              .trim()
              .indexOf(this.keyword.toLowerCase().trim())
        );
      }
    },
  },
};
</script>
<template>
  <main>
    <div class="body">
      <h1 class="searchTitle">Busqueda</h1>
      <div class="bar">
        <div>
          <b-form-input
            v-model.trim="keyword"
            placeholder="Buscar por modelo"
          ></b-form-input>
        </div>

        <b-form-checkbox v-model="filters">Filtros</b-form-checkbox>

        <b-form-select
          v-if="filters"
          v-model="selectedBrand"
          :options="brands"
        ></b-form-select>

        <b-form-select
          v-if="filters"
          v-model="selectedFuel"
          :options="Fuels"
        ></b-form-select>

        <b-form-select
          v-if="filters"
          v-model="selectedGearbox"
          :options="gearboxs"
        ></b-form-select>
      </div>
      <br />
      <div class="table">
        <b-table striped hover :items="filteredCars" :fields="fields"></b-table>
      </div>
    </div>
  </main>
</template>

<style>
.body {
  padding: 3%;
}
.bar {
  display: grid;
  grid-template-columns: 40% 4% 8% 8% 8%;
  gap: 10px;
}
</style>