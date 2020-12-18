<template>
    <div class="navbar">
        <nav>
            <div>
                <h1>
                    <g-link to="/"> Strapi Learning Platform </g-link>
                </h1>
            </div>
            <ul>
                <li>
                    <g-link class="nav-link" to="/course/1"
                        >Strapi with Gatsby
                    </g-link>
                </li>

                <li>
                    <g-link class="nav-link" to="/course/2"
                        >Strapi with Gridsome
                    </g-link>
                </li>

                <li>
                    <g-link class="nav-link" to="/course/3"
                        >Strapi with React
                    </g-link>
                </li>
            </ul>
        </nav>
    </div>
</template>

<style scoped>
.navbar {
    width: 100%;
}
h1 a {
    color: #fff;
    text-decoration: none;
}
nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

ul {
    list-style-type: none;
    display: flex;
}

li {
    margin-left: 0.5rem;
    margin-right: 0.5rem;
}

.nav-link {
    color: #fff;
    text-decoration: none;
}
</style>
