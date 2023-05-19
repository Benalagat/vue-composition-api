<template>
           <Teleport to =".modals-container">
        <div 
    
        class="modal">
            <h1>{{ title }}</h1>
            <slot/>
            <!-- <button @click="$emit('hideModal')" >Hide Modal</button> -->
            <button @click="$emit('handleButtonClick')" >Hide Modal</button>
        </div>
    </Teleport>
</template>
<script setup>

const props=defineProps({
    title: {
            type: String,
            default: "No title specified"
        }
})

const emit=defineEmits(['hideModal',false])
// export default {
//     props: {
//         title: {
//             type: String,
//             default: "No title specified"
//         }
//     }
// }
const handleButtonClick=()=>{
    emit('hideModal')
}

</script>

<style>
.modal{
    background-color: beige;
    padding: 10px;
    position: absolute;
    top: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
}
</style>