<template>
  <div class="mb-12">

    <section :class="$vuetify.breakpoint.name === 'xl' ? 'container' : ''">
      <v-img
        alt="Image background"
        width="100%"
        height="auto"
        :src="require('@/assets/image/kanan_atas.png')">
        <v-container class="py-8 my-8">
          <v-row class="pa-3 py-8 my-8"  align="center" no-gutters>
            <v-col cols="12" md="6">
              <div
                v-if="$vuetify.breakpoint.name !== 'xs'"
                style="
                  font-family: 'Kaushan Script', cursive !important;
                  font-size: 60px;
                "
                class="
                  text-four
                  font-weight-bold
                  text-capitalize text-justify mb-8">
                Nuha & Nabila
              </div>
              <div
                v-else
                style="
                  font-family: 'Kaushan Script', cursive !important;
                  font-size: 60px;
                "
                class="
                  d-flex flex-column
                  text-four
                  font-weight-bold
                  text-capitalize text-justify mb-8">
                  <div>Alfian An Naufal Nuha</div>
                  <div class="text-center">&</div>
                  <div class="text-right">Nabila Nurika Utada</div>
              </div>
              <p
                class="
                  font-courgette
                  text-four
                  font-weight-bold
                  text-capitalize text-justify
                  mt-5">
                Dihari Yang Berbahagia ini kami sekeleuarga ingin meminta doa untuk kelanggengan hubungan ini dan kelancaran dalam proses acara yang akan dilaksanakan pada Minggu, Tanggal Bulan Tahun pukul sekian. Terima kasih kami ucapkan.
              </p>
            </v-col>
            <v-col cols="12" md="6" class="pr-0 pl-0 custom__margin">
              <v-img
                alt="sodapos"
                height="500"
                width="500"
                class="rounded-circle"
                style="margin:auto;z-index: 1;border: 7px solid #BCAAA4"
                :src="require('@/assets/image/searching.png')"
              >
              </v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-img>
    </section>

    <svg v-if="$vuetify.breakpoint.name !== 'xs'" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        fill="#BCAAA4"
        fill-opacity="1"
        d="M0,160L48,154.7C96,149,192,139,288,112C384,85,480,43,576,69.3C672,96,768,192,864,234.7C960,277,1056,267,1152,240C1248,213,1344,171,1392,149.3L1440,128L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
      ></path>
    </svg>

    <section id="timeline" style="position: relative;top: -50px;background-color: #BCAAA4;padding: 10px 0px 10px;" class="mt-10 pt-13">
      <v-container
        style=""
        :class="$vuetify.breakpoint.name !== 'xs' ? '' : 'mt-5'"
      >
        <p class="font-kaushan white--text text-center text-decoration-underline">
          Susunan Acara
        </p>
        <v-timeline align-top dense v-for="(item,i) in timeline" :key="i">
          <v-timeline-item color="#6D4C41" small>
            <v-row class="pt-1">
              <v-col cols="3">
                <strong>{{ item.waktu }}</strong>
              </v-col>
              <v-col>
                <strong>{{ item.title }}</strong>
                <div class="body-2">
                  {{ item.description }}
                </div>
              </v-col>
            </v-row>
          </v-timeline-item>
        </v-timeline>
      </v-container>
    </section>


    <section id="gallery" style="padding: 10px 0px 10px" class="mt-10 pt-13">
      <v-img
        alt="sodapos"
        width="100%"
        height="auto"
        :src="require('@/assets/image/kiri_atas.png')"
        class="ma-auto"
      >
        <v-container :class="$vuetify.breakpoint.name !== 'xs' ? '' : 'mt-5'">
          <p class="font-kaushan text-center text-four text-decoration-underline">
            Kenangan Bersama
          </p>
          <v-row no-gutters justify="center">
            <v-col
              cols="12"
              :sm="
                $vuetify.breakpoint.name !== 'xs'
                  ? $vuetify.breakpoint.name === 'sm'
                    ? 6
                    : 4
                  : 12
              "
              v-for="n in 9"
              :key="n"
              class="d-flex child-flex py-2 px-2">
              <v-img
                :src="`https://picsum.photos/500/300?image=${n * 5 + 10}`"
                :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}`"
                aspect-ratio="1"
                class="grey lighten-2"
              >
                <template v-slot:placeholder>
                  <v-row
                    class="fill-height ma-0"
                    align="center"
                    justify="center"
                  >
                    <v-progress-circular
                      indeterminate
                      color="grey lighten-5"
                    ></v-progress-circular>
                  </v-row>
                </template>
              </v-img>
            </v-col>
          </v-row>
        </v-container>
      </v-img>
    </section>

    <section id="lokasi" style="padding: 10px 0px 10px; background-color: #BCAAA4" class="mt-10 pt-13">
      <v-container
        style=""
        :class="$vuetify.breakpoint.name !== 'xs' ? '' : 'mt-5'"
      >
        <p class="font-kaushan text-center white--text text-decoration-underline">
          Lokasi Acara
        </p>
        <v-row no-gutters>
          <v-col cols="12" md="8">
            <iframe src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d3966.199591683741!2d107.0417820749665!3d-6.2374029937508535!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zNsKwMTQnMTQuNyJTIDEwN8KwMDInMzkuNyJF!5e0!3m2!1sen!2sid!4v1689568635789!5m2!1sen!2sid"
            :width="$vuetify.breakpoint.name !== 'xs' ? 750 : 350"  height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
          </v-col>
          <v-col cols="12" md="4">
            Jl. Gatot Kaca Raya 5-2, Setiamekar, Kec. Tambun Sel., Kabupaten Bekasi, Jawa Barat 17510
          </v-col>
        </v-row>
        <a href="https://goo.gl/maps/DBdLUSrwNQDywqUp8" target="_blank">
          Buka di Google Maps
        </a>
      </v-container>
    </section>

  </div>
</template>

<script>
export default {
  middleware: false, //notAuthenticated
  data() {
    return {
      timeline: [
        {
          waktu: "08:00",
          title:  "Kedatangan",
          description:  "Kedatangan mempelai lelaki ke rumag mempelai wanita"
        },
        {
          waktu: "08:30",
          title:  "Pembukaan",
          description:  "Pembukaan Acara yang akan disampain oleh Pembawa Acara"
        },
        {
          waktu: "08:40",
          title:  "Pembacaan ayat suci Alquran",
          description:  "Pembacaan ayat suci Alquran"
        },
        {
          waktu: "08:45",
          title:  "Khutbah Nikah",
          description:  "Pelaksanaan Khutbah Nikah"
        },
        {
          waktu: "09:00",
          title:  "Ijab Qabul",
          description:  "Pelaksanaan Ijab Qabul "
        },
        {
          waktu: "10:00 - selesai",
          title:  "Pemotretan",
          description:  "Sesi Pemotretan bersama "
        },
      ],
      process: {
        run: false
      },
    };
  },
  components: {},
  watch: {
    // $route(to, from) {
    //   if (to.query.langkah) {
    //     setTimeout(() => {
    //       let elmnt = document.getElementById("langkah");
    //       elmnt.scrollIntoView();
    //     });
    //   }
    //   if (to.query.syarat) {
    //     setTimeout(() => {
    //       let elmnt = document.getElementById("syarat");
    //       elmnt.scrollIntoView();
    //     });
    //   }
    // }
  },
  computed: {},
  mounted() {
    // if (this.$route.query.langkah) {
    //   setTimeout(() => {
    //     let langkah = document.getElementById("langkah");
    //     langkah.scrollIntoView();
    //   });
    // }
    // if (this.$route.query.syarat) {
    //   setTimeout(() => {
    //     let elmnt = document.getElementById("syarat");
    //     elmnt.scrollIntoView();
    //   });
    // }
  },
  methods: {}
};
</script>

<style scoped>
  .font-kaushan{
    font-family: 'Kaushan Script', cursive !important;
    font-size: 30px;
  }
  .font-courgette{
    font-family: 'Courgette', cursive !important;
    font-size: 22px;
  }
</style>
<style lang="scss" scoped>
  @media screen and (min-width: 320px) and (max-width: 960px) {
    .custom__margin {
    margin-top : 5rem !important;
  }  
}
</style>