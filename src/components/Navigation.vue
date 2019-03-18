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
                    href:"index.html"
                },
                {
                    name:"About",
                    href:"about.html"
                },
                {
                    name:"Contact",
                    href:"contact.html"
                }
            ]
        }
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
