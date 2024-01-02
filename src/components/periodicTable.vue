<!--
<template>
  <v-container>
    <v-row class="mb-2">
      <v-col v-for="(element, index) in elements" :key="index" cols="1" class="text-center custom-col">
        <v-card class="custom-box" @click="squareClick(element)" @mouseover="squareHover(true, element)" @mouseleave="squareHover(false, element)" :style="{ backgroundColor: element.backgroundColor }">
            <v-card-text class="lineNumber">
                <div class="lineNumber">{{ element.atomicNumber }}</div>
            </v-card-text> -->
          <!-- <v-card-title class="headline d-flex align-center justify-center">{{ element.symbol }}</v-card-title> -->
          <!--<v-card-title class="headline d-flex align-center justify-center">
            <div class="symbol">{{ element.symbol }}</div>
          </v-card-title>
          <v-card-subtitle class="lineName">
            {{ element.name }}
          </v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template> -->

<!-- --body-bg: rgb(243, 246, 248); -->

<template>
  <v-container>
    <v-row v-for="(row, rowIndex) in elementsInRows" :key="rowIndex" class="rowStyle">
      <v-col v-for="(element, colIndex) in row" :key="colIndex" cols="1" class="text-center custom-col">
        <v-card v-if="element" class="custom-box" @click="squareClick(element)" @mouseover="squareHover(true, element)" @mouseleave="squareHover(false, element)" :style="{ backgroundColor: element.backgroundColor }">
          <v-card-text class="lineNumber">
            <div class="lineNumber">{{ element.atomicNumber }}</div>
          </v-card-text>
          <v-card-title class="headline d-flex align-center justify-center">
            <div class="symbol">{{ element.symbol }}</div>
          </v-card-title>
          <v-card-subtitle class="lineName">
            {{ element.name }}
          </v-card-subtitle>
        </v-card>
        <div v-else class="custom-box empty-box"></div>
      </v-col>
    </v-row>
  </v-container>
    <v-container>
    <v-row v-for="(row, rowIndex) in elementsInRowsSecond" :key="rowIndex" class="rowStyle2">
      <v-col v-for="(element, colIndex) in row" :key="colIndex" cols="1" class="text-center custom-col">
        <v-card v-if="element" class="custom-box" @click="squareClick(element)" @mouseover="squareHover(true, element)" @mouseleave="squareHover(false, element)" :style="{ backgroundColor: element.backgroundColor }">
          <v-card-text class="lineNumber">
            <div class="lineNumber">{{ element.atomicNumber }}</div>
          </v-card-text>
          <v-card-title class="headline d-flex align-center justify-center">
            <div class="symbol">{{ element.symbol }}</div>
          </v-card-title>
          <v-card-subtitle class="lineName">
            {{ element.name }}
          </v-card-subtitle>
        </v-card>
        <div v-else class="custom-box empty-box"></div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      elements: [
            { atomicNumber: 1, symbol: 'H', name: 'Hidrogjen', atomicWeight: 1.008, backgroundColor: '#8CED8C' },
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            { atomicNumber: 2, symbol: 'He', name: 'Helium', atomicWeight: 4.0026, backgroundColor: '#E5BDE5'},
            { atomicNumber: 3, symbol: 'Li', name: 'Litium', atomicWeight: 6.94, backgroundColor: '#EACE5D' },
            { atomicNumber: 4, symbol: 'Be', name: 'Berilium', atomicWeight: 9.0122, backgroundColor: '#F1F165' },
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            { atomicNumber: 5, symbol: 'B', name: 'Bor', atomicWeight: 10.81, backgroundColor: '#9EE5D4' },
            { atomicNumber: 6, symbol: 'C', name: 'Karbon', atomicWeight: 12.011, backgroundColor: '#8CED8C' },
            { atomicNumber: 7, symbol: 'N', name: 'Nitrogjen', atomicWeight: 14.007, backgroundColor: '#8CED8C' },
            { atomicNumber: 8, symbol: 'O', name: 'Oksigjen', atomicWeight: 15.999, backgroundColor: '#8CED8C' },
            { atomicNumber: 9, symbol: 'F', name: 'Fluor', atomicWeight: 18.998, backgroundColor: '#8CED8C' },
            { atomicNumber: 10, symbol: 'Ne', name: 'Neon', atomicWeight: 20.180, backgroundColor: '#E5BDE5' },
            { atomicNumber: 11, symbol: 'Na', name: 'Natrium', atomicWeight: 22.990, backgroundColor: '#EACE5D' },
            { atomicNumber: 12, symbol: 'Mg', name: 'Magnez', atomicWeight: 24.305, backgroundColor: '#F1F165' },
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            { atomicNumber: 13, symbol: 'Al', name: 'Alumin', atomicWeight: 26.982, backgroundColor: '#ACDFEC' },
            { atomicNumber: 14, symbol: 'Si', name: 'Silic', atomicWeight: 28.085, backgroundColor: '#9EE5D4' },
            { atomicNumber: 15, symbol: 'P', name: 'Fosfor', atomicWeight: 30.974, backgroundColor: '#8CED8C' },
            { atomicNumber: 16, symbol: 'S', name: 'Squfur', atomicWeight: 32.06, backgroundColor: '#8CED8C' },
            { atomicNumber: 17, symbol: 'Cl', name: 'Klor', atomicWeight: 35.45, backgroundColor: '#8CED8C' },
            { atomicNumber: 18, symbol: 'Ar', name: 'Argon', atomicWeight: 39.948, backgroundColor: '#E5BDE5' },
            { atomicNumber: 19, symbol: 'K', name: 'Kalium', atomicWeight: 39.098, backgroundColor: '#EACE5D' },
            { atomicNumber: 20, symbol: 'Ca', name: 'Kalcium', atomicWeight: 40.078, backgroundColor: '#F1F165' },
            { atomicNumber: 21, symbol: 'Sc', name: 'Skandium', atomicWeight: 44.956, backgroundColor: '#FAC5B7' },
            { atomicNumber: 22, symbol: 'Ti', name: 'Titanium', atomicWeight: 47.867, backgroundColor: '#FAC5B7' },
            { atomicNumber: 23, symbol: 'V', name: 'Vanadium', atomicWeight: 50.942, backgroundColor: '#FAC5B7' },
            { atomicNumber: 24, symbol: 'Cr', name: 'Krom', atomicWeight: 51.996, backgroundColor: '#FAC5B7' },
            { atomicNumber: 25, symbol: 'Mn', name: 'Mangan', atomicWeight: 54.938, backgroundColor: '#FAC5B7' },
            { atomicNumber: 26, symbol: 'Fe', name: 'Hekur', atomicWeight: 55.845, backgroundColor: '#FAC5B7' },
            { atomicNumber: 27, symbol: 'Ni', name: 'Nikel', atomicWeight: 58.693, backgroundColor: '#FAC5B7' },
            { atomicNumber: 28, symbol: 'Co', name: 'Kobalt', atomicWeight: 58.933, backgroundColor: '#FAC5B7' },
            { atomicNumber: 29, symbol: 'Cu', name: 'Baker', atomicWeight: 63.546, backgroundColor: '#FAC5B7' },
            { atomicNumber: 30, symbol: 'Zn', name: 'Zink', atomicWeight: 65.38, backgroundColor: '#FAC5B7' },
            { atomicNumber: 31, symbol: 'Ga', name: 'Galium', atomicWeight: 69.723, backgroundColor: '#ACDFEC' },
            { atomicNumber: 32, symbol: 'Ge', name: 'Germanium', atomicWeight: 72.630, backgroundColor: '#9EE5D4' },
            { atomicNumber: 33, symbol: 'As', name: 'Arsenik', atomicWeight: 74.922, backgroundColor: '#9EE5D4' },
            { atomicNumber: 34, symbol: 'Se', name: 'Selen', atomicWeight: 78.971, backgroundColor: '#8CED8C' },
            { atomicNumber: 35, symbol: 'Br', name: 'Brom', atomicWeight: 79.904, backgroundColor: '#8CED8C' },
            { atomicNumber: 36, symbol: 'Kr', name: 'Kripton', atomicWeight: 83.798, backgroundColor: '#E5BDE5' },
            { atomicNumber: 37, symbol: 'Rb', name: 'Rubidium', atomicWeight: 85.468, backgroundColor: '#EACE5D' },
            { atomicNumber: 38, symbol: 'Sr', name: 'Stroncium', atomicWeight: 87.62, backgroundColor: '#F1F165' },
            { atomicNumber: 39, symbol: 'Y', name: 'Yttrium', atomicWeight: 88.906, backgroundColor: '#FAC5B7' },
            { atomicNumber: 40, symbol: 'Zr', name: 'Zirkon', atomicWeight: 91.224, backgroundColor: '#FAC5B7' },
            { atomicNumber: 41, symbol: 'Nb', name: 'Niobium', atomicWeight: 92.906, backgroundColor: '#FAC5B7' },
            { atomicNumber: 42, symbol: 'Mo', name: 'Molybdenum', atomicWeight: 95.95, backgroundColor: '#FAC5B7' },
            { atomicNumber: 43, symbol: 'Tc', name: 'Technetium', atomicWeight: 98, backgroundColor: '#FAC5B7' },
            { atomicNumber: 44, symbol: 'Ru', name: 'Ruthenium', atomicWeight: 101.07, backgroundColor: '#FAC5B7' },
            { atomicNumber: 45, symbol: 'Rh', name: 'Rhodium', atomicWeight: 102.91, backgroundColor: '#FAC5B7' },
            { atomicNumber: 46, symbol: 'Pd', name: 'Palladium', atomicWeight: 106.42, backgroundColor: '#FAC5B7' },
            { atomicNumber: 47, symbol: 'Ag', name: 'Argjend', atomicWeight: 107.87, backgroundColor: '#FAC5B7' },
            { atomicNumber: 48, symbol: 'Cd', name: 'Cadmium', atomicWeight: 112.41, backgroundColor: '#FAC5B7' },
            { atomicNumber: 49, symbol: 'In', name: 'Indium', atomicWeight: 114.82, backgroundColor: '#ACDFEC' },
            { atomicNumber: 50, symbol: 'Sn', name: 'Kallaj', atomicWeight: 118.71, backgroundColor: '#ACDFEC' },
            { atomicNumber: 51, symbol: 'Sb', name: 'Antimoni', atomicWeight: 121.76, backgroundColor: '#9EE5D4' },
            { atomicNumber: 52, symbol: 'Te', name: 'Tellurium', atomicWeight: 127.60, backgroundColor: '#9EE5D4' },
            { atomicNumber: 53, symbol: 'I', name: 'Jod', atomicWeight: 126.90, backgroundColor: '#8CED8C' },
            { atomicNumber: 54, symbol: 'Xe', name: 'Ksenon', atomicWeight: 131.29, backgroundColor: '#E5BDE5' },
            { atomicNumber: 55, symbol: 'Cs', name: 'Cesium', atomicWeight: 132.91, backgroundColor: '#EACE5D' },
            { atomicNumber: 56, symbol: 'Ba', name: 'Barium', atomicWeight: 137.33, backgroundColor: '#F1F165' },
            null,
            // { atomicNumber: 57, symbol: 'La', name: 'Lanthanum', atomicWeight: 138.91 },
            // { atomicNumber: 58, symbol: 'Ce', name: 'Cerium', atomicWeight: 140.12 },
            // { atomicNumber: 59, symbol: 'Pr', name: 'Praseodymium', atomicWeight: 140.91 },
            // { atomicNumber: 60, symbol: 'Nd', name: 'Neodymium', atomicWeight: 144.24 },
            // { atomicNumber: 61, symbol: 'Pm', name: 'Promethium', atomicWeight: 145 },
            // { atomicNumber: 62, symbol: 'Sm', name: 'Samarium', atomicWeight: 150.36 },
            // { atomicNumber: 63, symbol: 'Eu', name: 'Europium', atomicWeight: 151.96 },
            // { atomicNumber: 64, symbol: 'Gd', name: 'Gadolinium', atomicWeight: 157.25 },
            // { atomicNumber: 65, symbol: 'Tb', name: 'Terbium', atomicWeight: 158.93 },
            // { atomicNumber: 66, symbol: 'Dy', name: 'Dysprosium', atomicWeight: 162.50 },
            // { atomicNumber: 67, symbol: 'Ho', name: 'Holmium', atomicWeight: 164.93 },
            // { atomicNumber: 68, symbol: 'Er', name: 'Erbium', atomicWeight: 167.26 },
            // { atomicNumber: 69, symbol: 'Tm', name: 'Thulium', atomicWeight: 168.93 },
            // { atomicNumber: 70, symbol: 'Yb', name: 'Ytterbium', atomicWeight: 173.04 },
            // { atomicNumber: 71, symbol: 'Lu', name: 'Lutetium', atomicWeight: 174.97 },
            { atomicNumber: 72, symbol: 'Hf', name: 'Hafnium', atomicWeight: 178.49, backgroundColor: '#FAC5B7' },
            { atomicNumber: 73, symbol: 'Ta', name: 'Tantalum', atomicWeight: 180.95, backgroundColor: '#FAC5B7' },
            { atomicNumber: 74, symbol: 'W', name: 'Tungsten', atomicWeight: 183.84, backgroundColor: '#FAC5B7' },
            { atomicNumber: 75, symbol: 'Re', name: 'Rhenium', atomicWeight: 186.21, backgroundColor: '#FAC5B7' },
            { atomicNumber: 76, symbol: 'Os', name: 'Osmium', atomicWeight: 190.23, backgroundColor: '#FAC5B7' },
            { atomicNumber: 77, symbol: 'Ir', name: 'Iridium', atomicWeight: 192.22, backgroundColor: '#FAC5B7' },
            { atomicNumber: 78, symbol: 'Pt', name: 'Platinum', atomicWeight: 195.08, backgroundColor: '#FAC5B7' },
            { atomicNumber: 79, symbol: 'Au', name: 'Ar', atomicWeight: 196.97, backgroundColor: '#FAC5B7' },
            { atomicNumber: 80, symbol: 'Hg', name: 'Merkur', atomicWeight: 200.59, backgroundColor: '#FAC5B7' },
            { atomicNumber: 81, symbol: 'Tl', name: 'Thallium', atomicWeight: 204.38, backgroundColor: '#ACDFEC' },
            { atomicNumber: 82, symbol: 'Pb', name: 'Plumb', atomicWeight: 207.2, backgroundColor: '#ACDFEC' },
            { atomicNumber: 83, symbol: 'Bi', name: 'Bismuth', atomicWeight: 208.98, backgroundColor: '#ACDFEC' },
            { atomicNumber: 84, symbol: 'Po', name: 'Polonium', atomicWeight: 209, backgroundColor: '#ACDFEC' },
            { atomicNumber: 85, symbol: 'At', name: 'Astatine', atomicWeight: 210, backgroundColor: '#9EE5D4' },
            { atomicNumber: 86, symbol: 'Rn', name: 'Radon', atomicWeight: 222, backgroundColor: '#E5BDE5' },
            { atomicNumber: 87, symbol: 'Fr', name: 'Francium', atomicWeight: 223, backgroundColor: '#EACE5D' },
            { atomicNumber: 88, symbol: 'Ra', name: 'Radium', atomicWeight: 226, backgroundColor: '#F1F165' },
            null,
            // { atomicNumber: 89, symbol: 'Ac', name: 'Actinium', atomicWeight: 227 },
            // { atomicNumber: 90, symbol: 'Th', name: 'Thorium', atomicWeight: 232.04 },
            // { atomicNumber: 91, symbol: 'Pa', name: 'Protactinium', atomicWeight: 231.04 },
            // { atomicNumber: 92, symbol: 'U', name: 'Uranium', atomicWeight: 238.03 },
            // { atomicNumber: 93, symbol: 'Np', name: 'Neptunium', atomicWeight: 237 },
            // { atomicNumber: 94, symbol: 'Pu', name: 'Plutonium', atomicWeight: 244 },
            // { atomicNumber: 95, symbol: 'Am', name: 'Americium', atomicWeight: 243 },
            // { atomicNumber: 96, symbol: 'Cm', name: 'Curium', atomicWeight: 247 },
            // { atomicNumber: 97, symbol: 'Bk', name: 'Berkelium', atomicWeight: 247 },
            // { atomicNumber: 98, symbol: 'Cf', name: 'Californium', atomicWeight: 251 },
            // { atomicNumber: 99, symbol: 'Es', name: 'Einsteinium', atomicWeight: 252 },
            // { atomicNumber: 100, symbol: 'Fm', name: 'Fermium', atomicWeight: 257 },
            // { atomicNumber: 101, symbol: 'Md', name: 'Mendelevium', atomicWeight: 258 },
            // { atomicNumber: 102, symbol: 'No', name: 'Nobelium', atomicWeight: 259 },
            // { atomicNumber: 103, symbol: 'Lr', name: 'Lawrencium', atomicWeight: 262 },
            { atomicNumber: 104, symbol: 'Rf', name: 'Rutherfordium', atomicWeight: (267), backgroundColor: '#FAC5B7' }, 
            { atomicNumber: 105, symbol: 'Db', name: 'Dubnium', atomicWeight: (268), backgroundColor: '#FAC5B7' }, 
            { atomicNumber: 106, symbol: 'Sg', name: 'Seaborgium', atomicWeight: (269), backgroundColor: '#FAC5B7' }, 
            { atomicNumber: 107, symbol: 'Bh', name: 'Bohrium', atomicWeight: (270), backgroundColor: '#FAC5B7' },
            { atomicNumber: 108, symbol: 'Hs', name: 'Hassium', atomicWeight: (277), backgroundColor: '#FAC5B7' }, 
            { atomicNumber: 109, symbol: 'Mt', name: 'Meitnerium', atomicWeight: (278), backgroundColor: '#EEE' },
            { atomicNumber: 110, symbol: 'Ds', name: 'Darmstadtium', atomicWeight: (281), backgroundColor: '#EEE' }, 
            { atomicNumber: 111, symbol: 'Rg', name: 'Roentgenium', atomicWeight: (282), backgroundColor: '#EEE' }, 
            { atomicNumber: 112, symbol: 'Cn', name: 'Copernicium', atomicWeight: (285), backgroundColor: '#EEE' },
            { atomicNumber: 113, symbol: 'Nh', name: 'Nihonium', atomicWeight: (286), backgroundColor: '#EEE' }, 
            { atomicNumber: 114, symbol: 'Fl', name: 'Flerovium', atomicWeight: (289), backgroundColor: '#EEE' }, 
            { atomicNumber: 115, symbol: 'Mc', name: 'Moscovium', atomicWeight: (290), backgroundColor: '#EEE' },
            { atomicNumber: 116, symbol: 'Lv', name: 'Livermorium', atomicWeight: (293), backgroundColor: '#EEE' },
            { atomicNumber: 117, symbol: 'Ts', name: 'Tennessine', atomicWeight: (284), backgroundColor: '#EEE' },
            { atomicNumber: 118, symbol: 'Og', name: 'Oganesson', atomicWeight: (294), backgroundColor: '#EEE' },
      ], 

      secondElements: [
            null,
            null,
            null,
            { atomicNumber: 57, symbol: 'La', name: 'Lanthanum', atomicWeight: 138.91, backgroundColor: '#E8D19C' },
            { atomicNumber: 58, symbol: 'Ce', name: 'Cerium', atomicWeight: 140.12, backgroundColor: '#E8D19C' },
            { atomicNumber: 59, symbol: 'Pr', name: 'Praseodymium', atomicWeight: 140.91, backgroundColor: '#E8D19C' },
            { atomicNumber: 60, symbol: 'Nd', name: 'Neodymium', atomicWeight: 144.24, backgroundColor: '#E8D19C' },
            { atomicNumber: 61, symbol: 'Pm', name: 'Promethium', atomicWeight: 145, backgroundColor: '#E8D19C' },
            { atomicNumber: 62, symbol: 'Sm', name: 'Samarium', atomicWeight: 150.36, backgroundColor: '#E8D19C' },
            { atomicNumber: 63, symbol: 'Eu', name: 'Europium', atomicWeight: 151.96, backgroundColor: '#E8D19C' },
            { atomicNumber: 64, symbol: 'Gd', name: 'Gadolinium', atomicWeight: 157.25, backgroundColor: '#E8D19C' },
            { atomicNumber: 65, symbol: 'Tb', name: 'Terbium', atomicWeight: 158.93, backgroundColor: '#E8D19C' },
            { atomicNumber: 66, symbol: 'Dy', name: 'Dysprosium', atomicWeight: 162.50, backgroundColor: '#E8D19C' },
            { atomicNumber: 67, symbol: 'Ho', name: 'Holmium', atomicWeight: 164.93, backgroundColor: '#E8D19C' },
            { atomicNumber: 68, symbol: 'Er', name: 'Erbium', atomicWeight: 167.26, backgroundColor: '#E8D19C' },
            { atomicNumber: 69, symbol: 'Tm', name: 'Thulium', atomicWeight: 168.93, backgroundColor: '#E8D19C' },
            { atomicNumber: 70, symbol: 'Yb', name: 'Ytterbium', atomicWeight: 173.04, backgroundColor: '#E8D19C' },
            { atomicNumber: 71, symbol: 'Lu', name: 'Lutetium', atomicWeight: 174.97, backgroundColor: '#E8D19C' },
            null,
            null,
            null,
            { atomicNumber: 89, symbol: 'Ac', name: 'Actinium', atomicWeight: 227, backgroundColor: '#F5CCDA' },
            { atomicNumber: 90, symbol: 'Th', name: 'Thorium', atomicWeight: 232.04, backgroundColor: '#F5CCDA' },
            { atomicNumber: 91, symbol: 'Pa', name: 'Protactinium', atomicWeight: 231.04, backgroundColor: '#F5CCDA' },
            { atomicNumber: 92, symbol: 'U', name: 'Uranium', atomicWeight: 238.03, backgroundColor: '#F5CCDA' },
            { atomicNumber: 93, symbol: 'Np', name: 'Neptunium', atomicWeight: 237, backgroundColor: '#F5CCDA' },
            { atomicNumber: 94, symbol: 'Pu', name: 'Plutonium', atomicWeight: 244, backgroundColor: '#F5CCDA' },
            { atomicNumber: 95, symbol: 'Am', name: 'Americium', atomicWeight: 243, backgroundColor: '#F5CCDA' },
            { atomicNumber: 96, symbol: 'Cm', name: 'Curium', atomicWeight: 247, backgroundColor: '#F5CCDA' },
            { atomicNumber: 97, symbol: 'Bk', name: 'Berkelium', atomicWeight: 247, backgroundColor: '#F5CCDA' },
            { atomicNumber: 98, symbol: 'Cf', name: 'Californium', atomicWeight: 251, backgroundColor: '#F5CCDA' },
            { atomicNumber: 99, symbol: 'Es', name: 'Einsteinium', atomicWeight: 252, backgroundColor: '#F5CCDA' },
            { atomicNumber: 100, symbol: 'Fm', name: 'Fermium', atomicWeight: 257, backgroundColor: '#F5CCDA' },
            { atomicNumber: 101, symbol: 'Md', name: 'Mendelevium', atomicWeight: 258, backgroundColor: '#F5CCDA' },
            { atomicNumber: 102, symbol: 'No', name: 'Nobelium', atomicWeight: 259, backgroundColor: '#F5CCDA' },
            { atomicNumber: 103, symbol: 'Lr', name: 'Lawrencium', atomicWeight: 262, backgroundColor: '#F5CCDA' },
      ]
    };
  },
  created(){
    console.log('TTTTTTtttttt');
  },
    computed: {
    elementsInRows() {
      const elementsPerRow = 18;
      const rows = [];
      for (let i = 0; i < this.elements.length; i += elementsPerRow) {
        const row = this.elements.slice(i, i + elementsPerRow);
        rows.push(row);
      }
      return rows;
    },
    elementsInRowsSecond(){
      const elementsPerRowSecond = 18;
      const rows = [];
      for (let i = 0; i < this.secondElements.length; i += elementsPerRowSecond) {
        const row = this.secondElements.slice(i, i + elementsPerRowSecond);
        rows.push(row);
      }
      return rows;
    },
  },
  methods: {
    squareClick(element) {
        console.log('square', element)
        this.$emit('selectedElement', element)
    },
    //  squareHover(isHovered, element) {
    // //   if (isHovered) {
    // //     // Call your method or perform actions when the card is hovered
    // //     console.log(`Hovered over ${element.name}`);
    // //     this.$emit('selectedElement', element)
    // //   } else {
    // //     // Call your method or perform actions when the mouse leaves the card
    // //     console.log(`Left ${element.name}`);
    // //   }
    // },
  }
};
</script>

<style scoped>
.rowStyle{
  display: flex;
  justify-content: center;
}
.rowStyle2{
  display: flex;
  justify-content: center;  
  margin-top: 0.1%;
}
.middle-elements {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px;
}
.empty-box {
  width: 70px;
  height: 70px;
  box-sizing: border-box;
  position: relative;
  /* background-color: #fff; */
  border: none;
  /* background-color: #f0f8ff; */
  /* border: 1px solid #ccc; */
}

.symbol {
  font-size: 16px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.custom-col {
 margin: -1.8%; /* Adjust the margin between columns */
}
.lineNumber{
  font-size: 8px;
  position: absolute;
  top: -5%;
  left: 2px;
}
.lineName{
  font-size: 8px;
  position: absolute;
  bottom: -10%; 
  left: -25%;
}
.headline{
    font-size: 14px;
}
.custom-box {
  width: 70%; /* Adjust the width to your preference */
  height: 70px; /* Adjust the height to your preference */
  box-sizing: border-box;
  max-height: 65%;
  /* border: none; */
}
.d-flex {
  display: flex;
}

.align-center {
  align-items: center;
}

.justify-center {
  justify-content: center;
}
</style>
