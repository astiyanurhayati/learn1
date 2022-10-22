<template>
    <div>
    <HeaderView />
    <AboutView />
    <SkillView />
    <QualityView />
    <ServiceView />
    </div>
</template>
<script>
import HeaderView from './HeaderView.vue';
import QualityView from './QualityView.vue';
import AboutView from '@/views/AboutView.vue'
import SkillView from './SkillView.vue';
import ServiceView from './ServiceView.vue';
export default {
    name: 'HomeView',
    components:{
    HeaderView,
    AboutView,
    QualityView,
    SkillView,
    ServiceView
}
}
</script>