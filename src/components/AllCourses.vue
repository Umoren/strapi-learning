<template>
    <div>
        <hr />

        <div
            class="course_list"
            v-for="course in $static.allCourse.edges"
            :key="course.node.id"
        >
            <div>
                <g-image
                    :src="course.node.course_image.url"
                    alt=""
                    class="course-image"
                />
            </div>

            <div class="course-content">
                <h3>{{ course.node.title }}</h3>
                <p>{{ course.node.description }}</p>
                <p class="price">Buy for ${{ course.node.price }}</p>
                <button
                    @click="$router.push(`/course/${course.node.id}`)"
                    class="btn"
                >
                    View Course
                </button>
            </div>
        </div>
    </div>
</template>

<static-query>
    query {
      allCourse {
            edges {
                node {
                    id
                    title
                    description
                    price
                    course_image{
                        url
                    }
                }
            }
        }
    }
</static-query>

<script>
export default {
    data() {
        return {
            courses: [],
        };
    },
    mounted() {
        this.courses = this.$static.allCourse.edges;
        console.log('sfdfd', this.$static.allCourse.edges);
    },
};
</script>

<style scoped>
.course_list {
    display: flex;
    margin-top: 2rem;
    margin-bottom: 2rem;
    /* justify-content: space-between; */
    color: #fff;
    border-bottom: 2px solid #fff;
}

.btn {
    border: none;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    cursor: pointer;
    height: 4.375em;
    border-radius: 1.5em;
    padding: 0 1.5em;
    background-color: rgb(87, 41, 178);
    color: #fff;
    font-size: 14px;
    font-weight: 600;
    font-family: 'Karla';
    outline: none;
}

.course-content {
    margin-right: 5rem;
    margin-left: 5rem;
}

.price {
    font-weight: 700;
}
</style>
