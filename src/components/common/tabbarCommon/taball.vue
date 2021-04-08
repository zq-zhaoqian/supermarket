<template>
    <div class="taball">
        <slot></slot>
    </div>
</template>
<script>
import tabsolt from './tabsolt'
export default {
    name:'taball',
    components:{tabsolt}
}
</script>
<style scoped>
.tab-bar img{
    width: 24px;
    margin-top: 2px;
}
.icon-test{
    font-size: 12px;
}
</style>
