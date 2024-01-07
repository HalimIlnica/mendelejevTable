<template>
  <div class="main-container">
    <div class="text-center d-flex pb-4">
      <v-btn class="ma-2" style="background-color: #3498db" @click="toggleAll">
        Shfaqi te gjitha
      </v-btn>
      <v-btn class="ma-2" style="background-color: #2ecc71" @click="oksidet">
        Oksidet
      </v-btn>
      <v-btn class="ma-2" style="background-color: #e74c3c" @click="acidet">
        Acidet
      </v-btn>
      <v-btn class="ma-2" style="background-color: #f39c12" @click="bazat">
        Bazat
      </v-btn>
      <v-btn class="ma-2" style="background-color: #9b59b6" @click="kriperat">
        Kriperat
      </v-btn>
      <v-btn class="ma-2" style="background-color: #ecf0f1" @click="none">
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
                <td style="text-align: center;" colspan="5"><b>Oksidet</b></td>
              </tr>
              <tr>
                 <!-- background-color: #DCDCDC -->
                <td>Nr.</td>
                <td style="text-align: center;" colspan="2">Okside acide</td>
                <td style="text-align: center;" colspan="2">Okside bazike</td>
              </tr>
              <tr>
                <td>1</td>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>2</td>
                <td>SO2</td>
                <td>Dioksid squfuri</td>
                <td>Na2O</td>
                <td>Oksid natriumi</td>
              </tr>
              <tr>
                <td>2</td>
                <td>SO3</td>
                <td>Trioksid squfuri</td>
                <td>MgO</td>
                <td>Oksid magenzi</td>
              </tr>
              <tr>
                <td>3</td>
                <td>CO2</td>
                <td>Dioksid karboni</td>
                <td>CuO</td>
                <td>Oksid bakri (II)</td>
              </tr>
              <tr>
                <td>4</td>
                <td>CO</td>
                <td>Monoksid karboni</td>
                <td>Cu2O3</td>
                <td>Oksid bakri (III)</td>
              </tr>
              <tr>
                <td>5</td>
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
                <td style="text-align: center;" colspan="5"><b>Acidet</b></td>
              </tr>
              <tr>
                <td>Nr.</td>
                <td style="text-align: center;" colspan="2">Hidroacide</td>
                <td style="text-align: center;" colspan="2">Oksiacide</td>
              </tr>
              <tr>
                <td>1</td>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>2</td>
                <td>HCl</td>
                <td>Acid klorhidrik</td>
                <td>HNO2</td>
                <td>Acid nitror</td>
              </tr>
              <tr>
                <td>3</td>
                <td>H2S</td>
                <td>Acid sulfhidrik</td>
                <td>HNO3</td>
                <td>Acid nitric</td>
              </tr>
              <tr>
                <td>4</td>
                <td>HF</td>
                <td>Acid fluorhidrik</td>
                <td>H2SO3</td>
                <td>Acid sulfuror</td>
              </tr>
              <tr>
                <td>4</td>
                <td>HI</td>
                <td>Acid jodhiidrik</td>
                <td>H2SO4</td>
                <td>Acid sulfuric</td>
              </tr>
              <tr>
                <td>5</td>
                <td>HBr</td>
                <td>Acid bromhidrik</td>
                <td>H3PO4</td>
                <td>Acid fosforik</td>
              </tr>
              <tr>
                <td>6</td>
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
                <td style="text-align: center;" colspan="3"><b>Bazat</b></td>
              </tr>
              <tr>
                <td>Nr.</td>
                <td style="text-align: center;" colspan="1">Formula</td>
                <td style="text-align: center;" colspan="1">Emërtimi</td>
              </tr>
              <tr>
                <td>1</td>
                <td>KOH</td>
                <td>Hidroksid kaliumi</td>
              </tr>
              <tr>
                <td>2</td>
                <td>NaOH</td>
                <td>Hidroksid natriumi</td>
              </tr>
              <tr>
                <td>3</td>
                <td>Mg(OH)2</td>
                <td>Hidroksid magnezi</td>
              </tr>
              <tr>
                <td>4</td>
                <td>Cu(OH)2</td>
                <td>Hidroksid bakri (II)</td>
              </tr>
              <tr>
                <td>5</td>
                <td>Cu(OH)3</td>
                <td>Hidroksid bakri (III)</td>
              </tr>
              <tr>
                <td>6</td>
                <td>Fe(OH)2</td>
                <td>Hidroksid hekuri (II)</td>
              </tr>
              <tr>
                <td>7</td>
                <td>Fe(OH)3</td>
                <td>Hidroksid hekuri (III)</td>
              </tr>
              <tr>
                <td>8</td>
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
                <td style="text-align: center;" colspan="5"><b>Kripërat</b></td>
              </tr>
              <tr>
                <td>Nr.</td>
                <td style="text-align: center;" colspan="2">Formohet me mbetje hidroacide</td>
                <td style="text-align: center;" colspan="2">Formohet me mbetje oksiacide</td>
              </tr>
              <tr>
                <td>1</td>
                <td>Formula</td>
                <td>Emërtimi</td>
                <td>Formula</td>
                <td>Emërtimi</td>
              </tr>
              <tr>
                <td>2</td>
                <td>NaCl</td>
                <td>Klorur natriumi</td>
                <td>NaNO2</td>
                <td>Nitrit natriumi</td>
              </tr>
              <tr>
                <td>3</td>
                <td>K2S</td>
                <td>Sulfur kaliumi</td>
                <td>Mg(NO3)2</td>
                <td>Nitrat magnezi</td>
              </tr>
              <tr>
                <td>4</td>
                <td>MgF2</td>
                <td>Florur magnezi</td>
                <td>CuSO3</td>
                <td>Sulfit bakri</td>
              </tr>
              <tr>
                <td>5</td>
                <td>CuI2</td>
                <td>Jodur bakri</td>
                <td>FeSO4</td>
                <td>Sulfat hekuri</td>
              </tr>
              <tr>
                <td>6</td>
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

