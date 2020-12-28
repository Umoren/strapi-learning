<template>
    <div>
        <h2> Something is here</h2>
    </div>
</template>

<script>
import axios from 'axios'
export default {

    mounted(){
        const access_token = this.$route.query.access_token
        console.log({access_token})
        axios.get(`https://aqueous-bastion-06425.herokuapp.com/auth/github/callback${access_token}`)
            .then(res => {
                console.log(res)
            })
            .catch(err => console.log(err))

        }
    }
</script>