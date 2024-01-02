<template>
  <div class="tables-container">
    <table class="letter-table">
      <tbody>
        <tr>
          <td class="letter-cell">
            <span class="left-letter">Numri atomik</span>
            <span class="right-letter">
                <!-- {{selectedEl ? elementsData.filter(x => x.atomic_number == selectedEl.atomicNumber)[0].atomic_weight : ''}} -->
                {{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.atomic_number || '' : '' }}
            </span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Gjendja</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.state_at_room_temp || '' : '' }}</span>
          </td>
            <td class="letter-cell">
            <span class="left-letter">Masa atomike</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.atomic_weight || '' : '' }}</span>
          </td>
        </tr>
        <tr> 
          <td class="letter-cell">
            <span class="left-letter">Niveli Energjitik</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.energy_levels || '' : '' }}</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Elektronegativiteti</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.electronegativity || '' : '' }}</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Pika e Shkrirjes</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.melting_point || '' : '' }}</span>
          </td>
        </tr>
        <tr>
          <td class="letter-cell">
            <span class="left-letter">Pika e Vlimit</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.boiling_point || '' : '' }}</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Afiniteti i Elektroneve</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.electron_affinity || '' : '' }}</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Jonizimi</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.ionization_energy || '' : '' }}</span>
          </td>
        </tr>
        <tr>
          <td class="letter-cell">
            <span class="left-letter">Rrezja Atomike</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.radius_calculated || '' : '' }}</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Fortësia</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.hardness_brinell || '' : '' }}</span>
          </td>
          <!-- <td class="letter-cell">
            <span class="left-letter">Modulus,bulk</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.modulus_bulk || '' : '' }}</span>
          </td> -->
          <td class="letter-cell">
            <span class="left-letter">Viti i Zbulimit</span>
            <span class="right-letter">{{ selectedEl && selectedEl.atomicNumber ? elementsData.find(x => x.atomic_number === selectedEl.atomicNumber)?.discovery_year || '' : '' }}</span>
          </td>
        </tr>
      </tbody>
    </table>

    <table class="letter-table2">
      <tbody>
        <tr>
          <th class="letter-cell center-text" colspan="2">
            <span class="left-letter3">METALET</span>
          </th>
          <th class="letter-cell center-text">
            <span class="left-letter">JOMETALET</span>
          </th>
          <th class="letter-cell center-text2" rowspan="4">
            <span class="left-letter vertical">METALOIDET</span>
          </th>
        </tr>
        <tr> 
          <td class="letter-cell" style="backgroundColor: #EACE5D">
            <span class="left-letter">Metalet Alkaline</span>
          </td>
          <td class="letter-cell" style="backgroundColor: #F5CCDA">
            <span class="left-letter">Aktinide</span>
          </td>
          <td class="letter-cell" style="backgroundColor: #8CED8C">
            <span class="left-letter">Jometalet Reaktive</span>
          </td>
        </tr>
        <tr>
          <td class="letter-cell" style="backgroundColor: #F1F165">
            <span class="left-letter">Metalet Alkalino Tokesore </span>
          </td>
          <td class="letter-cell" style="backgroundColor: #FAC5B7">
            <span class="left-letter">Metalet Kalimtare</span>
          </td>
          <td class="letter-cell" style="backgroundColor: #E5BDE5" rowspan="2">
            <span class="left-letter">Gazet e Plogesht</span>
          </td>
        </tr>
        <tr>
          <td class="letter-cell" style="backgroundColor: #E8D19C">
            <span class="left-letter">Lantanide</span>
          </td>
          <td class="letter-cell" style="backgroundColor: #ACDFEC">
            <span class="left-letter">Metalet Post Kalimtare</span>
          </td>
        </tr>
        <!-- <tr>
          <td class="letter-cell">
            <span class="left-letter">Actinide</span>
          </td>
          <td class="letter-cell">
            <span class="left-letter">Hardness,</span>
          </td>
        </tr> -->
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
    props: {
    selectedEl: {
      type: String, // or whatever type selectedEl should be
      required: true,
    },
  },
  data() {
    return {

elementsData: [
    {atomic_number: 1, symbol: "H", name: "Hydrogen", atomic_weight: 1.008, state_at_room_temp: "Gas",
     energy_levels: 1, electronegativity: 2.20, melting_point: 13.99, boiling_point: 20.271,
     electron_affinity: 0.754, ionization_energy: 13.5984, radius_calculated: 0.53,
     hardness_brinell: "N/A", modulus_bulk: "N/A", density_stp: 0.0899, thermal_conductivity: 0.1805,
     specific_heat: 14.304, abundance_universe: 75.0, discovery_year: 1766},

    {atomic_number: 2, symbol: "He", name: "Helium", atomic_weight: 4.0026, state_at_room_temp: "Gas",
     energy_levels: 1, electronegativity: "N/A", melting_point: 0.95, boiling_point: 4.222,
     electron_affinity: 0.0, ionization_energy: 24.5874, radius_calculated: 0.31,
     hardness_brinell: "N/A", modulus_bulk: "N/A", density_stp: 0.1786, thermal_conductivity: 0.1513,
     specific_heat: 5.193, abundance_universe: 23.0, discovery_year: 1868},

    {atomic_number: 3, symbol: "Li", name: "Lithium", atomic_weight: 6.94, state_at_room_temp: "Solid",
     energy_levels: 2, electronegativity: 0.98, melting_point: 453.65, boiling_point: 1615,
     electron_affinity: 0.618, ionization_energy: 5.3917, radius_calculated: 1.67,
     hardness_brinell: 34.3, modulus_bulk: 11.0, density_stp: 0.534, thermal_conductivity: 84.8,
     specific_heat: 3.58, abundance_universe: 0.0062, discovery_year: 1817},

    {atomic_number: 4, symbol: "Be", name: "Beryllium", atomic_weight: 9.0122, state_at_room_temp: "Solid",
     energy_levels: 2, electronegativity: 1.57, melting_point: 1560, boiling_point: 2743,
     electron_affinity: 0.0, ionization_energy: 9.3227, radius_calculated: 1.12,
     hardness_brinell: 376, modulus_bulk: 130.0, density_stp: 1.85, thermal_conductivity: 200.0,
     specific_heat: 1.825, abundance_universe: 0.0002, discovery_year: 1798},

    {atomic_number: 5, symbol: "B", name: "Boron", atomic_weight: 10.81, state_at_room_temp: "Solid",
     energy_levels: 2, electronegativity: 2.04, melting_point: 2349, boiling_point: 4200,
     electron_affinity: 0.277, ionization_energy: 8.298, radius_calculated: 0.87,
     hardness_brinell: "N/A", modulus_bulk: 340.0, density_stp: 2.34, thermal_conductivity: 27.0,
     specific_heat: 1.026, abundance_universe: 0.0006, discovery_year: 1808},

    {atomic_number: 6, symbol: "C", name: "Carbon", atomic_weight: 12.011, state_at_room_temp: "Solid",
     energy_levels: 2, electronegativity: 2.55, melting_point: 3915, boiling_point: 3915,
     electron_affinity: 1.263, ionization_energy: 11.2603, radius_calculated: 0.67,
     hardness_brinell: "N/A", modulus_bulk: 470.0, density_stp: 2.267, thermal_conductivity: 140.0,
     specific_heat: 0.709, abundance_universe: 0.18, discovery_year: "I lashte"},

    {atomic_number: 7, symbol: "N", name: "Nitrogen", atomic_weight: 14.007, state_at_room_temp: "Gas",
    energy_levels: 2, electronegativity: 3.04, melting_point: 63.15, boiling_point: 77.355,
    electron_affinity: 0.072, ionization_energy: 14.5341, radius_calculated: 0.56,
    hardness_brinell: "None", modulus_bulk: "None", density_stp: 0.00125, thermal_conductivity: 0.0258,
    specific_heat: 1.04, abundance_universe: 78.0, discovery_year: 1772},

    {atomic_number: 8, symbol: "O", name: "Oxygen", atomic_weight: 15.999, state_at_room_temp: "Gas",
    energy_levels: 2, electronegativity: 3.44, melting_point: 54.36, boiling_point: 90.188,
    electron_affinity: 1.461, ionization_energy: 13.6181, radius_calculated: 0.48,
    hardness_brinell: "None", modulus_bulk: "None", density_stp: 0.00143, thermal_conductivity: 0.0266,
    specific_heat: 0.918, abundance_universe: 23.0, discovery_year: 1774},

    {atomic_number: 9, symbol: "F", name: "Fluorine", atomic_weight: 18.998, state_at_room_temp: "Gas",
    energy_levels: 2, electronegativity: 3.98, melting_point: 53.53, boiling_point: 85.03,
    electron_affinity: 3.399, ionization_energy: 17.4228, radius_calculated: 0.42,
    hardness_brinell: "None", modulus_bulk: "None", density_stp: 0.0017, thermal_conductivity: 0.0277,
    specific_heat: 0.824, abundance_universe: 0.0003, discovery_year: 1886}, 

    {atomic_number: 10, symbol: "Ne", name: "Neon", atomic_weight: 20.180, state_at_room_temp: "Gas",
    energy_levels: 2, electronegativity: "None", melting_point: 24.56, boiling_point: 27.07,
    electron_affinity: 0.0, ionization_energy: 21.5645, radius_calculated: 0.38,
    hardness_brinell: "None", modulus_bulk: "None", density_stp: 0.0009, thermal_conductivity: 0.0491,
    specific_heat: 1.03, abundance_universe: 0.0001, discovery_year: 1898},

    {atomic_number: 11, symbol: "Na", name: "Sodium", atomic_weight: 22.990, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 0.93, melting_point: 370.87, boiling_point: 1156,
     electron_affinity: 0.548, ionization_energy: 5.1391, radius_calculated: 1.90,
     hardness_brinell: 0.69, modulus_bulk: 6.3, density_stp: 0.97, thermal_conductivity: 140.0,
     specific_heat: 1.23, abundance_universe: 0.002, discovery_year: 1807},
    
    {atomic_number: 12, symbol: "Mg", name: "Magnesium", atomic_weight: 24.305, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 1.31, melting_point: 923, boiling_point: 1380,
     electron_affinity: 0.0, ionization_energy: 7.6462, radius_calculated: 1.45,
     hardness_brinell: 260, modulus_bulk: 45.0, density_stp: 1.74, thermal_conductivity: 156.0,
     specific_heat: 1.04, abundance_universe: 0.025, discovery_year: 1755},
    
    {atomic_number: 13, symbol: "Al", name: "Aluminum", atomic_weight: 26.982, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 1.61, melting_point: 933.47, boiling_point: 2792,
     electron_affinity: 0.432, ionization_energy: 5.9858, radius_calculated: 1.18,
     hardness_brinell: 245, modulus_bulk: 70.0, density_stp: 2.70, thermal_conductivity: 237.0,
     specific_heat: 0.90, abundance_universe: 0.005, discovery_year: 'I lashte'},

     {atomic_number: 14, symbol: "Si", name: "Silicon", atomic_weight: 28.085, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 1.90, melting_point: 1687, boiling_point: 3538,
     electron_affinity: 1.385, ionization_energy: 8.1517, radius_calculated: 1.11,
     hardness_brinell: 880, modulus_bulk: 100.0, density_stp: 2.33, thermal_conductivity: 149.0,
     specific_heat: 0.71, abundance_universe: 0.07, discovery_year: 1824},
    
    {atomic_number: 15, symbol: "P", name: "Phosphorus", atomic_weight: 30.974, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 2.19, melting_point: 317.25, boiling_point: 553,
     electron_affinity: 0.746, ionization_energy: 10.4867, radius_calculated: 1.06,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 1.82, thermal_conductivity: 0.236,
     specific_heat: 0.71, abundance_universe: 0.0001, discovery_year: 1669},
    
    {atomic_number: 16, symbol: "S", name: "Sulfur", atomic_weight: 32.06, state_at_room_temp: "Solid",
     energy_levels: 3, electronegativity: 2.58, melting_point: 388.36, boiling_point: 717.8,
     electron_affinity: 2.077, ionization_energy: 10.36, radius_calculated: 1.02,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 2.07, thermal_conductivity: 0.71,
     specific_heat: 0.71, abundance_universe: 0.05, discovery_year: 'I lashte'},
    
    {atomic_number: 17, symbol: "Cl", name: "Chlorine", atomic_weight: 35.45, state_at_room_temp: "Gas",
     energy_levels: 3, electronegativity: 3.16, melting_point: 171.6, boiling_point: 239.11,
     electron_affinity: 3.613, ionization_energy: 12.9676, radius_calculated: 0.99,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 0.0032, thermal_conductivity: 0.0089,
     specific_heat: 0.48, abundance_universe: 0.0001, discovery_year: 1774},

      {atomic_number: 18, symbol: "Ar", name: "Argon", atomic_weight: 39.948, state_at_room_temp: "Gas",
     energy_levels: 3, electronegativity: 'None', melting_point: 83.81, boiling_point: 87.302,
     electron_affinity: 0.0, ionization_energy: 15.7596, radius_calculated: 0.71,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 0.0018, thermal_conductivity: 0.016,
     specific_heat: 0.52, abundance_universe: 0.0018, discovery_year: 1894},
    
    {atomic_number: 19, symbol: "K", name: "Potassium", atomic_weight: 39.098, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 0.82, melting_point: 336.53, boiling_point: 1032,
     electron_affinity: 0.501, ionization_energy: 4.3407, radius_calculated: 2.31,
     hardness_brinell: 0.363, modulus_bulk: 3.1, density_stp: 0.86, thermal_conductivity: 102.0,
     specific_heat: 0.75, abundance_universe: 0.25, discovery_year: 1807},
    
    {atomic_number: 20, symbol: "Ca", name: "Calcium", atomic_weight: 40.078, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.0, melting_point: 1115, boiling_point: 1757,
     electron_affinity: 0.024, ionization_energy: 6.1132, radius_calculated: 1.74,
     hardness_brinell: 167, modulus_bulk: 17.0, density_stp: 1.54, thermal_conductivity: 200.0,
     specific_heat: 0.647, abundance_universe: 0.015, discovery_year: 'I lashte'},
    
    {atomic_number: 21, symbol: "Sc", name: "Scandium", atomic_weight: 44.956, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.36, melting_point: 1814, boiling_point: 3103,
     electron_affinity: 0.188, ionization_energy: 6.5615, radius_calculated: 1.44,
     hardness_brinell: 750, modulus_bulk: 74.0, density_stp: 2.99, thermal_conductivity: 16.0,
     specific_heat: 0.568, abundance_universe: 0.00003, discovery_year: 1879},
    
    {atomic_number: 22, symbol: "Ti", name: "Titanium", atomic_weight: 47.867, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.54, melting_point: 1941, boiling_point: 3560,
     electron_affinity: 0.084, ionization_energy: 6.8281, radius_calculated: 1.32,
     hardness_brinell: 716, modulus_bulk: 120.0, density_stp: 4.50, thermal_conductivity: 22.0,
     specific_heat: 0.523, abundance_universe: 0.0006, discovery_year: 1791},
    
    {atomic_number: 23, symbol: "V", name: "Vanadium", atomic_weight: 50.942, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.63, melting_point: 2183, boiling_point: 3680,
     electron_affinity: 0.525, ionization_energy: 6.7462, radius_calculated: 1.22,
     hardness_brinell: 628, modulus_bulk: 160.0, density_stp: 6.11, thermal_conductivity: 30.7,
     specific_heat: 0.489, abundance_universe: 0.0001, discovery_year: 1801},
    
    {atomic_number: 24, symbol: "Cr", name: "Chromium", atomic_weight: 51.996, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.66, melting_point: 2180, boiling_point: 2944,
     electron_affinity: 0.666, ionization_energy: 6.7665, radius_calculated: 1.18,
     hardness_brinell: 1120, modulus_bulk: 160.0, density_stp: 7.15, thermal_conductivity: 93.9,
     specific_heat: 0.449, abundance_universe: 0.014, discovery_year: 'I lashte'},
    
    {atomic_number: 25, symbol: "Mn", name: "Manganese", atomic_weight: 54.938, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.55, melting_point: 1519, boiling_point: 2334,
     electron_affinity: 0.0, ionization_energy: 7.434, radius_calculated: 1.39,
     hardness_brinell: 196, modulus_bulk: 120.0, density_stp: 7.35, thermal_conductivity: 7.8,
     specific_heat: 0.479, abundance_universe: 0.0009, discovery_year: 1774},
     
     {atomic_number: 26, symbol: "Fe", name: "Iron", atomic_weight: 55.845, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.83, melting_point: 1811, boiling_point: 3134,
     electron_affinity: 0.156, ionization_energy: 7.9024, radius_calculated: 1.32,
     hardness_brinell: 490, modulus_bulk: 170.0, density_stp: 7.87, thermal_conductivity: 80.4,
     specific_heat: 0.449, abundance_universe: 0.006, discovery_year: 'I lashte'},
    
    {atomic_number: 27, symbol: "Co", name: "Cobalt", atomic_weight: 58.933, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.88, melting_point: 1768, boiling_point: 3200,
     electron_affinity: 0.663, ionization_energy: 7.881, radius_calculated: 1.26,
     hardness_brinell: 700, modulus_bulk: 180.0, density_stp: 8.90, thermal_conductivity: 100.0,
     specific_heat: 0.421, abundance_universe: 0.0003, discovery_year: 'I lashte'},
    
    {atomic_number: 28, symbol: "Ni", name: "Nickel", atomic_weight: 58.693, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.91, melting_point: 1728, boiling_point: 3186,
     electron_affinity: 1.157, ionization_energy: 7.6398, radius_calculated: 1.25,
     hardness_brinell: 638, modulus_bulk: 180.0, density_stp: 8.91, thermal_conductivity: 90.9,
     specific_heat: 0.444, abundance_universe: 0.006, discovery_year: 'I lashte'},
    
    {atomic_number: 29, symbol: "Cu", name: "Copper", atomic_weight: 63.546, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.90, melting_point: 1357.77, boiling_point: 2835,
     electron_affinity: 1.228, ionization_energy: 7.7264, radius_calculated: 1.28,
     hardness_brinell: 369, modulus_bulk: 140.0, density_stp: 8.96, thermal_conductivity: 398.0,
     specific_heat: 0.385, abundance_universe: 0.0005, discovery_year: 'I lashte'},
    
    {atomic_number: 30, symbol: "Zn", name: "Zinc", atomic_weight: 65.38, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.65, melting_point: 692.68, boiling_point: 1180,
     electron_affinity: 0.0, ionization_energy: 9.3942, radius_calculated: 1.31,
     hardness_brinell: 411, modulus_bulk: 70.0, density_stp: 7.13, thermal_conductivity: 116.0,
     specific_heat: 0.388, abundance_universe: 0.007, discovery_year: 'I lashte'},

     	{atomic_number: 31, symbol: "Ga", name: "Gallium", atomic_weight: 69.723, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 1.81, melting_point: 302.91, boiling_point: 2673,
     electron_affinity: 0.3, ionization_energy: 5.9993, radius_calculated: 1.26,
     hardness_brinell: 60.0, modulus_bulk: 9.6, density_stp: 5.91, thermal_conductivity: 40.6,
     specific_heat: 0.371, abundance_universe: 0.00003, discovery_year: 1875},
    
    {atomic_number: 32, symbol: "Ge", name: "Germanium", atomic_weight: 72.63, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 2.01, melting_point: 1211.4, boiling_point: 3106,
     electron_affinity: 1.232, ionization_energy: 7.8994, radius_calculated: 1.22,
     hardness_brinell: 762.5, modulus_bulk: 75.0, density_stp: 5.32, thermal_conductivity: 60.2,
     specific_heat: 0.32, abundance_universe: 0.0006, discovery_year: 1886},
    
    {atomic_number: 33, symbol: "As", name: "Arsenic", atomic_weight: 74.922, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 2.18, melting_point: 1090, boiling_point: 887,
     electron_affinity: 0.814, ionization_energy: 9.7886, radius_calculated: 1.20,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 5.73, thermal_conductivity: 50.2,
     specific_heat: 0.33, abundance_universe: 0.0002, discovery_year: 'I lashte'},
    
    {atomic_number: 34, symbol: "Se", name: "Selenium", atomic_weight: 78.971, state_at_room_temp: "Solid",
     energy_levels: 4, electronegativity: 2.55, melting_point: 494, boiling_point: 958,
     electron_affinity: 2.021, ionization_energy: 9.7524, radius_calculated: 1.16,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 4.79, thermal_conductivity: 0.52,
     specific_heat: 0.705, abundance_universe: 0.00005, discovery_year: 1817},
    
    {atomic_number: 35, symbol: "Br", name: "Bromine", atomic_weight: 79.904, state_at_room_temp: "Liquid",
     energy_levels: 4, electronegativity: 2.96, melting_point: 265.8, boiling_point: 332,
     electron_affinity: 3.365, ionization_energy: 11.8138, radius_calculated: 1.14,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 3.12, thermal_conductivity: 0.122,
     specific_heat: 0.474, abundance_universe: 0.0004, discovery_year: 1826},
    
    {atomic_number: 36, symbol: "Kr", name: "Krypton", atomic_weight: 83.798, state_at_room_temp: "Gas",
     energy_levels: 4, electronegativity: 'None', melting_point: 115.79, boiling_point: 119.93,
     electron_affinity: 0.0, ionization_energy: 13.9996, radius_calculated: 0.88,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 0.0037, thermal_conductivity: 0.00943,
     specific_heat: 0.248, abundance_universe: 0.0001, discovery_year: 1898},
	 
	     {atomic_number: 37, symbol: "Rb", name: "Rubidium", atomic_weight: 85.468, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 0.82, melting_point: 312.46, boiling_point: 961,
     electron_affinity: 0.47, ionization_energy: 4.1771, radius_calculated: 2.48,
     hardness_brinell: 0.216, modulus_bulk: 2.5, density_stp: 1.53, thermal_conductivity: 58.2,
     specific_heat: 0.363, abundance_universe: 0.0002, discovery_year: 1861},
    
    {atomic_number: 38, symbol: "Sr", name: "Strontium", atomic_weight: 87.62, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 0.95, melting_point: 1050, boiling_point: 1655,
     electron_affinity: 0.52, ionization_energy: 5.6949, radius_calculated: 2.15,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 2.63, thermal_conductivity: 35.3,
     specific_heat: 0.301, abundance_universe: 0.0003, discovery_year: 1790},
    
    {atomic_number: 39, symbol: "Y", name: "Yttrium", atomic_weight: 88.906, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.22, melting_point: 1799, boiling_point: 3609,
     electron_affinity: 0.307, ionization_energy: 6.2173, radius_calculated: 1.80,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 4.47, thermal_conductivity: 17.2,
     specific_heat: 0.298, abundance_universe: 0.0002, discovery_year: 1794},
    
    {atomic_number: 40, symbol: "Zr", name: "Zirconium", atomic_weight: 91.224, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.33, melting_point: 2128, boiling_point: 4682,
     electron_affinity: 0.426, ionization_energy: 6.6339, radius_calculated: 1.56,
     hardness_brinell: 650, modulus_bulk: 94.0, density_stp: 6.52, thermal_conductivity: 22.7,
     specific_heat: 0.278, abundance_universe: 0.00002, discovery_year: 1789},
    
    {atomic_number: 41, symbol: "Nb", name: "Niobium", atomic_weight: 92.906, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.6, melting_point: 2750, boiling_point: 5017,
     electron_affinity: 0.893, ionization_energy: 6.7589, radius_calculated: 1.47,
     hardness_brinell: 735, modulus_bulk: 105.0, density_stp: 8.57, thermal_conductivity: 53.7,
     specific_heat: 0.265, abundance_universe: 0.0002, discovery_year: 1801},
    
    {atomic_number: 42, symbol: "Mo", name: "Molybdenum", atomic_weight: 95.95, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.16, melting_point: 2896, boiling_point: 4912,
     electron_affinity: 0.747, ionization_energy: 7.0924, radius_calculated: 1.38,
     hardness_brinell: 1500, modulus_bulk: 230.0, density_stp: 10.22, thermal_conductivity: 138.0,
     specific_heat: 0.251, abundance_universe: 0.0002, discovery_year: 1778},
    
    {atomic_number: 43, symbol: "Tc", name: "Technetium", atomic_weight: 98, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.9, melting_point: 2430, boiling_point: 4538,
     electron_affinity: 0.55, ionization_energy: 7.28, radius_calculated: 1.35,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 11.5, thermal_conductivity: 50.6,
     specific_heat: 0.24, abundance_universe: 'Trace', discovery_year: 1937},
    
    {atomic_number: 44, symbol: "Ru", name: "Ruthenium", atomic_weight: 101.07, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.2, melting_point: 2607, boiling_point: 4423,
     electron_affinity: 1.046, ionization_energy: 7.3605, radius_calculated: 1.3,
     hardness_brinell: 2160, modulus_bulk: 220.0, density_stp: 12.45, thermal_conductivity: 117.0,
     specific_heat: 0.238, abundance_universe: 0.0001, discovery_year: 1844},
	 
	{atomic_number: 45, symbol: "Rh", name: "Rhodium", atomic_weight: 102.91, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.28, melting_point: 2237, boiling_point: 3968,
     electron_affinity: 0.843, ionization_energy: 7.4589, radius_calculated: 1.34,
     hardness_brinell: 1100, modulus_bulk: 275.0, density_stp: 12.41, thermal_conductivity: 150.0,
     specific_heat: 0.243, abundance_universe: 0.0001, discovery_year: 1803},
    
    {atomic_number: 46, symbol: "Pd", name: "Palladium", atomic_weight: 106.42, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.20, melting_point: 1828.05, boiling_point: 3236,
     electron_affinity: 0.562, ionization_energy: 8.3369, radius_calculated: 1.37,
     hardness_brinell: 400, modulus_bulk: 121.0, density_stp: 12.02, thermal_conductivity: 71.8,
     specific_heat: 0.244, abundance_universe: 0.0001, discovery_year: 1803},
    
    {atomic_number: 47, symbol: "Ag", name: "Silver", atomic_weight: 107.87, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.93, melting_point: 1234.93, boiling_point: 2435,
     electron_affinity: 1.302, ionization_energy: 7.5762, radius_calculated: 1.44,
     hardness_brinell: 251, modulus_bulk: 100.0, density_stp: 10.49, thermal_conductivity: 429.0,
     specific_heat: 0.235, abundance_universe: 0.00005, discovery_year: 'I lashte'},
    
    {atomic_number: 48, symbol: "Cd", name: "Cadmium", atomic_weight: 112.41, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.69, melting_point: 594.22, boiling_point: 1040,
     electron_affinity: 0.0, ionization_energy: 8.9938, radius_calculated: 1.49,
     hardness_brinell: 203, modulus_bulk: 50.0, density_stp: 8.65, thermal_conductivity: 96.6,
     specific_heat: 0.232, abundance_universe: 0.00004, discovery_year: 1817},
    
    {atomic_number: 49, symbol: "In", name: "Indium", atomic_weight: 114.82, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.78, melting_point: 429.75, boiling_point: 2345,
     electron_affinity: 0.3, ionization_energy: 5.7864, radius_calculated: 1.66,
     hardness_brinell: 0.9, modulus_bulk: 10.0, density_stp: 7.31, thermal_conductivity: 81.8,
     specific_heat: 0.233, abundance_universe: 0.0003, discovery_year: 1863},
	 
	 {atomic_number: 50, symbol: "Sn", name: "Tin", atomic_weight: 118.71, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 1.96, melting_point: 505.08, boiling_point: 2875,
     electron_affinity: 1.112, ionization_energy: 7.3439, radius_calculated: 1.46,
     hardness_brinell: 50, modulus_bulk: 58.0, density_stp: 7.31, thermal_conductivity: 67.0,
     specific_heat: 0.228, abundance_universe: 0.00004, discovery_year: 'I lashte'},
	 
	 {atomic_number: 51, symbol: "Sb", name: "Antimony", atomic_weight: 121.76, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.05, melting_point: 903.78, boiling_point: 1860,
     electron_affinity: 1.047, ionization_energy: 8.6084, radius_calculated: 1.45,
     hardness_brinell: 294, modulus_bulk: 42.0, density_stp: 6.68, thermal_conductivity: 24.6,
     specific_heat: 0.207, abundance_universe: 0.00002, discovery_year: 'I lashte'},
    
     {atomic_number: 52, symbol: "Te", name: "Tellurium", atomic_weight: 127.60, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.1, melting_point: 722.66, boiling_point: 1261,
     electron_affinity: 1.971, ionization_energy: 9.0096, radius_calculated: 1.42,
     hardness_brinell: 180, modulus_bulk: 65.0, density_stp: 6.24, thermal_conductivity: 2.35,
     specific_heat: 0.202, abundance_universe: 0.000001, discovery_year: 1782},
	 
	 {atomic_number: 53, symbol: "I", name: "Iodine", atomic_weight: 126.90, state_at_room_temp: "Solid",
     energy_levels: 5, electronegativity: 2.66, melting_point: 386.85, boiling_point: 457.4,
	 electron_affinity: 3.059, ionization_energy: 10.4513, radius_calculated: 1.39,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 4.93, thermal_conductivity: 0.449,
	 specific_heat: 0.214, abundance_universe: 0.00003, discovery_year: 1811},
	 
	 {atomic_number: 54, symbol: "Xe", name: "Xenon", atomic_weight: 131.29, state_at_room_temp: "Gas",
	 energy_levels: 5, electronegativity: 'None', melting_point: 161.36, boiling_point: 165.03,
	 electron_affinity: 0.0, ionization_energy: 12.1298, radius_calculated: 1.40,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 0.0059, thermal_conductivity: 0.0057,
	 specific_heat: 0.158, abundance_universe: 'Trace', discovery_year: 1898},

	 {atomic_number: 55, symbol: "Cs", name: "Cesium", atomic_weight: 132.91, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 0.79, melting_point: 301.7, boiling_point: 944,
	 electron_affinity: 0.472, ionization_energy: 3.8939, radius_calculated: 2.44,
	 hardness_brinell: 0.14, modulus_bulk: 1.6, density_stp: 1.93, thermal_conductivity: 35.9,
	 specific_heat: 0.242, abundance_universe: 0.0003, discovery_year: 1860},

	 {atomic_number: 56, symbol: "Ba", name: "Barium", atomic_weight: 137.33, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 0.89, melting_point: 1000, boiling_point: 2170,
	 electron_affinity: 0.144, ionization_energy: 5.2117, radius_calculated: 2.15,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 3.62, thermal_conductivity: 18.4,
	 specific_heat: 0.204, abundance_universe: 0.04, discovery_year: 1808},

	 {atomic_number: 57, symbol: "La", name: "Lanthanum", atomic_weight: 138.91, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 1.1, melting_point: 1193, boiling_point: 3737,
	 electron_affinity: 0.47, ionization_energy: 5.5769, radius_calculated: 2.07,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 6.15, thermal_conductivity: 13.4,
	 specific_heat: 0.195, abundance_universe: 0.0003, discovery_year: 1839},

	 {atomic_number: 58, symbol: "Ce", name: "Cerium", atomic_weight: 140.12, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 1.12, melting_point: 1068, boiling_point: 3716,
	 electron_affinity: 0.5, ionization_energy: 5.5387, radius_calculated: 2.04,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 6.77, thermal_conductivity: 11.3,
	 specific_heat: 0.192, abundance_universe: 0.0006, discovery_year: 1803},

	 {atomic_number: 59, symbol: "Pr", name: "Praseodymium", atomic_weight: 140.91, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 1.13, melting_point: 1208, boiling_point: 3793,
	 electron_affinity: 0.5, ionization_energy: 5.473, radius_calculated: 2.03,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 6.77, thermal_conductivity: 12.7,
	 specific_heat: 0.193, abundance_universe: 0.00002, discovery_year: 1885},

	 {atomic_number: 60, symbol: "Nd", name: "Neodymium", atomic_weight: 144.24, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 1.14, melting_point: 1297, boiling_point: 3347,
	 electron_affinity: 0.5, ionization_energy: 5.525, radius_calculated: 2.01,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 7.01, thermal_conductivity: 16.5,
	 specific_heat: 0.19, abundance_universe: 0.00002, discovery_year: 1885},

	 {atomic_number: 61, symbol: "Pm", name: "Promethium", atomic_weight: 145, state_at_room_temp: "Solid",
	 energy_levels: 6, electronegativity: 1.13, melting_point: 1443, boiling_point: 3000,
	 electron_affinity: 0.5, ionization_energy: 5.582, radius_calculated: 2.00,
	 hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
	 specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1945},
	 
	 {atomic_number: 62, symbol: "Sm", name: "Samarium", atomic_weight: 150.36, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.17, melting_point: 1345, boiling_point: 2067,
     electron_affinity: 0.639, ionization_energy: 5.6437, radius_calculated: 1.98,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 7.52, thermal_conductivity: 13.3,
     specific_heat: 0.197, abundance_universe: 0.0006, discovery_year: 1853},
    
    {atomic_number: 63, symbol: "Eu", name: "Europium", atomic_weight: 151.96, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.2, melting_point: 1099, boiling_point: 1802,
     electron_affinity: 0.52, ionization_energy: 5.6704, radius_calculated: 2.0,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 5.24, thermal_conductivity: 13.9,
     specific_heat: 0.182, abundance_universe: 0.00005, discovery_year: 1901},
    
    {atomic_number: 64, symbol: "Gd", name: "Gadolinium", atomic_weight: 157.25, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.2, melting_point: 1585, boiling_point: 3546,
     electron_affinity: 0.61, ionization_energy: 6.1498, radius_calculated: 1.99,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 7.90, thermal_conductivity: 10.6,
     specific_heat: 0.236, abundance_universe: 0.00003, discovery_year: 1880},
    
    {atomic_number: 65, symbol: "Tb", name: "Terbium", atomic_weight: 158.93, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.2, melting_point: 1629, boiling_point: 3503,
     electron_affinity: 0.11, ionization_energy: 5.8638, radius_calculated: 1.98,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 8.23, thermal_conductivity: 11.1,
     specific_heat: 0.182, abundance_universe: 0.00003, discovery_year: 1843},
    
    {atomic_number: 66, symbol: "Dy", name: "Dysprosium", atomic_weight: 162.50, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.22, melting_point: 1680, boiling_point: 2840,
     electron_affinity: 0.53, ionization_energy: 5.9389, radius_calculated: 1.97,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 8.55, thermal_conductivity: 10.7,
     specific_heat: 0.17, abundance_universe: 0.00006, discovery_year: 1886},
    
    {atomic_number: 67, symbol: "Ho", name: "Holmium", atomic_weight: 164.93, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.23, melting_point: 1734, boiling_point: 2993,
     electron_affinity: 0.6, ionization_energy: 6.0215, radius_calculated: 1.96,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 8.80, thermal_conductivity: 16.2,
     specific_heat: 0.165, abundance_universe: 0.00003, discovery_year: 1878},
    
    {atomic_number: 68, symbol: "Er", name: "Erbium", atomic_weight: 167.26, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.24, melting_point: 1802, boiling_point: 3141,
     electron_affinity: 0.86, ionization_energy: 6.1077, radius_calculated: 1.95,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 9.07, thermal_conductivity: 14.5,
     specific_heat: 0.168, abundance_universe: 0.00003, discovery_year: 1842},
    
    {atomic_number: 69, symbol: "Tm", name: "Thulium", atomic_weight: 168.93, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.25, melting_point: 1818, boiling_point: 2223,
     electron_affinity: 0.2, ionization_energy: 6.1843, radius_calculated: 1.94,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 9.32, thermal_conductivity: 16.8,
     specific_heat: 0.16, abundance_universe: 0.00004, discovery_year: 1879},
	 
	{atomic_number: 70, symbol: "Yb", name: "Ytterbium", atomic_weight: 173.04, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.1, melting_point: 1097, boiling_point: 1469,
     electron_affinity: 1.0, ionization_energy: 6.2542, radius_calculated: 1.93,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 6.57, thermal_conductivity: 34.9,
     specific_heat: 0.155, abundance_universe: 0.00006, discovery_year: 1878},
    
    {atomic_number: 71, symbol: "Lu", name: "Lutetium", atomic_weight: 174.97, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.27, melting_point: 1925, boiling_point: 3675,
     electron_affinity: 0.5, ionization_energy: 5.4259, radius_calculated: 1.72,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 9.84, thermal_conductivity: 16.4,
     specific_heat: 0.154, abundance_universe: 0.00001, discovery_year: 1907},
    
    {atomic_number: 72, symbol: "Hf", name: "Hafnium", atomic_weight: 178.49, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.3, melting_point: 2506, boiling_point: 4876,
     electron_affinity: 0.61, ionization_energy: 6.8251, radius_calculated: 1.59,
     hardness_brinell: 1700, modulus_bulk: 78.0, density_stp: 13.31, thermal_conductivity: 23.0,
     specific_heat: 0.144, abundance_universe: 0.00003, discovery_year: 1923},
    
    {atomic_number: 73, symbol: "Ta", name: "Tantalum", atomic_weight: 180.95, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.5, melting_point: 3290, boiling_point: 5731,
     electron_affinity: 0.322, ionization_energy: 7.5496, radius_calculated: 1.44,
     hardness_brinell: 870, modulus_bulk: 200.0, density_stp: 16.69, thermal_conductivity: 57.5,
     specific_heat: 0.14, abundance_universe: 0.00002, discovery_year: 1802},
    
    {atomic_number: 74, symbol: "W", name: "Tungsten", atomic_weight: 183.84, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.36, melting_point: 3695, boiling_point: 5828,
     electron_affinity: 0.815, ionization_energy: 7.8640, radius_calculated: 1.36,
     hardness_brinell: 2570, modulus_bulk: 310.0, density_stp: 19.25, thermal_conductivity: 170.0,
     specific_heat: 0.132, abundance_universe: 0.00001, discovery_year: 1783},
    
    {atomic_number: 75, symbol: "Re", name: "Rhenium", atomic_weight: 186.21, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.9, melting_point: 3459, boiling_point: 5869,
     electron_affinity: 0.15, ionization_energy: 7.8335, radius_calculated: 1.33,
     hardness_brinell: 1320, modulus_bulk: 370.0, density_stp: 21.02, thermal_conductivity: 47.9,
     specific_heat: 0.137, abundance_universe: 0.0000006, discovery_year: 1925},
    
    {atomic_number: 76, symbol: "Os", name: "Osmium", atomic_weight: 190.23, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.2, melting_point: 3306, boiling_point: 5285,
     electron_affinity: 1.077, ionization_energy: 8.4382, radius_calculated: 1.37,
     hardness_brinell: 3920, modulus_bulk: 462.0, density_stp: 22.59, thermal_conductivity: 87.6,
     specific_heat: 0.13, abundance_universe: 0.000001, discovery_year: 1803},
    
    {atomic_number: 77, symbol: "Ir", name: "Iridium", atomic_weight: 192.22, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.2, melting_point: 2719, boiling_point: 4701,
     electron_affinity: 1.564, ionization_energy: 8.9670, radius_calculated: 1.35,
     hardness_brinell: 1670, modulus_bulk: 528.0, density_stp: 22.56, thermal_conductivity: 147.0,
     specific_heat: 0.131, abundance_universe: 0.0000002, discovery_year: 1803},
	 
	 {atomic_number: 78, symbol: "Pt", name: "Platinum", atomic_weight: 195.08, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.28, melting_point: 2041.4, boiling_point: 4098,
     electron_affinity: 2.128, ionization_energy: 8.9587, radius_calculated: 1.39,
     hardness_brinell: 3920, modulus_bulk: 168.0, density_stp: 21.45, thermal_conductivity: 71.6,
     specific_heat: 0.133, abundance_universe: 0.0000005, discovery_year: 'I lashte'},
    
    {atomic_number: 79, symbol: "Au", name: "Gold", atomic_weight: 196.97, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.54, melting_point: 1337.33, boiling_point: 3129,
     electron_affinity: 2.308, ionization_energy: 9.2255, radius_calculated: 1.44,
     hardness_brinell: 216, modulus_bulk: 220.0, density_stp: 19.32, thermal_conductivity: 315.0,
     specific_heat: 0.129, abundance_universe: 0.0000005, discovery_year: 'I lashte'},
    
    {atomic_number: 80, symbol: "Hg", name: "Mercury", atomic_weight: 200.59, state_at_room_temp: "Liquid",
     energy_levels: 6, electronegativity: 2.00, melting_point: 234.32, boiling_point: 629.88,
     electron_affinity: 0.0, ionization_energy: 10.4375, radius_calculated: 1.55,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 13.55, thermal_conductivity: 8.3,
     specific_heat: 0.14, abundance_universe: 0.00000003, discovery_year: 'I lashte'},
    
    {atomic_number: 81, symbol: "Tl", name: "Thallium", atomic_weight: 204.38, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.62, melting_point: 577, boiling_point: 1746,
     electron_affinity: 0.378, ionization_energy: 6.1082, radius_calculated: 1.96,
     hardness_brinell: 26, modulus_bulk: 43.0, density_stp: 11.85, thermal_conductivity: 46.1,
     specific_heat: 0.129, abundance_universe: 0.0000006, discovery_year: 1861},
    
    {atomic_number: 82, symbol: "Pb", name: "Lead", atomic_weight: 207.2, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 1.87, melting_point: 600.61, boiling_point: 2022,
     electron_affinity: 0.364, ionization_energy: 7.4167, radius_calculated: 2.02,
     hardness_brinell: 38, modulus_bulk: 46.0, density_stp: 11.34, thermal_conductivity: 35.3,
     specific_heat: 0.128, abundance_universe: 0.0000006, discovery_year: 'I lashte'},
    
    {atomic_number: 83, symbol: "Bi", name: "Bismuth", atomic_weight: 208.98, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.02, melting_point: 544.7, boiling_point: 1837,
     electron_affinity: 0.946, ionization_energy: 7.2856, radius_calculated: 2.07,
     hardness_brinell: 94, modulus_bulk: 32.0, density_stp: 9.78, thermal_conductivity: 7.87,
     specific_heat: 0.122, abundance_universe: 0.00000006, discovery_year: 'I lashte'},
    
    {atomic_number: 84, symbol: "Po", name: "Polonium", atomic_weight: 209, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.0, melting_point: 527, boiling_point: 1235,
     electron_affinity: 1.9, ionization_energy: 8.417, radius_calculated: 1.97,
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 9.20, thermal_conductivity: 50.0,
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1898},
	
	{atomic_number: 85, symbol: "At", name: "Astatine", atomic_weight: 210, state_at_room_temp: "Solid",
     energy_levels: 6, electronegativity: 2.2, melting_point: 575, boiling_point: 610,
     electron_affinity: 2.8, ionization_energy: 9.3, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1940},
    
    {atomic_number: 86, symbol: "Rn", name: "Radon", atomic_weight: 222, state_at_room_temp: "Gas",
     energy_levels: 6, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 10.7485, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 0.00973, thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1900},
    
    {atomic_number: 87, symbol: "Fr", name: "Francium", atomic_weight: 223, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 0.7, melting_point: 300, boiling_point: 'None',
     electron_affinity: 0.46, ionization_energy: 3.8939, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1939},
    
    {atomic_number: 88, symbol: "Ra", name: "Radium", atomic_weight: 226, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 0.9, melting_point: 1413, boiling_point: 1413,
     electron_affinity: 0.9, ionization_energy: 5.2784, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 5.5, thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1898},
    
    {atomic_number: 89, symbol: "Ac", name: "Actinium", atomic_weight: 227, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.1, melting_point: 1220, boiling_point: 3200,
     electron_affinity: 1.1, ionization_energy: 5.17, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 10.07, thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1899},
    
    {atomic_number: 90, symbol: "Th", name: "Thorium", atomic_weight: 232.04, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 2115, boiling_point: 5061,
     electron_affinity: 1.1, ionization_energy: 6.3067, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 11.72, thermal_conductivity: 54.0,
     specific_heat: 0.113, abundance_universe: 0.0006, discovery_year: 1828},
	 
	{atomic_number: 91, symbol: "Pa", name: "Protactinium", atomic_weight: 231.04, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.5, melting_point: 1841, boiling_point: 4300,
     electron_affinity: 1.4, ionization_energy: 5.89, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 15.37, thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1913},
    
    {atomic_number: 92, symbol: "U", name: "Uranium", atomic_weight: 238.03, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.38, melting_point: 1405.3, boiling_point: 4404,
     electron_affinity: 0.5, ionization_energy: 6.1941, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 18.95, thermal_conductivity: 27.6,
     specific_heat: 0.116, abundance_universe: 0.00003, discovery_year: 1789},
    
    {atomic_number: 93, symbol: "Np", name: "Neptunium", atomic_weight: 237, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.36, melting_point: 917, boiling_point: 4273,
     electron_affinity: 1.29, ionization_energy: 6.2657, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1940},
	 
	 {atomic_number: 94, symbol: "Pu", name: "Plutonium", atomic_weight: 244, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.28, melting_point: 913, boiling_point: 3503,
     electron_affinity: 0.0, ionization_energy: 6.0262, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 6.74,
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1940},
    
    {atomic_number: 95, symbol: "Am", name: "Americium", atomic_weight: 243, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1449, boiling_point: 2284,
     electron_affinity: 0.0, ionization_energy: 5.9738, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1944},
    
    {atomic_number: 96, symbol: "Cm", name: "Curium", atomic_weight: 247, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1613, boiling_point: 3383,
     electron_affinity: 0.0, ionization_energy: 5.9915, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1944},
    
    {atomic_number: 97, symbol: "Bk", name: "Berkelium", atomic_weight: 247, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1259, boiling_point: 2900,
     electron_affinity: 0.0, ionization_energy: 6.1979, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1949},
    
    {atomic_number: 98, symbol: "Cf", name: "Californium", atomic_weight: 251, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1173, boiling_point: 1743,
     electron_affinity: 0.0, ionization_energy: 6.2817, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1950},
    
    {atomic_number: 99, symbol: "Es", name: "Einsteinium", atomic_weight: 252, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1133, boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 6.42, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1952},
    
    {atomic_number: 100, symbol: "Fm", name: "Fermium", atomic_weight: 257, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 1800, boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 6.5, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1952},
    
    {atomic_number: 101, symbol: "Md", name: "Mendelevium", atomic_weight: 258, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 6.58, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1955},
    
    {atomic_number: 102, symbol: "No", name: "Nobelium", atomic_weight: 259, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 6.65, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1957},
	 
	     {atomic_number: 103, symbol: "Lr", name: "Lawrencium", atomic_weight: 266, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 1.3, melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 4.9, radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1961},
    
    {atomic_number: 104, symbol: "Rf", name: "Rutherfordium", atomic_weight: 267, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1969},
    
    {atomic_number: 105, symbol: "Db", name: "Dubnium", atomic_weight: 270, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1967},
    
    {atomic_number: 106, symbol: "Sg", name: "Seaborgium", atomic_weight: 271, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1974},
    
    {atomic_number: 107, symbol: "Bh", name: "Bohrium", atomic_weight: 270, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1976},
    
    {atomic_number: 108, symbol: "Hs", name: "Hassium", atomic_weight: 277, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1984},
    
    {atomic_number: 109, symbol: "Mt", name: "Meitnerium", atomic_weight: 276, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1982},
    
    {atomic_number: 110, symbol: "Ds", name: "Darmstadtium", atomic_weight: 281, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1994},
    
    {atomic_number: 111, symbol: "Rg", name: "Roentgenium", atomic_weight: 280, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1994},
    
    {atomic_number: 112, symbol: "Cn", name: "Copernicium", atomic_weight: 285, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 0.0, ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1996},
	 
	 {atomic_number: 113, symbol: "Nh", name: "Nihonium", atomic_weight: 284, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 2003},
    
    {atomic_number: 114, symbol: "Fl", name: "Flerovium", atomic_weight: 289, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 1998},
    
    {atomic_number: 115, symbol: "Mc", name: "Moscovium", atomic_weight: 288, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 2003},
    
    {atomic_number: 116, symbol: "Lv", name: "Livermorium", atomic_weight: 293, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 2000},
    
    {atomic_number: 117, symbol: "Ts", name: "Tennessine", atomic_weight: 294, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 2010},
    
    {atomic_number: 118, symbol: "Og", name: "Oganesson", atomic_weight: 294, state_at_room_temp: "Solid",
     energy_levels: 7, electronegativity: 'None', melting_point: 'None', boiling_point: 'None',
     electron_affinity: 'None', ionization_energy: 'None', radius_calculated: 'None',
     hardness_brinell: 'None', modulus_bulk: 'None', density_stp: 'None', thermal_conductivity: 'None',
     specific_heat: 'None', abundance_universe: 'Trace', discovery_year: 2002}
     ]
    };
  },
};
</script>

