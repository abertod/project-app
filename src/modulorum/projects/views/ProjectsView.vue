<template>
  <div class="overflow-x-auto w-full">
    <table class="table">
      <!-- head -->
      <thead>
        <tr>
          <th></th>
          <th>Proyectos</th>
          <th>Tareas</th>
          <th>Avance</th>
        </tr>
      </thead>
      <tbody>
        <!-- row 1 
        <tr>
          <th>1</th>
          <td>Cy Ganderton</td>
          <td>Quality Control Specialist</td>
          <td>Blue</td>
        </tr>-->
        <!-- row 2 -->
        <tr class="hover:bg-base-300">
          <th>2</th>
          <td>Hart Hagerty</td>
          <td>Desktop Support Technician</td>
          <td>Purple</td>
        </tr>
        <!-- row 3 
        <tr>
          <th>3</th>
          <td>Brice Swyre</td>
          <td>Tax Accountant</td>
          <td>Red</td>
        </tr>-->
      </tbody>
    </table>
  </div>
  <InputModal
    :aperta="modalAperta"
    @claudere="modalAperta = false"
    @valorem="cumNovusValorem"
    placeholder="Introduce el nombre del proyecto"
    titulus="Nuevo proyecto"
    subtitulus="Dale un nombre apropiado a tu proyecto"
  />

  <proprium-modal :aperta="propriumModalAperta">
    <template #header>
      <h1 class="text-3xl">Título del modal</h1>
    </template>

    <template #body>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Explicabo numquam facilis nostrum
        assumenda nam distinctio nisi sed vitae autem ducimus, maiores iusto neque aspernatur
        dolorem expedita delectus voluptate harum eos!
      </p>
    </template>

    <template #footer>
      <div class="flex justify-end">
        <button @click="propriumModalAperta = false" class="btn">Close</button>
        <button @click="propriumModalAperta = false" class="btn btn-primary ml-4">Aceptar</button>
      </div>
    </template>
  </proprium-modal>

  <fab-button @click="modalAperta = true">
    <AddCircle />
  </fab-button>

  <fab-button @click="propriumModalAperta = true" positione="bottom-left">
    <ModalIcon />
  </fab-button>

  <!--<FabButton positione="bottom-left" />-->
</template>

<script lang="ts" setup>
import FabButton from '@/modulorum/commune/components/FabButton.vue';
import InputModal from '@/modulorum/commune/components/InputModal.vue';
import PropriumModal from '@/modulorum/commune/components/PropriumModal.vue';
import AddCircle from '@/modulorum/commune/icons/AddCircle.vue';
import ModalIcon from '@/modulorum/commune/icons/ModalIcon.vue';
import { ref } from 'vue';
import { useProjectsStore } from '../store/projects.store';

const modalAperta = ref(false);

const propriumModalAperta = ref(false);

const projectsStore = useProjectsStore();

const cumNovusValorem = (projectNomen: string) => {
  console.log(projectNomen);
};
</script>
