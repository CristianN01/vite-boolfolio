<script>
export default {
    data() {
        return {
        
        }
    },
    props: {
        title: {
            typeof: String,
            required: true
        },
        author: {
            typeof: String,
            required: true
        },
        content: {
            typeof: String,
            required: false
        },
        projectImage: {
            typeof: String,
            required: true
        }
    }
}
</script>

<template>
    <div class="card">
        <div class="card__image">
            <img :src="projectImage" alt="project image">
        </div>
        <div class="card__content">
            <h4 class="card__title">{{ title }}</h4>
            <h6 class="card__description"><em>{{ author }}</em></h6>
            <p>{{ content }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped >
@use '../../styles/partials/variables.scss' as *;
.card {
    background-color: $secondary-color;
    border-radius: $border-radius;
    box-shadow: $box-shadow;
    max-width: 400px;
    overflow: hidden;
    transition: transform $transition-time, box-shadow $transition-time;
    margin-bottom: 2rem;

&:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

&__image img {
    width: 100%;
    display: block;
}

&__content {
    padding: 20px;

    &__title {
    font-size: 24px;
    margin: 0 0 10px;
    }

    &__description {
    font-size: 16px;
    margin: 0 0 20px;
    color: #666;
    }

    &__button {
    display: inline-block;
    padding: 10px 20px;
    background-color: $primary-color;
    color: $secondary-color;
    text-decoration: none;
    border-radius: $border-radius;
    transition: background-color $transition-time;

    &:hover {
        background-color: darken($primary-color, 10%);
    }
    }
}
}
</style>