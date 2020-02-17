<template>
  <v-data-table 
      :headers="headers"
      :items="items">
    <template v-slot:item.value0="props">
      <span v-bind:class="getColor(props.item.value0)">{{ props.item.value0 }}</span>
    </template>
    <template v-slot:item.value1="props">
      <span v-bind:class="getColor(props.item.value1)">{{ props.item.value1 }}</span>
    </template>
    <template v-slot:item.value2="props">
      <span v-bind:class="getColor(props.item.value2)">{{ props.item.value2 }}</span>
    </template>
    <template v-slot:item.value3="props">
      <span v-bind:class="getColor(props.item.value3)">{{ props.item.value3 }}</span>
    </template>
    <template v-slot:item.value4="props">
      <span v-bind:class="getColor(props.item.value4)">{{ props.item.value4 }}</span>
    </template>
    <template v-slot:item.value5="props">
      <span v-bind:class="getColor(props.item.value5)">{{ props.item.value5 }}</span>
    </template>
    <template v-slot:item.value6="props">
      <span v-bind:class="getColor(props.item.value6)">{{ props.item.value6 }}</span>
    </template>
    <template v-slot:item.value7="props">
      <span v-bind:class="getColor(props.item.value7)">{{ props.item.value7 }}</span>
    </template>
    <template v-slot:item.value8="props">
      <span v-bind:class="getColor(props.item.value8)">{{ props.item.value8 }}</span>
    </template>
    <template v-slot:item.value9="props">
      <span v-bind:class="getColor(props.item.value9)">{{ props.item.value9 }}</span>
    </template>
    <template v-slot:item.value10="props">
      <span v-bind:class="getColor(props.item.value10)">{{ props.item.value10 }}</span>
    </template>
    <template v-slot:item.value11="props">
      <span v-bind:class="getColor(props.item.value11)">{{ props.item.value11 }}</span>
    </template>
    <template v-slot:item.value12="props">
      <span v-bind:class="getColor(props.item.value12)">{{ props.item.value12 }}</span>
    </template>
    <template v-slot:item.value13="props">
      <span v-bind:class="getColor(props.item.value13)">{{ props.item.value13 }}</span>
    </template>
    <template v-slot:item.value14="props">
      <span v-bind:class="getColor(props.item.value14)">{{ props.item.value14 }}</span>
    </template>
    <template v-slot:item.value15="props">
      <span v-bind:class="getColor(props.item.value15)">{{ props.item.value15 }}</span>
    </template>
    <template v-slot:item.value16="props">
      <span v-bind:class="getColor(props.item.value16)">{{ props.item.value16 }}</span>
    </template>
    <template v-slot:item.value17="props">
      <span v-bind:class="getColor(props.item.value17)">{{ props.item.value17 }}</span>
    </template>
    <template v-slot:item.value18="props">
      <span v-bind:class="getColor(props.item.value18)">{{ props.item.value18 }}</span>
    </template>
    <template v-slot:item.value19="props">
      <span v-bind:class="getColor(props.item.value19)">{{ props.item.value19 }}</span>
    </template>
    <template v-slot:item.value20="props">
      <span v-bind:class="getColor(props.item.value20)">{{ props.item.value20 }}</span>
    </template>
    <template v-slot:item.value21="props">
      <span v-bind:class="getColor(props.item.value21)">{{ props.item.value21 }}</span>
    </template>
    <template v-slot:item.value22="props">
      <span v-bind:class="getColor(props.item.value22)">{{ props.item.value22 }}</span>
    </template>
    <template v-slot:item.value23="props">
      <span v-bind:class="getColor(props.item.value23)">{{ props.item.value23 }}</span>
    </template>
    <template v-slot:item.value24="props">
      <span v-bind:class="getColor(props.item.value24)">{{ props.item.value24 }}</span>
    </template>
    <template v-slot:item.value25="props">
      <span v-bind:class="getColor(props.item.value25)">{{ props.item.value25 }}</span>
    </template>
    <template v-slot:item.value26="props">
      <span v-bind:class="getColor(props.item.value26)">{{ props.item.value26 }}</span>
    </template>
    <template v-slot:item.value27="props">
      <span v-bind:class="getColor(props.item.value27)">{{ props.item.value27 }}</span>
    </template>
    <template v-slot:item.value28="props">
      <span v-bind:class="getColor(props.item.value28)">{{ props.item.value28 }}</span>
    </template>
    <template v-slot:item.value29="props">
      <span v-bind:class="getColor(props.item.value29)">{{ props.item.value29 }}</span>
    </template>
    <template v-slot:item.value30="props">
      <span v-bind:class="getColor(props.item.value30)">{{ props.item.value30 }}</span>
    </template>

  </v-data-table>
</template>

<script>
export default {
    name: 'MyTable',
    props: ['headers', 'items'],
    methods: {
      getColor: function(value) {
        if (value >= 3000) return 'red--text'
        else if (value >= 2000) return 'purple--text'
        else if (value >= 1000) return 'blue--text'
        else if (value >= 500) return 'green--text'
        else return 'black--text'
      }
    },
}
</script>

<style>
.red {
  color: red;
}
.purple {
  color: purple;
}
.blue {
  color: blue;
}
.green {
  color: green;
}
.black {
  color: black;
}

</style>