<template>
    <nav class="nav-bar">
        <a class="nav-bar__logo" href="#">
            <img class="nav-bar__logo--img" src="@/assets/shared/logo.svg" alt="logo">
        </a>

        <button @click="openSideMenu" class="nav-bar__hamburger">
            <img v-show="!open" class="nav-bar__hamburger--img" src="@/assets/shared/icon-hamburger.svg" alt="">
            <img v-show="open" class="nav-bar__hamburger--img" src="@/assets/shared/icon-close.svg" alt="">
        </button>

        <ul v-show="open" class="nav-bar__links-list">  
            <li class="list-item">
                <a class="list-item--link" v-for="link in links" :key="link.to">{{ link.name }}</a>
            </li>  
        </ul>
    </nav>
</template>

<script>

export default{
    name: 'NavBar',
    components: {

    },
    data() {
        return {
            open: false,
            links: [
                { to: 'home', name: '00 HOME ' },
                { to: 'destination', name: '01 DESTINATION '},
                { to: 'crew', name: '02 CREW' },
                { to: 'technology', name: '03 TECHNOLOGY ' },
            ]
        }
    },
    methods: {
        openSideMenu() {
            this.open = !this.open;
        }
    }
}
</script>

<style scoped>
.nav-bar {
    background-color: #0B0D17;
    display: flex;
        align-items: center;
        justify-content: space-between;
    height: 96px;
    overflow: visible;
    padding: 0 1.5rem 0;
    position: relative;
}

.nav-bar__logo {
   
}

.nav-bar__hamburger {
    background-color: #0B0D17;
    border: none;
    z-index: 1;
}

.nav-bar__links {
    background-color: #979797 transparent;
    display: grid;
    color: red;
    height: 50%;
    position: fixed;
        right: calc(-25% + 40px);
        top: 35px;
    width: 254px;
    z-index: 0;
}


</style>