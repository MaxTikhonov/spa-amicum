<template>
 <div class="wrapper">
  <div>
   <span class="span">{{ user.surname }}</span>
   <span class="span">{{ user.name }}</span>
   <span>{{ user.patronymic }}</span>
  </div>
  <div>
   <span>{{ user.dateOfBirth }}</span>
  </div>
  <div style="font-size: 1rem;">
   <span>Таб №: </span>
   <span>{{ user.table }}</span>
  </div>
  <div style="font-size: 1rem;">
   <span>{{ user.occupation }}</span>
  </div>
 </div>
</template>

<script>

export default {
 data() {
  return {
   user: {
    name: 'Максим',
    surname: 'Тихонов',
    patronymic: 'Евгеньевич',
    dateOfBirth: '18.12.1989',
    table: '0342347199',
    occupation: 'Проходчик IV разряда'
   }
  }
 }
}
</script>

<style scoped>
.wrapper {
 width: calc(100% - 1rem);
 padding: .5rem;
 display: flex;
 flex-direction: column;
 background: #596c94 !important;
 z-index: 1;
 border-radius: .2rem;
 font-size: 1.7rem;
 color: #fff;
 font-family: Roboto;
}

.span {
 margin-right: .7rem;
}
</style>