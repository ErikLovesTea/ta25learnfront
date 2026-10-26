<script setup>

</script>
<template>
    <div class="tabs is-centered">
        <ul>
            <li v-for="route in $router.getRoutes()" :key="route.path" :class="{'is-active': route.path === $route.path }">
                <RouterLink :to="route.path">{{ route.name }}</RouterLink>
            </li>
        </ul>
    </div>
</template>
