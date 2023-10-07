<template>
  <div class="w-full h-screen bg-modal flex items-center justify-center modal-background fixed top-0 left-0 z-40">
    <div class="w-[95%] sm:w-[296px] rounded-2xl bg-white absolute p-16 sm:px-3 sm:py-3 overflow-auto max-h-[750px] justify-between">
      <img
        src="../assets/modal-close.svg"
        alt=""
        class="absolute top-4 right-4 cursor-pointer"
        @click="$emit('closeModal')"
      />
      <div class="grid grid-cols-12 gap-2 items-end mb-3">
        <div class="col-span-4 ...">
          <div class="text-xl">PANEL DE ACTIVIDADES DIARIAS</div>
          <div class="text-sm text-gray-400">Importante! : Completete los retrasados y coloque el mati`hva del retraso,</div>
        </div>
        <div class="col-span-6 ... flex">
          <span class="mx-20"><i class="fa fa-warning text-red-600"></i> 5 Actividades Retrasadas</span>
          <span><i class="fa fa-calendar text-blue-500"></i> 5 Actividades del dia Actual</span>
        </div>
        <div class="col-span-2 ... grid justify-items-center">
          <button class="bg-gray-600 text-white w-[190px] rounded">Samana 24</button>
          <span>{{ '< Nov 05/23 - Nov 11/23 >' }}</span>
        </div>
      </div>
      <div class="border-double br-gray-600 border-b-4 border-t-4 h-[600px] text-base text">
        <div class="mt-5 bg-gray-100 grid gap-1 grid-flow-col overflow-x-auto overflow-y-hidden h-[570px]">
          <div v-for="card in rawDataInicial" :key="card.id" class="grid grid-cols-1 w-[278px] pr-4 mt-3">
            <div class="border br-gray-600 rounded grid items-center justify-center mt-3 mb-2 h-[30px]"><span class="w-full">{{ 'Jueves 07/10/23' }}</span></div>
            <div>
              <div class="border br-gray-600 rounded text-xs mb-1 py-1 px-3" v-for="item in 3" :key="item.index">
                <div class="text-sm text-gray-800">{{ 'Conclllar reunion con junta de propletarioe y notaria' }}</div>
                <div class="text-gray-400">{{ card.estado }}</div>
                <div class="text-gray-400">{{ card.responsable }}</div>
                <div class="text-gray-400">{{ card.desActividad }}</div>
                <div class="text-gray-400">{{ card.desTipoRestriccion }}</div>
                <div>
                  <span class="bg-gray-300 px-2 py-[2px] mr-2"><i class="fa fa-flag text-white"></i></span>
                  <span class="text-gray-400"> Pendienie <i class="fa fa-chevron-down pl-3"></i></span>
                </div>
              </div>
            </div>
            <button class="bg-gray-600 text-white w-full rounded my-3 h-[30px]">Var mas...</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "success-component",
  props: {

  },
  components: {

  },
  data: function () {
    return {
      rawDataInicial : [
          {id: 1, codProyecto: 10, codAnaResFrente : 1 , desAnaResFrente : 'Frente 001', codAnaResFase : 2, desAnaResFase : 'Fase 001' , dayFechaRequerida: '2023/01/01', dayFechaIdentificacion: '2023/01/01' ,codEstadoActividad:3, estado: 'Comp.Retraso', codresponsable : 1, responsable : 'Diego Warthon', desActividad : 'Encofrado', desTipoRestriccion: 'Arquitectura', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 2, codProyecto: 10, codAnaResFrente : 1 , desAnaResFrente : 'Frente 001', codAnaResFase : 2, desAnaResFase : 'Fase 001' , dayFechaRequerida: '2023/01/01', dayFechaIdentificacion: '2023/01/01' ,codEstadoActividad:3, estado: 'Comp.Retraso', codresponsable : 1, responsable : 'Diego Warthon', desActividad : 'Enchape', desTipoRestriccion: 'Arquitectura', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 3, codProyecto: 10, codAnaResFrente : 1 , desAnaResFrente : 'Frente 001', codAnaResFase : 2, desAnaResFase : 'Fase 001' , dayFechaRequerida: '2023/01/05', dayFechaIdentificacion: '2023/01/01' ,codEstadoActividad:2, estado: 'Retrasado', codresponsable : 2, responsable : 'Javier Melendez', desActividad : 'Enchape', desTipoRestriccion: 'Arquitectura', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 4, codProyecto: 10, codAnaResFrente : 1 , desAnaResFrente : 'Frente 001', codAnaResFase : 2, desAnaResFase : 'Fase 001' , dayFechaRequerida: '2023/01/05', dayFechaIdentificacion: '2023/01/01' , codEstadoActividad:1 ,estado: 'Pendiente', codresponsable : 3, responsable : 'Juan Perez', desActividad : 'Encofrado 2', desTipoRestriccion: 'Arquitectura', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 5, codProyecto: 10, codAnaResFrente : 1 , desAnaResFrente : 'Frente 001', codAnaResFase : 2, desAnaResFase : 'Fase 001' , dayFechaRequerida: '2023/01/08', dayFechaIdentificacion: '2023/01/01' ,codEstadoActividad:1,  estado: 'Pendiente', codresponsable : 3, responsable : 'Juan Perez', desActividad : 'Cimentacion', desTipoRestriccion: 'Arquitectura', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 6, codProyecto: 10, codAnaResFrente : 2 , desAnaResFrente : 'Frente Nuevo 002', codAnaResFase : 3, desAnaResFase : 'Fase 002' , dayFechaRequerida: '2023/02/09', dayFechaIdentificacion: '2023/02/01' ,codEstadoActividad:1, estado: 'Comp.Retraso', codresponsable : 1, responsable : 'Diego Warthon', desActividad : 'Cimentacion', desTipoRestriccion: 'Construccion', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 7, codProyecto: 10, codAnaResFrente : 2 , desAnaResFrente : 'Frente Nuevo 002', codAnaResFase : 3, desAnaResFase : 'Fase 002' , dayFechaRequerida: '2023/02/10', dayFechaIdentificacion: '2023/02/01' , codEstadoActividad:2,estado: 'Comp.Plazo', codresponsable : 3, responsable : 'Juan Perez', desActividad : 'Cimentacion', desTipoRestriccion: 'Construccion', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 8, codProyecto: 11, codAnaResFrente : 3 , desAnaResFrente : 'Frente Modificado', codAnaResFase : 4, desAnaResFase : 'Fase Modificado' , dayFechaRequerida: '2023/02/10', dayFechaIdentificacion: '2023/02/01' , codEstadoActividad:2, estado: 'Comp.Plazo', codresponsable : 2, responsable : 'Javier Melendez', desActividad : 'Cimentacion', desTipoRestriccion: 'Construccion', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 9, codProyecto: 11, codAnaResFrente : 3 , desAnaResFrente : 'Frente Modificado', codAnaResFase : 4, desAnaResFase : 'Fase Modificado' , dayFechaRequerida: '2023/02/11', dayFechaIdentificacion: '2023/02/01' , codEstadoActividad:3, estado: 'Retrasado', codresponsable : 1, responsable : 'Diego Warthon', desActividad : 'Techo', desTipoRestriccion: 'Construccion', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'},
          {id: 10, codProyecto: 11, codAnaResFrente : 3 , desAnaResFrente : 'Frente Modificado', codAnaResFase : 4, desAnaResFase : 'Fase Modificado' , dayFechaRequerida: '2023/02/11', dayFechaIdentificacion: '2023/02/01' , codEstadoActividad:3, estado: 'Pendiente', codresponsable : 2,responsable : 'Javier Melendez', desActividad : 'Techo', desTipoRestriccion: 'Construccion', dayFechaConciliada: '2020/10/12', dayFechaLevantamiento: '2020/10/12'}
      ],
    };
  },
};
</script>

<style scoped>
.modal-background {
  background: rgba(0, 12, 30, 0.7);
}
.modal-header {
  word-break: break-word;
}
</style>