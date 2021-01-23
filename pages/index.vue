<template>
  <v-row justify="center" align="center">
    <v-col>
      <v-card
        class="mx-auto"
        align="center"
        min-height="1300"
        >
        <v-sheet min-height="100"></v-sheet>
        <v-img
          position="center"
          max-width="1000"
          :src="data.image"
          >
        </v-img>
          <v-sheet min-height="100"></v-sheet>
          <v-sheet
            tile
            class="px-4 pt-4 pb-3"
            >
            <div
              class="ma-5 text-h3 font-weight-thin"
              v-text="data.nameEn"
              ></div>
            <div
              class="ma-5 text-h1 font-weight-thin"
              v-text="data.nameJa"
              ></div>
            <div
              class="ma-5 text-h4 font-weight-thin"
              >work</div>
          </v-sheet>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      data: {
        image: "https://i.gyazo.com/e784de0521be5a4cbfca2a5a315ac4bb.png",
        nameEn: "Takagi Ayano",
        nameJa: "鷹木 彩乃",
      }
    }
  }
}
</script>
