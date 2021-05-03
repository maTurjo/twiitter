<template>

    <div id=profileCard>
        <span>{{fullName}}</span>

    </div>


</template>

<script>

export default{
    name:"profileCard",
    data(){
        return{

            user:{
                Id:1,
                Name:"tj_on_the_rocks_",
                firstName:"Mubassir Ahmed",
                lastName:"Turjo",
                followers:0
            }
        }
    },

    computed:{
        fullName(){
            return `$this.user.firstName $this.user.lastName`;
        }
    }
}
</script>


<style scoped>

</style>