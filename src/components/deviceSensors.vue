<script setup>
import { useBattery, useOnline, useGeolocation } from '@vueuse/core';
const battery = useBattery();
const online = useOnline();
const { coords, locatedAt, error } = useGeolocation()
</script>

<template>
  {{ battery }}
  <br/>
  <p>Online: {{online}} </p>
  <br />
    <pre lang="json">{{
        JSON.stringify(
          {
            coords: {
              accuracy: coords.accuracy,
              latitude: coords.latitude,
              longitude: coords.longitude,
              altitude: coords.altitude,
              altitudeAccuracy: coords.altitudeAccuracy,
              heading: coords.heading,
              speed: coords.speed,
            },
            locatedAt,
            error: error ? error.message : error,
          },
          null,
          2
        )
      }}</pre>
</template>
