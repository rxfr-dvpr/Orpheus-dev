<template>
    <main class="main">
        <NftSection/>
        <ContributionSection :lightTheme="lightTheme"/>
    </main>
</template>

<script>
import ContributionVue from './Contribution.vue'
import NftVue from './Nft.vue'

export default {
    name: "Main",
    components: {
        NftSection: NftVue,
        ContributionSection: ContributionVue
    },
    props: {
        lightTheme: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style lang="scss" scoped>
.main {
    width: 100%;
    padding: 40px 0;
}
</style>