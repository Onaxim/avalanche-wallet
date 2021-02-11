<template>
    <div class="max-w-8xl container mt-24">
        <transition name="fade" mode="out-in">
            <router-view class="access_card"></router-view>
        </transition>
    </div>
</template>
<style scoped lang="scss">
@use "../../main";

.access_view {
    display: flex;
    justify-content: center;
    align-items: center;
}

.access_card {
    text-align: center;
}
</style>
