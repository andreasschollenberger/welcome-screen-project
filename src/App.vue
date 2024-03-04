<script setup>
import { ref } from 'vue'
import haeder from './components/screen/haeder.vue'
import main1 from './components/screen/main1.vue'
import footer1 from './components/screen/footer1.vue'


const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID;
const api_token = import.meta.env.VITE_GOOGLE_API_KEY;

// const title = "Titel";
// const description = "Description";
// const time = "13:00";
// const date = "29.02.2024";


// const events = [
//   0 : ['13:00', '29.02.2024', 'Das ist ein Titel', 'Das ist eine Beschreibung', 'default'],
//   1 : [0: '13:00', 1: '29.02.2024', 2: 'Das ist ein Titel', 3: 'Das ist eine Beschreibung', 4: 'default'],
//   2 : ['13:00', '29.02.2024', 'Das ist ein Titel', 'Das ist eine Beschreibung', 'default'],
// ]


  const events = ref('')

  // DEFINITION DER FUNKTION
  async function fetchData(){
    // frage google server nach meinem tabelleninhalt (gib id und token mit zur authentifizierung)
    // speichere die Antwort (Daten) in der Konstante response
    const response = await fetch(`https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`);
    
    // wandle die erhaltene Antwort (json) in ein Javascript Objekt um
    // speichere das Objekt in der Konstante data
    // damit wir diese Daten weiter verwenden können
    const data = await response.json()

    events.value = data.valueRanges[0].values;
    
    // console.log(data.valueRanges[0].values);
  }

  // AUFRUF DER FUNKTION
  fetchData();
    

  // innerhalb html (template tags):

  // 1. main component erweitern, dass PROPS weitergegeben werden können
  
  // mit statischen Daten ausprobieren
  // in der Dokumentation nachschauen


  // 2. v-for loop erstellen über das events objekt
  // in vue.js dokumentation nachschauen, wie das funktioniert
      
</script>

<template>
  <haeder />
  <main>
  <main1 v-for="(event, index) in events"
    :key="index"
    :title="event[2]"
    :description="event[3]"
    :time="event[0]"
    :date="event[1]"
  />
  </main>
  <footer1 />
</template>

