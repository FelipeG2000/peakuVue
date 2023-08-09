<template>
    <div v-for="empleo in empleos" :key="empleo.nombreEmpresa">
      <div class="card job-card mb-3 border">
        <div class="card-body p-3 p-md-3">
          <div class="row aling-items-center">
            <div class="justify-content-center align-items-center col-md-1 col-3">
              <img :src="empleo.logo" :alt="empleo.alt" width="110" class="rounded">
            </div>
            <div class="col-md col-9">
              <div class="row align-items-center">
                <div class="mb-2 col">
                  <a :href="empleo.url" class="text-dark stretched-link">
                    <h2>{{ empleo.nombreEmpresa }}</h2>
                    <div class="p-1 d-inline-flex align-items-center text-wrap">
                      <div
                        class="skill-tag text-truncate border border-dark text-dark text-capitalize"
                        v-for="habilidad in empleo.habilidades"
                        :key="habilidad.id"
                      >
                        {{ habilidad.nombre }}
                      </div>
                    </div>
                  </a>
                </div>
              </div>
              <div class="row pl-md-2 mt-1 flex-column flex-md-row" style="font-size: 0.9em;">
                <div class="text-truncate text-capitalize col">{{ empleo.localidad }}</div>
                <div class="text-truncate col">{{ empleo.rangoSalarial }}</div>
                <div class="d-none d-md-inline-block col">{{ empleo.vacantes }} Vacante</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>

<script lang="ts" setup>
import {Ref,ref} from 'vue';
interface Empleo {
  logo: string;
  nombreVacante: string;
  url: string;
  alt: string;
  nombreEmpresa: string;
  localidad: string;
  modalidad: string;
  rangoSalarial: string;
  vacantes: string;
  tiempoPublicacion: string;
  habilidades: Habilidad[];
}

interface Habilidad {
  id: number;
  nombre: string;
}
let empleos:Ref<Array<Empleo>> = ref([
    {
        logo: require('@/assets/partners.jpg'),
        nombreVacante:'SDR (Sales Development Representative)',
        url:'https://peaku.io/es/empleos/10860-sdr-%2528sales-development-representative%2529',
        alt:"logo Empresa",
        nombreEmpresa:'Double V Partners',
        localidad:'Bogota',
        modalidad:'Remoto',
        rangoSalarial:'$ 4M - 8M COP',
        vacantes:'1',
        tiempoPublicacion:'11 hours ago',
        habilidades:[{id:1, nombre:'Prospecting'},{id:2, nombre:'B2b Business Relationship'}, {id:3, nombre:'Negotiation Strategy'}]
    },{
        logo:require('@/assets/offimedicas-logo.jpg'),
        nombreVacante:'Químico farmacéutico / Tuluá',
        url:'https://peaku.io/es/empleos/10854-quimico-farmaceutico---tulua',
        alt:"logo Empresa",
        nombreEmpresa:'OFFIMEDICAS S.A',
        localidad:'Santiago de cali',
        modalidad:'Remoto',
        rangoSalarial:'$ 3M - 4M COP',
        vacantes:'1',
        tiempoPublicacion:'about 9 hours ago',
        habilidades:[{id:1, nombre:'Technical Knowledge'},{id:2, nombre:'Problem Analysis'}]
    },{
        logo: require('@/assets/data-tools-logo.jpg'),
        nombreVacante:'Especialista en Gestión Cloud',
        url:'https://peaku.io/es/empleos/10854-quimico-farmaceutico---tulua',
        alt:"logo Empresa",
        nombreEmpresa:'Data Tools',
        localidad:'Bogota',
        modalidad:'Remoto',
        rangoSalarial:'Confidencial',
        vacantes:'1',
        tiempoPublicacion:'12 hours ago',
        habilidades:[{id:1, nombre:'Cloud Computing'},{id:2, nombre:'Cloud'}, {id:3, nombre:'Blue'}]
    },{
        logo: require('@/assets/data-tools-logo.jpg'),
        nombreVacante:'Especialista en Gestión del cambio',
        url:'https://peaku.io/es/empleos/10852-especialista-en-gestion-del-cambio',
        alt:"logo Empresa",
        nombreEmpresa:'Data Tools',
        localidad:'Bogota',
        modalidad:'Remoto',
        rangoSalarial:'Confidencial',
        vacantes:'1',
        tiempoPublicacion:'13 hours ago',
        habilidades:[{id:1, nombre:'Gestión Del Cambio'},{id:2, nombre:'Organization Communicaion'}]
    },{
        logo: require('@/assets/vichara-logo.jpg'),
        nombreVacante:'Desarrolador .Net Ssr',
        url:'https://peaku.io/es/empleos/10845-desarrollador-net-ssr-',
        alt:"logo Empresa",
        nombreEmpresa:'VICHARA TECHNOLOGIES',
        localidad:'Remoto en Colombia',
        modalidad:'Remoto',
        rangoSalarial:'$ 7M - 9M COP',
        vacantes:'1',
        tiempoPublicacion:'11 hours ago',
        habilidades:[{id:1, nombre:'Cloud Computing'},{id:2, nombre:'Cloud'}, {id:3, nombre:'Blue'}]
    }
])


</script>


<style scoped>

.card:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
}

.text-truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.skill-tag {
  border: 1px solid grey;
  border-radius: 10px;
  font-size: 12px;
  color: grey;
  text-transform: uppercase;
  -moz-text-align-last: left;
  text-align-last: left;
  display: inline-block;
  margin-right: 3px;
  margin-bottom: 3px;
  padding: 0 0.5rem;
  pointer-events: none;
  cursor: pointer;
  transition: all .2s ease;
}

a {
  color: #007bff;
  text-decoration: none;
  background-color: transparent;
}

.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  word-wrap: break-word;
  background-color: #fff;
  background-clip: border-box;
  border: 1px solid rgba(0, 0, 0, .125);
  border-radius: 0.25rem;
}

.row {
  display: flex;
  flex-wrap: wrap;
  margin-right: -15px;
  margin-left: -15px;
}
</style>