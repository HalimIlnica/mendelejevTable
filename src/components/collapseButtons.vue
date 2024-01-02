<template>
  <div class="main-container">
    <div class="text-center d-flex pb-4">
      <v-btn class="ma-2" @click="toggleAll">
        Shfaqi te gjitha
      </v-btn>
      <v-btn class="ma-2" @click="none">
        asnje
      </v-btn>
    </div>

    <v-expansion-panels v-model="panel" multiple>
      <v-expansion-panel title="Oksidet" value="Oksidet">
        <v-simple-table class="custom-table" v-if="panel.includes('Oksidet')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                 <!-- background-color: #C0C0C0; -->
                <td style="text-align: center;" colspan="4"><b>Oksidet</b></td>
              </tr>
              <tr>
                 <!-- background-color: #DCDCDC -->
                <td style="text-align: center;" colspan="2">Okside acide</td>
                <td style="text-align: center;" colspan="2">Okside bazike</td>
              </tr>
              <tr>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>SO2</td>
                <td>Dioksid squfuri</td>
                <td>Na2O</td>
                <td>Oksid natriumi</td>
              </tr>
              <tr>
                <td>SO3</td>
                <td>Trioksid squfuri</td>
                <td>MgO</td>
                <td>Oksid magenzi</td>
              </tr>
              <tr>
                <td>CO2</td>
                <td>Dioksid karboni</td>
                <td>CuO</td>
                <td>Oksid bakri (II)</td>
              </tr>
              <tr>
                <td>CO</td>
                <td>Monoksid karboni</td>
                <td>Cu2O3</td>
                <td>Oksid bakri (III)</td>
              </tr>
              <tr>
                <td>P2O5</td>
                <td>Oksid magenzi</td>
                <td>Al2O3</td>
                <td>Oksid alumini</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Acidet" value="Acidet">
        <v-simple-table class="custom-table" v-if="panel.includes('Acidet')">
          <template v-slot:default>
            <tbody class="acidetDesign">
              <tr>
                <td style="text-align: center;" colspan="4"><b>Acidet</b></td>
              </tr>
              <tr>
                <td style="text-align: center;" colspan="2">Hidroacide</td>
                <td style="text-align: center;" colspan="2">Oksiacide</td>
              </tr>
              <tr>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>HCl</td>
                <td>Acid klorhidrik</td>
                <td>HNO2</td>
                <td>Acid nitror</td>
              </tr>
              <tr>
                <td>H2S</td>
                <td>Acid sulfhidrik</td>
                <td>HNO3</td>
                <td>Acid nitric</td>
              </tr>
              <tr>
                <td>HF</td>
                <td>Acid fluorhidrik</td>
                <td>H2SO3</td>
                <td>Acid sulfuror</td>
              </tr>
              <tr>
                <td>HI</td>
                <td>Acid jodhiidrik</td>
                <td>H2SO4</td>
                <td>Acid sulfuric</td>
              </tr>
              <tr>
                <td>HBr</td>
                <td>Acid bromhidrik</td>
                <td>H3PO4</td>
                <td>Acid fosforik</td>
              </tr>
              <tr>
                <td></td>
                <td></td>
                <td>H2CO3</td>
                <td>Acid karbonik</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Bazat" value="Bazat">
        <v-simple-table class="custom-table" v-if="panel.includes('Bazat')">
          <template v-slot:default>
            <tbody class="bazatDesign">
              <tr>
                <td style="text-align: center;" colspan="2"><b>Bazat</b></td>
              </tr>
              <tr>
                <td style="text-align: center;" colspan="1">Formula</td>
                <td style="text-align: center;" colspan="1">Emërtimi</td>
              </tr>
              <tr>
                <td>KOH</td>
                <td>Hidroksid kaliumi</td>
              </tr>
              <tr>
                <td>NaOH</td>
                <td>Hidroksid natriumi</td>
              </tr>
              <tr>
                <td>Mg(OH)2</td>
                <td>Hidroksid magnezi</td>
              </tr>
              <tr>
                <td>Cu(OH)2</td>
                <td>Hidroksid bakri (II)</td>
              </tr>
              <tr>
                <td>Cu(OH)3</td>
                <td>Hidroksid bakri (III)</td>
              </tr>
              <tr>
                <td>Fe(OH)2</td>
                <td>Hidroksid hekuri (II)</td>
              </tr>
              <tr>
                <td>Fe(OH)3</td>
                <td>Hidroksid hekuri (III)</td>
              </tr>
              <tr>
                <td>Al(OH)3</td>
                <td>Hidroksid alumini</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Kriperat" value="Kriperat">
        <v-simple-table class="custom-table" v-if="panel.includes('Kriperat')">
          <template v-slot:default>
            <tbody class="kriperatDesign">
              <tr>
                <td style="text-align: center;" colspan="4"><b>Kripërat</b></td>
              </tr>
              <tr>
                <td style="text-align: center;" colspan="2">Formohet me mbetje hidroacide</td>
                <td style="text-align: center;" colspan="2">Formohet me mbetje oksiacide</td>
              </tr>
              <tr>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>NaCl</td>
                <td>Klorur natriumi</td>
                <td>NaNO2</td>
                <td>Nitrit natriumi</td>
              </tr>
              <tr>
                <td>K2S</td>
                <td>Sulfur kaliumi</td>
                <td>Mg(NO3)2</td>
                <td>Nitrat magnezi</td>
              </tr>
              <tr>
                <td>MgF2</td>
                <td>Florur magnezi</td>
                <td>CuSO3</td>
                <td>Sulfit bakri</td>
              </tr>
              <tr>
                <td>CuI2</td>
                <td>Jodur bakri</td>
                <td>FeSO4</td>
                <td>Sulfat hekuri</td>
              </tr>
              <tr>
                <td>AlBr3</td>
                <td>Bromur alumini</td>
                <td>AlPO4</td>
                <td>Fosfat alumini</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>



