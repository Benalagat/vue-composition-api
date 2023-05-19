<template>
    <div class="modals">
        <h1>Modal</h1>
        <button @click="showModal=true">Show modals</button>
        <Modal 
        v-if="showModal"
        title="My Modal title (via props)"
        >
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Porro ipsa iste consequuntur earum cumque dolores placeat mollitia sed nulla harum, magnam aliquam beatae rem unde ipsum velit ut asperiores recusandae!</p>
        </Modal>
 
    </div>
</template>

<script setup>
    import {ref} from 'vue'

    const showModal= ref(false)
</script>

<script>
import Modal from '@/components/Modal.vue'

export default{
    components:{
        Modal
    }
}

</script>

