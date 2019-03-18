<template>
    <div class="navbar">
        <div class="container">
            <nav class="nav">
                <a v-bind:key="link.name" :href="link.href" v-for="link in links">{{ link.name }}</a> 
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    name:"Navigation",
    data() {
        return {
            links: [
                {
                    name:"Home",
                    href:"/",
                    View:"/pages/Home.vue"
                },
                {
                    name:"About",
                    href:"about",
                    View:"/pages/About.vue"
                },
                {
                    name:"Contact",
                    href:"contact",
                    View:"/pages/About.vue"
                }
            ]
        }
    },
    methods: {
        renderPage(e) {
            return e(this.View)
        },
        render (h) { return h(this.View) }
    }
}
</script>

<style scoped>
    .navbar {
        background:#1c1c1c;
        color:#FFF;
    }
    .nav a {
        text-transform: uppercase;
        letter-spacing: 1px;
        font-size: .8rem;
        color:#FFF;
        padding:.5rem;
        display: inline-block;
        text-decoration:none;
        transition:linear 150ms;
        border-top:3px solid transparent;
        border-bottom:3px solid transparent;
    }
    .nav a:hover {
        border-bottom:3px solid #A41E35;
    }
</style>