<style scoped>
.main-container{
    margin-top: 5%;
    margin-bottom: 5%;
}
  .table-container {
    margin: 0 auto;
    width: 90%;
  }
  .orkidetDesign, .acidetDesign .bazatDesign .kriperatDesign {
    border-collapse: collapse;
    width: 100%;
  }

  .orkidetDesign th .orkidetDesign td, 
  .acidetDesign th .acidetDesign tr,
  .bazatDesign th .bazatDesign tr,
  .kriperatDesign th .kriperatDesign tr 
  {
    border: 1px solid #ddd;
    padding: 12px;
    text-align: left;
  }

  .orkidetDesign th, 
  .acidetDesign th,
  .bazatDesign th,
  .kriperatDesign th {
    /* background-color: #C0C0C0; */
    color: #333;
    font-weight: bold;
  }

  .orkidetDesign tr:nth-child(even),
  .acidetDesign tr:nth-child(even),
  .bazatDesign tr:nth-child(even),
  .kriperatDesign tr:nth-child(even)
   {
    background-color: #f2f2f2;
  }

  .orkidetDesign tr:hover,
  /* .acidetDesign tr:hover,
  .bazatDesign,
  .kriperatDesign  */
  {
    background-color: #ddd;
  }

.v-expansion-panel{
    max-width: 55%;
}
.d-flex {
    display: flex !important;
    flex-wrap: wrap;
    align-content: stretch;
    justify-content: center;
}
.custom-table {
  border-collapse: collapse;
  width: 100%;
}

.custom-table td,
.custom-table th {
  border: 1px solid #ddd;
  padding: 5px;
  text-align: left;
  font-size: 14px;
}

.custom-table th {
  /* background-color: #f2f2f2; */
}
</style>

<script>
export default {
  data() {
    return {
      panel: [],
    };
  },
  methods: {
    toggleAll() {
      if (this.panel.length === 4) {
        this.none();
      } else {
        this.all();
      }
    },
    all() {
      this.panel = ['Oksidet', 'Acidet', 'Bazat', 'Kriperat'];
    },
    none() {
      this.panel = [];
    },
  },
};
</script>
