<template>
    <div>
                            <v-calendar
                                class="custom-calendar"
                                :attributes="attributes"
                                :columns="screens({ default: 1, lg: 2 })"  is-expanded  :available-dates='{
                                                                start: new Date(),
                                                                end: new Date(2020, 9, 30)
                                                            }'
                                >
                                    <div
                                    slot="day-content"
                                    slot-scope="{ day, attributes }"
                                    class="day_box overflow-hidden"
                                >
                                    <span>{{ day.day }}</span>
                                    <div class="flex-grow overflow-y-scroll overflow-x-auto" >
                                    <div
                                        style=""
                                        v-for="attr in attributes"
                                        class="text-xs"
                                        :class="attr.customData.class"
                                        :key="attr.key"
                                    >
                                    <b-link href="#"  variant="link">{{ attr.customData.title }}</b-link>
                                    </div>
                                    
                                    </div>
                                </div>
                            </v-calendar>
    </div>
</template>

<script>
    export default {
        name: 'EventCalendar',
        data() {
              const month = new Date().getMonth();
              const year = new Date().getFullYear();
        return {
            masks: {
                weekdays: 'WWW',
              },
        attributes: [
        {
          key: 1,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 1),
        },
        {
          key: 2,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 2),
        },
        {
          key: 3,
          customData: {
            title: '$6,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 5),
        },
        {
          key: 4,
          customData: {
            title: '$9,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 6),
        },
        {
          key: 4,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 7),
        },
        {
          key: 5,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 11),
        },
        {
          key: 6,
          customData: {
            title: '$7,888起',
            class: 'text-black',
          },
          dates: { months: 5, ordinalWeekdays: { 2: 1 } },
        },
        {
          key: 7,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 22),
        },
        {
          key: 8,
          customData: {
            title: '$8,888起',
            class: 'text-black',
          },
          dates: new Date(year, month, 25),
        },
      ],
            }
        },
        mounted() {
            
        },
        methods: {
            
        }
    }
</script>

<style>
.vc-day:not(.on-right) {
    border-right: 1px solid rgb(226, 232, 240);
}
.vc-day:not(.on-left) {
    border-right: 1px solid rgb(226, 232, 240);
}
.vc-day:not(.on-bottom) {
    border-bottom: 1px solid rgb(226, 232, 240);
}
.vc-text-sm {
    font-size: 10px !important;
    color: black;
}
.day_box{
  height: 80px;
  width: 80px;
}

</style>