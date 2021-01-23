<template>
  <v-row
    justify="center"
    align="center"
    >
    <v-col
      cols="12"
      v-for="item in data"
      :key="item.id"
    >
      <v-card
        max-width="700"
        class="mx-auto"
        >
      <v-img
        position="center"
        :src="item.image"
      >
      </v-img>
      <v-card-title class="headline">
        {{ item.title }}
      </v-card-title>
      <v-card-text>
        <p>{{ item.created_at }}</p>
        <p>{{ item.size }}</p>
        <b>{{ item.description }}</b>
      </v-card-text>

      </v-card>
    </v-col>
  </v-row>

</template>

<script>
  const images = [
    {
      id: 1,
      image: "https://i.gyazo.com/e784de0521be5a4cbfca2a5a315ac4bb.png",
      title: "hell.o",
      created_at: "2020-1",
      size: "3m",
      description: "卒制で展示しました。"
    },
    {
      id: 2,
      image: "https://i.gyazo.com/e784de0521be5a4cbfca2a5a315ac4bb.png",
      title: "刺繍1",
      created_at: "2020-1",
      size: "3m",
      description: "あの青い空の波の音が聞こえるあたりに\
何かとんでもないおとし物を\
僕はしてきてしまったらしい\
透明な過去の駅で\
遺失物係の前に立ったら\
僕は余計に悲しくなってしまった"
    },
    {
      id: 3,
      image: "https://i.gyazo.com/e784de0521be5a4cbfca2a5a315ac4bb.png",
      title: "タイトル1",
      created_at: "2020-2",
      size: "3m",
      description: "宇都宮市は、栃木県の県庁所在地で、\
県の中南部、関東平野の中北部に位置する。\
中心市街地は日光連山から連なる山地が収束し平野部となる境界域、\
二荒山神社（ふたあらやまじんじゃ）と\
宇都宮城址公園付近を中心に形成されている。"
    },
    {
      id: 4,
      image: "https://i.gyazo.com/e784de0521be5a4cbfca2a5a315ac4bb.png",
      title: "タイトル2",
      created_at: "2020-3",
      size: "3m",
      description: "市域には鬼怒川（きぬがわ）、\
田川、釜川、新川（しんかわ）、姿川などの河川が流れ\
河岸はその河岸段丘と沖積平野となっている。",
    },
  ]
  export default {
    data() {
      return {
        data: images
      }
    }

    }
</script>
