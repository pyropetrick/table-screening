<template>
  <div>
    <button @click="openListDiseases" class="btn-open">Список заболеваний</button>
    <ModalDialog ref="modalDialogRef">
      <table class="list-diseases">
        <tr>
          <th>
            Название заболеваний
          </th>
        </tr>
        <tr
          v-for="disease in listDiseases"
          :key="disease"
          class="list-diseases__row"
        >
          <td class="list-diseases__disease">{{ disease }}</td>
        </tr>
      </table>
    </ModalDialog>
  </div>
</template>

<script>
import ModalDialog from '@/components/common/ModalDialog';
export default {
  name: "ListDiseases",
  components: {
    ModalDialog,
  },
  data: () => ({
    listDiseases: [
      'АГ',
      'Пневмония',
      'Хронический бронхит',
      'Хронический тонзиллит',
      'БА',
      'Острый гастрит',
      'Хронический гастрит(нед. секреция)',
      'Хронический гастрит(сохр. секреция)',
      'ЯБ',
      'Ожирение',
      'Острый пиелонефрит',
      'Хронический пиелонефрит',
      'Острый гломерулонефрит',
      'Хронический гломерулонефрит',
      'Анемия',
      'Васкулиты',
      'Геморрой',
      'Варикоз',
      'Эндоартериит',
      'МКБ',
      'Хронический отит',
      'ИБС',
      'Хронический аллергический риносинусит'
    ]
  }),
  methods: {
    openListDiseases() {
      this.$refs.modalDialogRef.showModal();
    }
  },
}
</script>

<style lang="scss" scoped>
.list-diseases {
  color: black;
  border: 1px solid black;
  border-spacing: 0;
  border-collapse: collapse;
  font-weight: normal;
  font-size: 0.875rem;
  background-color: white;
  &__row {
    border: 1px solid black;
  }
  &__disease {
    padding: 5px 0 5px 5px;
  }
}
</style>