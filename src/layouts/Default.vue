<template>
    <div class="layout">
        <header class="header">
            <Navbar />
        </header>

        <slot />
    </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import Navbar from '~/components/Navbar';
export default {
    components: {
        Navbar,
    },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Karla&display=swap');
body {
    font-family: 'Karla', sans-serif;
    margin: 0;
    padding: 0;
    background: #753ff6;
    line-height: 1.5;
}

.layout {
    max-width: 950px;
    margin: 0 auto;
    padding-left: 20px;
    padding-right: 20px;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    height: 80px;
}

.nav__link {
    margin-left: 20px;
}
</style>
