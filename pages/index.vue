<template>
  <div>
    <div :class="`${bgDayColor} flex justify-center items-center min-h-screen text-white`">
      <h1>
        <div class="animate__animated animate__fadeInDownBig">
          <div class="text-5xl animate__animated animate__tada animate__delay-1s">
              iam<span class="inline-block text-red-600 hover:text-red-700 transition ease-in duration-700">c</span>ommee
            <i class="inline-block fas fa-cat animate__animated animate__zoomInRight animate__delay-2s"></i>
          </div>
        </div>
        <div class="text-right animate__animated animate__fadeInRightBig">
          @BUZZWOO CNX
        </div>
      </h1>
    </div>
  </div>
</template>

<script>
  export default {
    data: function () {
      return {
        bgDayColor: "",
        textDayColor: "",
      }
    },
    created: function () {
      this.bgDayColor = this.getColorPair()
      // this.textDayColor = colorPair.textColor
    },
    methods: {

      getColorPair() {
        let date = new Date()
        let day = date.getDay()
        let nextDay = day === 6 ? 0 : day + 1
        let hour = date.getHours()

        let dayColors = [{
            bgColor: "red"
          },
          {
            bgColor: "yellow"
          },
          {
            bgColor: "pink"
          },
          {
            bgColor: "green"
          },
          {
            bgColor: "orange"
          },
          {
            bgColor: "blue"
          },
          {
            bgColor: "purple"
          },
        ]

        if (hour > 0 && hour <= 12) {
          return `bg-${dayColors[day].bgColor}-500`
        }

        if (hour > 12 && hour <= 23) {
          return `bg-gradient-to-r from-${dayColors[day].bgColor}-600 to-${dayColors[nextDay].bgColor}-600`
        }

      }
    }
  }
</script>