<style scoped>
.vertical {
  /* transform-origin: 0 50%; */
  transform: rotate(-90deg); 
  white-space: nowrap; 
  display: block;
  /* position: absolute; */
  bottom: 0;
  left: 50%;
}
.center-text {
    text-align: center;
    background-color: #DDD;
  }
  .center-text2 {
    text-align: center;
    background-color: #9EE5D4;
  }
.tables-container {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Two columns with equal width */
  gap: 16px; /* Adjust the gap as needed */
}
  .letter-table {
    margin: 10% auto; /* Center the table horizontally and add some top margin */
    width: 80%; /* Adjust the width as needed */
    border-collapse: collapse;
    border-radius: 10px; /* Rounded corners */
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add a subtle box shadow */
  }
  .letter-table2 {
    margin: 10% auto; /* Center the table horizontally and add some top margin */
    width: 80%; /* Adjust the width as needed */
    border-collapse: collapse;
    border-radius: 10px; /* Rounded corners */
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add a subtle box shadow */
  }

  .letter-cell {
    border: 1px solid #ddd; /* Light gray border */
    text-align: center;
    padding: 12px; /* Increase padding for better spacing */
    max-width: 150px; /* Set a fixed maximum width */
    overflow: hidden;
    white-space: nowrap; /* Prevent text wrapping */
  }

  .center-text {
    background-color: #f2f2f2; /* Light gray background for header cells */
  }

  .center-text2 {
    background-color: #f2f2f2; /* Light gray background for the vertical header cell */
    text-align: center;
  }

  .left-letter {
    display: block; /* Display each line of text as a block */
  }

  .vertical {
    writing-mode: vertical-lr; /* Rotate text vertically */
    transform: rotate(180deg); /* For IE */
  }
/* .letter-table2 {
  margin-left: 30%;
  margin-top: 10%;
  width: 90%;
  border-collapse: collapse;
  border-radius: 10px;
}

.letter-cell {
  border: 1px solid black;
  text-align: center;
  padding: 5px;
  max-width: 100%; overflow: hidden;
} */
.letter-cell2 {
  border: 1px solid black;
  text-align: center;
  padding: 5px;
  max-width: 100%; overflow: hidden;
}

.left-letter {
    display: block; /* Display each line of text as a block */
    font-size: 11px; /* Adjust font size */
  }
.left-letter3 {
  display: block;
  font-size: 12px;
  background-color: #DDD;
}
.right-letter {
    display: block; /* Display each line of text as a block */
    font-size: 14px; /* Adjust font size */
    margin-top: 5px; /* Add some margin between left and right text */
  }
</style>
