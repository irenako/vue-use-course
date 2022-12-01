<script>
import Title from './components/useTitle.vue'
import Clipboard from './components/useClipboard.vue'
import Dark from './components/useDark.vue'
import onKeyStroke from './components/onKeyStroke.vue'
import MagicKeys from './components/useMagicKeys.vue'
import deviceSensors from './components/deviceSensors.vue'
import mouseAndTouch from './components/mouseAndTouch.vue'
import useScroll from './components/useScroll.vue'
import useMedia from './components/useMedia.vue'
import useInterval from './components/useInterval.vue'
import animatedSprite from './components/animatedSprite.vue'
import timeOut from './components/timeOuts.vue'
import animatingTime from './components/animatingTime.vue'
import useTransition  from './components/useTransition.vue'
import RefHistory from './components/RefHistory.vue'
import persistentStorage from './components/persistentStorage.vue'
import useFetch from './components/useFetch.vue'
import vueuseUtilities from './components/vueuseUtilities.vue'
import computedAsync from './components/computedAsync.vue'
import imageCarousel from './components/imageCarousel.vue'
export default {
  components: {
    Title, Clipboard, Dark, onKeyStroke, MagicKeys, deviceSensors, mouseAndTouch, useScroll, useMedia, useInterval, animatedSprite, timeOut, animatingTime, useTransition, RefHistory, persistentStorage, useFetch, vueuseUtilities, computedAsync, imageCarousel
}
}
</script>

<template>
<div>VueUse course</div>
<br />
<Title />
<br />
<Clipboard />
<br />
<Dark />
<br/>
<onKeyStroke />
<br />
<MagicKeys />
<br/>
<deviceSensors />
<br />
<mouseAndTouch />
<br />
<useScroll />
<br/>
<useMedia />
<br/>
<useInterval />
<br/>
<animatedSprite/>
<br/>
<timeOut />
<br/>
<animatingTime/>
<br/>
<useTransition/>
<br />
<RefHistory />
<br />
<persistentStorage />
<br />
<useFetch />
<br />
<vueuseUtilities />
<br />
<computedAsync/>
<br />
<imageCarousel/>
</template>