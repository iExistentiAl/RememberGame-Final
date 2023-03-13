<script>

export default {
    props: {
        matched: {
            type: Boolean,
            default: false
        },
        position: {
            type: Number,
            required: true
        },
        value: {
            type: Number, 
            required: true
        },
        visible: {
            type: Boolean,
            default: false
        }
    },
    setup(props, context) {
        const selectCard = () => {
            context.emit('select-card', {
                position: props.position,
                faceValue: props.value  
            })
        }

        return{
            selectCard
        }
    }
}
    

</script>

<template>
    <div class="card" @click="selectCard">

        <div v-if="visible" class="card-face is-front">
            {{ value }}
        </div>
        <div v-else class="card-face is-back">
            WWWWW
            WWWWW
            WWWWW
            WWWWW
            WWWWW
        </div>

    </div>

</template>

<style>

.value {
    font-size: 16pt;
    text-align: center;
    
}

.card {
  border: 5px solid #fd77f7;
  position: relative;
}

.card-face {
    width: 100%;
    height: 100%;
    position: absolute;
}

.card-face.is-front {
    background-color: #63165f;
    color: white;
}

.card-face.is-back {
    background-color: rgb(0, 0, 0);
    color: purple;
}
</style>