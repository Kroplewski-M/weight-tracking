<template>
  <div class="w-[99vw] h-[100vh] bg-[#111111]">
    <AppWelcome :class="showWelcome" @submit="submit"></AppWelcome>
    <AppAddRecord :class="showAddRecord"></AppAddRecord>
    <div class="w-[800px] mx-auto">
      <AppOverview :name="name"></AppOverview>
      <AppWeightTracker></AppWeightTracker>
  </div>
  </div>
</template>

<script>
  import AppWeightTracker from '@/components/AppWeightTracker.vue'
  import AppWelcome from '@/components/AppWelcome.vue'
  import AppOverview from '@/components/AppOverview.vue'
  import AppAddRecord from './components/AppAddRecord.vue'

  export default{
    name:"App",
    components: {
    AppWelcome,
    AppWeightTracker,
    AppOverview,
    AppAddRecord
},
  data(){
    return{
      name: "",
      weightRecords: {},
      showWelcome: 'hidden',
      showAddRecord: 'hidden',
    };
  },
  methods:{
    submit(name,weight,date){
      this.showWelcome = 'hidden';

      this.name = name;
      localStorage.setItem('name',name);


      this.weightRecords[date] = weight;
      console.log(this.weightRecords);
      localStorage.setItem('weightRecords', JSON.stringify(this.weightRecords));
    }
  },  
  created(){
    let name = localStorage.getItem('name');
    if(name == undefined){
      this.showWelcome = '';
    }
    else{
      this.showWelcome = 'hidden';
      this.name = name;
    }

    let records = localStorage.getItem('weightRecords');
    if(records == null){
      console.log("weightRecords null");
    }else{
      this.weightRecords = JSON.parse(records);
      console.log(this.weightRecords);
    }
  }
  }

</script>