<!-- Collapse table 2 -->
    <div class="main-container">
    <div class="text-center d-flex pb-4">
      <v-btn class="ma-2" style="background-color: #4CAF50" @click="toggleAll2">
        Shfaqi te gjitha
      </v-btn>
      <v-btn class="ma-2" style="background-color: #FFC107" @click="alkanet">
        Alkanet
      </v-btn>
      <v-btn class="ma-2" style="background-color: #FF5722" @click="alkenet">
        Alkenet
      </v-btn>
      <v-btn class="ma-2" style="background-color: #673AB7" @click="alkinet">
        Alkinet
      </v-btn>
      <v-btn class="ma-2" style="background-color: #ecf0f1" @click="none">
        asnje
      </v-btn>
    </div>

    <v-expansion-panels v-model="panel" multiple>
      <v-expansion-panel title="Alkanet" value="Alkanet">
        <v-simple-table class="custom-table" v-if="panel.includes('Alkanet')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Alkanet</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">Nr.</td>
                <td style="text-align: left;" colspan="2">Emërtimi</td>
                <td style="text-align: left;" colspan="2">Formula empirike</td>
                <td style="text-align: left;" colspan="2">Formula gjysmë strukturore</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">1</td>
                <td style="text-align: left;" colspan="2">Metan</td>
                <td style="text-align: left;" colspan="2">CH4</td>
                <td style="text-align: left;" colspan="2">CH4</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">2</td>
                <td style="text-align: left;" colspan="2">Etan</td>
                <td style="text-align: left;" colspan="2">C2H6</td>
                <td style="text-align: left;" colspan="2">CH3 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">3</td>
                <td style="text-align: left;" colspan="2">Propan</td>
                <td style="text-align: left;" colspan="2">C3H8</td>
                <td style="text-align: left;" colspan="2">CH3 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">4</td>
                <td style="text-align: left;" colspan="2">Butan</td>
                <td style="text-align: left;" colspan="2">C4H10</td>
                <td style="text-align: left;" colspan="2">CH3 – CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">5</td>
                <td style="text-align: left;" colspan="2">Pentan</td>
                <td style="text-align: left;" colspan="2">C5H12</td>
                <td style="text-align: left;" colspan="2">CH3 – CH2 – CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">6</td>
                <td style="text-align: left;" colspan="2">Hekzan</td>
                <td style="text-align: left;" colspan="2">C6H14</td>
                <td style="text-align: left;" colspan="2">CH3 – CH2 – CH2 – CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">7</td>
                <td style="text-align: left;" colspan="2">Heptan</td>
                <td style="text-align: left;" colspan="2">C7H16</td>
                <td style="text-align: left;" colspan="2">CH3 – CH2 – CH2 – CH2 – CH2 – CH2 - CH3</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Alkenet" value="Alkenet">
        <v-simple-table class="custom-table" v-if="panel.includes('Alkenet')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Alkenet</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">Nr.</td>
                <td style="text-align: left;" colspan="2">Emërtimi</td>
                <td style="text-align: left;" colspan="2">Formula empirike</td>
                <td style="text-align: left;" colspan="2">Formula gjysmë strukturore</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">1</td>
                <td style="text-align: left;" colspan="2">Eten</td>
                <td style="text-align: left;" colspan="2">C2H4</td>
                <td style="text-align: left;" colspan="2">CH2 = CH2</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">2</td>
                <td style="text-align: left;" colspan="2">Propen</td>
                <td style="text-align: left;" colspan="2">C3H6</td>
                <td style="text-align: left;" colspan="2">CH2 = CH- CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">3</td>
                <td style="text-align: left;" colspan="2">Buten - 1</td>
                <td style="text-align: left;" colspan="2">C4H8</td>
                <td style="text-align: left;" colspan="2">CH2 = CH– CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">4</td>
                <td style="text-align: left;" colspan="2">Penten - 1</td>
                <td style="text-align: left;" colspan="2">C5H10</td>
                <td style="text-align: left;" colspan="2">CH2 = CH– CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">5</td>
                <td style="text-align: left;" colspan="2">Hekzen - 1</td>
                <td style="text-align: left;" colspan="2">C6H12</td>
                <td style="text-align: left;" colspan="2">CH2 = CH– CH2 – CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">6</td>
                <td style="text-align: left;" colspan="2">Hepten - 1</td>
                <td style="text-align: left;" colspan="2">C7H14</td>
                <td style="text-align: left;" colspan="2">CH2 = CH– CH2 – CH2 – CH2 – CH2 - CH3</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Alkinet" value="Alkinet">
        <v-simple-table class="custom-table" v-if="panel.includes('Alkinet')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Alkinet</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">Nr.</td>
                <td style="text-align: left;" colspan="2">Emërtimi</td>
                <td style="text-align: left;" colspan="2">Formula empirike</td>
                <td style="text-align: left;" colspan="2">Formula gjysmë strukturore</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">1</td>
                <td style="text-align: left;" colspan="2">Etin</td>
                <td style="text-align: left;" colspan="2">C2H2</td>
                <td style="text-align: left;" colspan="2">CH ≡ CH </td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">2</td>
                <td style="text-align: left;" colspan="2">Propin</td>
                <td style="text-align: left;" colspan="2">C3H4</td>
                <td style="text-align: left;" colspan="2">CH ≡ C - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">3</td>
                <td style="text-align: left;" colspan="2">Butin - 1</td>
                <td style="text-align: left;" colspan="2">C4H6</td>
                <td style="text-align: left;" colspan="2">CH ≡ C– CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">4</td>
                <td style="text-align: left;" colspan="2">Pentin - 1</td>
                <td style="text-align: left;" colspan="2">C5H8</td>
                <td style="text-align: left;" colspan="2">CH ≡ C– CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">5</td>
                <td style="text-align: left;" colspan="2">Hekzin - 1</td>
                <td style="text-align: left;" colspan="2">C6H10</td>
                <td style="text-align: left;" colspan="2">CH ≡ C– CH2 – CH2 – CH2 - CH3</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="1">6</td>
                <td style="text-align: left;" colspan="2">Heptin - 1</td>
                <td style="text-align: left;" colspan="2">C7H12</td>
                <td style="text-align: left;" colspan="2">CH2 ≡ C – CH2 – CH2 – CH2 – CH2 - CH3</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

    </v-expansion-panels>
  </div>

  <!-- Collapse table 3 -->
  <div class="main-container">
    <!-- <h2 style="text-align:center;">Reaksionet kimike</h2> -->
    <h2 style="text-align:center; color: #2c3e50; font-size: 24px; margin-bottom: 20px;">
      Reaksionet Kimike
    </h2>
    <div class="text-center d-flex pb-4">
      <v-btn class="ma-2" style="background-color: #3498db" @click="toggleAll3">
        Shfaqi te gjitha
      </v-btn>
      <v-btn class="ma-2" style="background-color: #e74c3c" @click="oksidimDheDjegie">
        R. e OKSIDMIT DHE DJEGIES
      </v-btn>
      <v-btn class="ma-2" style="background-color: #2ecc71" @click="reduktimi">
        R. e REDUKTIMIT
      </v-btn>
      <v-btn class="ma-2" style="background-color: #9b59b6" @click="redoks">
        R. REDOKS
      </v-btn>
      <v-btn class="ma-2" style="background-color: #f39c12" @click="shperberje">
        R. e SHPËRBËRJES
      </v-btn>
      <v-btn class="ma-2" style="background-color: #1abc9c" @click="precipitimi">
        R. e PRECIPITIMIT
      </v-btn>
      <v-btn class="ma-2" style="background-color: #d35400" @click="asnjanesimi">
        R. e ASNJANËSIMIT
      </v-btn>
      <v-btn class="ma-2" style="background-color: #3498db" @click="zevendesimi">
        R. e ZËVENDËSIMIT
      </v-btn>
      <v-btn class="ma-2" style="background-color: #ecf0f1" @click="none">
        asnje
      </v-btn>
    </div>

    <v-expansion-panels v-model="panel" multiple>
      <v-expansion-panel title="Reaksionet e OKSIDMIT DHE DJEGIES" value="OksidimDheDjegie">
        <v-simple-table class="custom-table" v-if="panel.includes('OksidimDheDjegie')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e OKSIDMIT DHE DJEGIES</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet e OKSIDMIT DHE DJEGIES</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE OKSIDIMI</i></b> (substanca vepron me oksigjenin)
                    <ul style="list-style-type: none;">
                        <li>• Substancë + oksigjen </li>
                        <li>• Ndryshkja e hekurit: hekur + oksigjen → ndryshku</li>
                        <li>• Oksidimi i gjalpit për skuqje</li> 
                        <b>REAKSIONE DJEGIE</b> (djegia e substancave në prani të oksigjenit)
                        <li>• Substancë + oksigjen → digjet</li> 
                        <li>• Metal + oksigjen →oksid metali</li> 
                        <li>• Jometal +oksigjen → okside të jometaleve</li> 
                        <li>• Qymyr + oksigjen → dioksid karboni + ujë</li>
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet e REDUKTIMIT" value="Reduktimi">
        <v-simple-table class="custom-table" v-if="panel.includes('Reduktimi')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e REDUKTIMIT</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet e REDUKTIMIT</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE REDUKTIMI</i></b> (ndodh kur një substancë e humbet oksigjenin)
                    <ul style="list-style-type: none;">
                        <li>• Nxjerrja e metaleve nga xeherorët </li>
                        <li>• Hematit + karbon → hekur + dioksid karboni </li>
                        <li>• Oksid hekuri +karbon → hekuri + karbon </li> 
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet REDOKS" value="Redoks">
        <v-simple-table class="custom-table" v-if="panel.includes('Redoks')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet REDOKS</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet REDOKS</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE KU NDODH OKSIDIMI DHE REDUKTIMI</i></b>
                    <ul style="list-style-type: none;">
                        <li>• Zink  + acid klorhidrik→klorur zinku + hidrogjen</li>
                        <li>• Oksid hekuri + acid sulfurik→sulfat hekuri + ujë</li>
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet e SHPËRBËRJES" value="Shperberje">
        <v-simple-table class="custom-table" v-if="panel.includes('Shperberje')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e SHPËRBËRJES</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet e SHPËRBËRJES</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>SHPËRBËRJE TERMIKE</i></b> (ndodh kur një substancë ndahet në substanca më të thjeshta) 
                    <ul style="list-style-type: none;">
                        <li>• Oksid argjendi + nxehtësi → argjend + oksigjen </li>
                        <li>• Karbonat kaliumi + nxehtësi → oksid kalciumi + dioksid karboni</li>
                    </ul>
                    <b><i>SHPËRBËRJE ELEKTRIKE</i></b>
                    <ul style="list-style-type: none;">
                        <li>• Klorur natriumi + energji elektrike → natrium + klor </li>
                    </ul>
                    <b><i>SHPËRBËRJE ME ANË TË DRITËS</i></b>
                    <ul style="list-style-type: none;">
                        <li>•	Bromur argjendi + energji e dritës → argjend + brom (përdoret në fotografi)</li>
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet e PRECIPITIMIT" value="Precipitimi">
        <v-simple-table class="custom-table" v-if="panel.includes('Precipitimi')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e PRECIPITIMIT</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet e PRECIPITIMIT</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE PRECIPITIMI</i></b> (ndodh kur gjatë bashkëveprimit të dy substancave si produkt formohet një precipitat)
                    <ul style="list-style-type: none;">
                        <li>• Tretësirë + tretësirë → ngurtë + tretësirë</li>
                        <li>• Nitrat plumbi + jodur kaliumi → jodur plumbi +nitrat kaliumi</li>
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet e ASNJANËSIMIT" value="Asnjanesimi">
        <v-simple-table class="custom-table" v-if="panel.includes('Asnjanesimi')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e ASNJANËSIMIT</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">REAKSIONE ASNJANËSIMI</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE ASNJANËSIMI</i></b> (ndodh kur vepron një acid me një bazë)
                    <ul style="list-style-type: none;">
                        <li>• Acid + Bazë → kripë + ujë</li>
                        <li>• Acid klorhidrik + hidroksid natriumi →klorur natriumi +ujë</li>
                        <li>• Acid klorhidrik+ karbonat kalciumi →klorur kalciumi + ujë </li>
                    </ul>
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-expansion-panel>

      <v-expansion-panel title="Reaksionet e ZËVENDËSIMIT" value="Zevendesimi">
        <v-simple-table class="custom-table" v-if="panel.includes('Zevendesimi')">
          <template v-slot:default>
            <tbody class="orkidetDesign">
              <tr>
                <td style="text-align: center;" colspan="8"><b>Reaksionet e ZËVENDËSIMIT</b></td>
              </tr>
              <tr>
                <td style="text-align: left;" rowspan="3">Reaksionet e ZËVENDËSIMIT</td>
              </tr>
              <tr>
                <td style="text-align: left;" colspan="8">
                    <b><i>REAKSIONE ZËVENDËSIMI</i></b> (ndodh kur një element më aktiv i zë vendin në një përbërje një elementi më pak aktiv)
                    <ul style="list-style-type: none;">
                        <li>• Oksid kromi + alumin → krom + oksid alumini Përfitimin e metaleve në industri</li>
                    </ul>
                </td>
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
    margin-left: 10%;
    margin-right: 10%;
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
    toggleAll2() {
      if (this.panel.length === 4) {
        this.none2();
      } else {
        this.all2();
      }
    },
    toggleAll3() {
      if (this.panel.length === 4) {
        this.none3();
      } else {
        this.all3();
      }
    },
    all() {
      this.panel = ['Oksidet', 'Acidet', 'Bazat', 'Kriperat'];
    },
    oksidet() {
      this.panel = ['Oksidet'];
    },
    acidet() {
      this.panel = ['Acidet'];
    },
    bazat() {
      this.panel = ['Bazat'];
    },
    kriperat() {
      this.panel = ['Kriperat'];
    },
    none() {
      this.panel = [];
    },
    all2() {
      this.panel = ['Alkanet', 'Alkenet', 'Alkinet'];
    },
    alkanet() {
      this.panel = ['Alkanet'];
    },
    alkenet() {
      this.panel = ['Alkenet'];
    },
    alkinet() {
      this.panel = ['Alkinet'];
    },
    all3() {
      this.panel = ['OksidimDheDjegie', 'Reduktimi', 'Redoks', 'Shperberje', 'Precipitimi', 'Asnjanesimi', 'Zevendesimi'];
    },
    oksidimDheDjegie() {
      this.panel = ['OksidimDheDjegie'];
    },
    reduktimi() {
      this.panel = ['Reduktimi'];
    },
    redoks() {
      this.panel = ['Redoks'];
    },
    shperberje() {
      this.panel = ['Shperberje'];
    },
    precipitimi() {
      this.panel = ['Precipitimi'];
    },
    asnjanesimi() {
      this.panel = ['Asnjanesimi'];
    },
    zevendesimi() {
      this.panel = ['Zevendesimi'];
    },
    none2() {
      this.panel = [];
    },
    none3() {
      this.panel = [];
    },
  },
};
</script>
