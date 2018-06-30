<template>
  <div class="row" style="height: 100%; margin-right: 10px;">
    <div class="row col-md-12">
      <b-tabs class="col-md-3" card id="myForm" style="height: 900px;">
        <!--Distributor Form-->
        <b-tab title="Distributor" active>
          <!--Distributor Form-->
          <div class="container-fluid text-left">
            <b-form class="form-condensed">
              <!-- &lt;!&ndash;Part Number&ndash;&gt;
               <b-form-group id="partNumber"
                             label="Part Number:"
                             label-size="sm"
                             class="form-condensed"
                             label-for="partNumber">
                 <b-form-input id="partNumber"
                               type="text"
                               placeholder="Part Number..."
                               size="sm"
                               class="mb-3">
                 </b-form-input>
               </b-form-group>-->
              <!--Dist Type-->
              <b-form-group id="distTypeGroup"
                            label="Distributor Type:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="type">
                <b-form-select v-model="type" :options="distributorTypes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Inlet Type-->
              <b-form-group id="inletTypeGroup"
                            label="Inlet Type:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="inletType">
                <b-form-select v-model="inletType" :options="inletTypes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Number of Circuits-->
              <b-form-group id="circuitNumGroup"
                            label="Number of Circuits:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="circuitNum">
                <b-form-input id="circuitNum"
                              type="number"
                              :max="60"
                              :min="2"
                              :step="1"
                              size="sm"
                              v-model="circuitNum">
                </b-form-input>
              </b-form-group>
              <!--Inlet Size-->
              <b-form-group id="inletSizeGroup"
                            label="Inlet Size:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="inletSize">
                <b-form-select v-model="inletSize" :options="inletSizes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Tubing OD-->
              <b-form-group id="tubingODGroup"
                            label="Tubing OD:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="tubingOD">
                <b-form-select v-model="tubingOD" :options="tubingODs" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Nozzle Orifice Size-->
              <b-form-group id="orrificeSizeGroup"
                            label="Nozzle Orifice Size:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="orrificeSize">
                <b-form-select v-model="orrificeSize" :options="orrificeSizes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Nozzle Type-->
              <b-form-group id="nozzleTypeGroup"
                            label="Nozzle Type:"
                            label-size="sm"
                            label-for="nozzleType"
                            class="form-condensed"
              >
                <b-form-select v-model="nozzleType" :options="nozzleTypes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Side Port-->
              <b-form-group id="sidePortGroup"
                            label="Side Port:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="sidePort">
                <b-form-select v-model="sidePortType" :options="sidePortTypes" size="sm" class="mb-3"/>
              </b-form-group>
              <!--Select Button-->
              <div style="text-align: right;">
                <b-button :variant="outline-primary">
                  Select Distributor
                </b-button>
              </div>
            </b-form>
          </div>
        </b-tab>
        <!--Performance Form-->
        <b-tab title="Performance">
          <div class="container-fluid text-left">
            <b-form class="form-control-sm form-condensed">
              <!--Part Number-->
              <b-form-group id="partNumberGroup"
                            label="Part Number:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="partNumber">
                <b-form-input id="partNumber"
                              type="text"
                              placeholder="Part Number..."
                              size="sm"
                              class="mb-3">
                </b-form-input>
              </b-form-group>
              <!--Refrigerants-->
              <b-form-group id="refrigerantGroup"
                            label="Refrigerant:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="refrigerant">
                <b-form-select v-model="refrigerant" :options="refrigerants" size="sm" class="mb-3 form-condensed"/>
              </b-form-group>
              <!--Capacity-->
              <b-form-group id="capacityGroup"
                            label="Capacity (tons):"
                            label-size="sm"
                            class="form-condensed"
                            label-for="capacity">
                <b-form-input id="capacity"
                              type="number"
                              :min="0"
                              :step="1"
                              size="sm"
                              v-model="capacity">
                </b-form-input>
              </b-form-group>
              <!--Suction Temperature-->
              <b-form-group id="suctionTempGroup"
                            label="Suction Temperature:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="suctionTemp">
                <b-form-select v-model="suctionTemp" :options="suctionTemps" class="mb-3" size="sm"/>
              </b-form-group>
              <!--Liquid Temperature-->
              <b-form-group id="liquidTempGroup"
                            label="Liquid Temperature:"
                            label-size="sm"
                            class="form-condensed"
                            label-for="liquidTemp">
                <b-form-select v-model="liquidTemp" :options="liquidTemps" class="mb-3" size="sm"/>
              </b-form-group>
              <!--Distributor Tube Length-->
              <b-form-group id="distTubeLengthGroup"
                            label="Distributor Tube Length (in):"
                            label-size="sm"
                            class="form-condensed"
                            label-for="tubeLength">
                <b-form-select v-model="tubeLength" :options="tubeLengths" class="mb-3" size="sm"/>
              </b-form-group>
              <div style="text-align: right;">
                <b-button :variant="outline-primary" class="btn btn-primary" style="text-align: left;">
                  Rate Distributor
                </b-button>
              </div>
            </b-form>
          </div>
        </b-tab>
      </b-tabs>
      <div class="row col-md-9" style="text-align: center;">
        <div class="row">
          <div class=col-md-12>
            <b-table striped hover :responsive="true" :outlined="true"
                     :sort-by.sync="sortBy"
                     :sort-desc.sync="sortDesc"
                     :items="distributors"
                     :fields="fields"
                     caption-top
                     head-variant="dark"
                     class="col-md-12"
                     style="height: 500px; text-align: center;">
              <template slot="table-caption">
                Brought to you by NewViz Programming LLC
              </template>
            </b-table>
          </div>
          <input
            id="fileInput"
            type="file"
            @change="upload">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Papa from 'papaparse'
  import Blob from 'blob'
  import FileSaver from 'file-saver'
  import {
    getRefrigerants,
    getInletSizes,
    getDistributorTypes,
    getInletTypes,
    getTubingOD,
    getNozzleTypes,
    getOrrificeSizes,
    getSidePortTypes,
    getSuctionTemps,
    getLiquidTemps,
    getTubeLengths
  } from '../scripts/handler.js'

  let inletSizes = getInletSizes();
  let inletTypes = getInletTypes();
  let refrigerants = getRefrigerants();
  let distributorTypes = getDistributorTypes();
  let tubingODs = getTubingOD();
  let nozzleTypes = getNozzleTypes();
  let orrificeSizes = getOrrificeSizes();
  let sidePortTypes = getSidePortTypes();
  let suctionTemps = getSuctionTemps();
  let liquidTemps = getLiquidTemps();
  let tubeLengths = getTubeLengths();

  export default {
    name: "k-f-selector",
    data() {
      return {
        doc: null,
        distributors: [{"bodyStyle": '', "sporlanStyle": '', "type": '', "minCircuit": '', "maxCircuit": '',
          "circuitSize": '', "nozzleSize": '', "hasSidePort":'', "OAL": '', "OD":'',"IDTol":'',"inletDiameter":'',
          "e":'', "f":''}],
        type: null,
        inletType: null,
        inletTypes: inletTypes,
        distributorTypes: distributorTypes,
        inletSize: null,
        inletSizes: inletSizes,
        tubingOD: null,
        tubingODs: tubingODs,
        nozzleType: null,
        nozzleTypes: nozzleTypes,
        orrificeSize: null,
        orrificeSizes: orrificeSizes,
        sidePortType: 'none',
        sidePortTypes: sidePortTypes,
        refrigerant: null,
        circuitNum: 2,
        /* Performance Info */
        refrigerants: refrigerants,
        capacity: 0,
        suctionTemp: 0,
        suctionTemps: suctionTemps,
        liquidTemp: null,
        liquidTemps: liquidTemps,
        tubeLength: null,
        tubeLengths: tubeLengths,
        sortBy: 'bodyStyle',
        sortDesc: false,
        fields: [
          {key: 'bodyStyle', sortable: true},
          {key: 'sporlanStyle', sortable: true},
          {key: 'type', sortable: true},
          {key: 'minCircuit', sortable: true},
          {key: 'maxCircuit', sortable: true},
          {key: 'circuitSize', sortable: true},
          {key: 'nozzleSize', sortable: true},
          {key: 'hasSidePort', sortable: true},
          {key: 'OAL', sortable: true},
          {key: 'OD', sortable: true},
          {key: 'IDTol', sortable: true},
          {key: 'inletDiameter', sortable: true},
          {key: '" E "', sortable: true},
          {key: 'F', sortable: true}
        ]
      }
    },
    methods: {
      upload(e) {
        const that = this;
        const fileToLoad = event.target.files[0];
        const reader = new FileReader();
        reader.onload = fileLoadedEvent => {
          Papa.parse(fileLoadedEvent.target.result, {
            header: true,
            complete(results) {
              console.log('complete', results);
              that.doc = JSON.stringify(results.data, null, 2)
              that.distributors = results.data;
            },
            error(errors) {
              console.log('error', errors)
            }
          })
        };
        reader.readAsText(fileToLoad)
      },
      save() {
        const blob = new Blob([this.parseJSONtoCSV()], {type: 'text/csv'})
        FileSaver.saveAs(blob, 'test.csv')
      },
      parseJSONtoCSV() {
        return Papa.unparse(this.doc)
      }
    }
  }
</script>

<style scoped>

</style>
