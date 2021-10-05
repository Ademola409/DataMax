<template>
    <div class="footer">
        <p>Showing {{pageNumber}} to 10 of 57 entries</p>
        <table border="1">
            <tr>
                <td><a @click="changePage('Previous')">Previous</a></td>
                <td :class="{active : pageNumber=='1'}"><button @click="changePage('1')" :class='{buttonColor:pageNumber=="1"}'>1</button></td>
                <td :class="{active : pageNumber=='2'}"><button @click="changePage('2')"  :class='{buttonColor:pageNumber=="2"}'>2</button></td>
                <td :class="{active : pageNumber=='3'}"><button @click="changePage('3')" :class='{buttonColor:pageNumber=="3"}'>3</button></td>
                <td :class="{active : pageNumber=='4'}"><button @click="changePage('4')" :class='{buttonColor:pageNumber=="4"}'>4</button></td>
                <td :class="{active : pageNumber=='5'}"><button @click="changePage('5')" :class='{buttonColor:pageNumber=="5"}'>5</button></td>
                <td :class="{active : pageNumber=='6'}"><button @click="changePage('6')" :class='{buttonColor:pageNumber=="6"}'>6</button></td>
                <td :class="{active : pageNumber=='Next'}"><button @click="changePage('Next')" :class='{buttonColor:pageNumber=="Next"}'>Next</button></td>
            </tr>
        </table>
    </div>
    
</template>


<script>
export default {
    data(){
        return {
            pageNumber:'1',

        }
    },

    methods:{
        changePage(pageNumber){
            this.pageNumber=pageNumber
        }
    }
}
</script>


<style scoped>
button{
    border:none;
    outline: none;
    background:none;
    color: blue;
}

.buttonColor{
    color: white;
}
.active{
    background: blue;
}


/* table, td{
    padding:2px
} */

.footer{
    display:flex;
    justify-content: space-between;
}
</style>