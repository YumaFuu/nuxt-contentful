<template>
  <v-row justify="center" align="center">
    <v-col
      cols="12"
      >
      <v-card
        class="mx-auto"
        >
        <v-sheet min-height="100"></v-sheet>
          <v-col
            cols="12"
            align="center"
            >
            <v-img
              :src="data.profileImage"
              max-width="500"
              ></v-img>
          </v-col>
          <v-col
            cols="12"
            align="center"
            >
            <v-sheet min-height="100"></v-sheet>
            <div
              class="text-h3">
              {{ data.nameJa }}
            </div>
            <div
              class="text-h3 font-weight-thin">
              {{ data.nameEn }}
            </div>
          </v-col>
          <v-col
            align="center"
            >
            <v-btn
              text
              :href="link"
              target="_blank"
            >
              <fa-icon icon="download"/>
              <span>Twitter</span>
            </v-btn>
          </v-col>
        <v-sheet min-height="100"></v-sheet>
      <v-col
        cols="10"
        offset="1"
        align="left"
        >
        <p class="text-h5">
          {{ data.description }}
        </p>
      </v-col>
      <v-row>
        <v-col
          cols="10"
          offset="1"
          align="left"
          v-for="item in performances"
          :key="item.id"
          >
          <p
            class="text-h6"
            > {{ item.performed_at }} {{ item.title }}
          </p>
        </v-col>
      </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      data: {
        profileImage: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTW26qWWk1F8At1qLzI5HaO1xOepgfH-KW1NA&usqp=CAU",
        nameEn: "Takagi Ayano",
        nameJa: "鷹木 彩乃",
        description: "YouTuber・ワタナベマホト（マホト）さんの所属するUUUMは、1月22日付でワタナベさんとの契約解除を発表した。\
        【写真】かつてはHIKAKINさんと厚い握手を交わしていたマホトさん\
        発表では「インターネット上で発信された情報につきまして本人に確認しましたところ、概ね内容を認めました」とコメント。"
      },
      performances: [
        {
          id: "1",
          performed_at: "2020",
          title: "多摩美術大学 卒業展示",
        },
        {
          id: "2",
          performed_at: "2021",
          title: "五美大展示 東京上野展示最優秀賞",
        },
        {
          id: "3",
          performed_at: "2022",
          title: "UUUM特別賞",
        },
        {
          id: "4",
          performed_at: "2022",
          title: "Youtube最優秀暴力賞受賞",
        },
      ]

    }
  }
}
</script>
