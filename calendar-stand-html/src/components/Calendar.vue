<template>
  <div>
    <full-calendar class="test-fc" :events="fcEvents"
      first-day='1' locale="fr"
      @changeMonth="changeMonth"
      @eventClick="eventClick"
      @dayClick="dayClick"
      @moreClick="moreClick">
        <template slot="fc-event-card" scope="p">
            <p><i class="fa"></i> {{ p.event.title }} test</p>
        </template>
    </full-calendar>
  </div>
</template>

<script>
let demoEvents = [
  {
    title: '#white',
    start: '2017-04-25',
    end: '2017-04-25',
    cssClass: 'family'
  },
  {
    title: '#white',
    start: '2017-04-26',
    end: '2017-04-26',
    cssClass: ['home', 'work']
  },
  {
    title: '#white',
    start: '2017-04-27',
    end: '2017-04-27'
  },
  {
    title: '#white',
    start: '2017-04-27',
    end: '2017-04-27'
  },
  {
    title: '#white',
    start: '2017-04-27',
    end: '2017-04-27'
  },
  {
    title: '#white',
    start: '2017-04-26',
    end: '2017-04-26'
  },
  {
    title: '#white',
    start: '2017-04-27',
    end: '2017-04-27'
  },
  {
    title: '#white',
    start: '2017-04-27',
    end: '2017-04-27'
  },
  {
    title: '#white',
    start: '2017-03-27',
    end: '2017-03-27'
  }
]

export default {
  data () {
    return {
      name: 'Sunny!',
      fcEvents: demoEvents
    }
  },
  methods: {
    'changeMonth' (start, end, current) {
      console.log('changeMonth', start.format(), end.format(), current.format())
    },
    'eventClick' (event, jsEvent, pos) {
      console.log('eventClick', event, jsEvent, pos)
    },
    'dayClick' (day, jsEvent) {
      console.log('dayClick', day, jsEvent)
    },
    'moreClick' (day, events, jsEvent) {
      console.log('moreCLick', day, events, jsEvent)
    }
  },
  components: {
    'full-calendar': require('../fullCalendar')
  }
}
</script>

