<template>
    <div class="card">
        <img :src="imageSrc" :alt="name" class="card__image">
        <div class="card__content">
            <div class="card__title">{{name}}</div>
            <div class="card__meta">
                <p><span>Estado:</span> {{status}}</p>
                <p><span>Especie:</span> {{species}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'personaje-comp',
    props: {
        id: {
            type: String,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        status: {
            type: String,
            required: true
        },
        species: {
            type: String,
            required: true
        },
        imageSrc: {
            type: String,
            required: true
        },
    },
    data: function(){
        return {}
    }
}
</script>

<style scoped>
    .card {
        background-color: hsl(var(--clr-card-bg)/.5);
        backdrop-filter: blur(10px);
        box-shadow: 
            inset -1px 0px 0px hsl(var(--clr-white)/.1),
            inset -1px 2px 4px hsl(var(--clr-white)/.1);
        border-radius: .625rem;
        padding: .9375rem 1.875rem 1.875rem;
    }
    .card__image {
        border-radius: 50%;
        border: 5px solid hsl(var(--clr-card-bg)/.7);
        margin-top: -6.25rem;
        margin-left: -.9375rem;
        height: 6.25rem;
        width: 6.25rem;
    }
    .card__content {
        color: hsl(var(--clr-white));
        margin-top: 1.25rem;
    }
    .card__title {
        font-family: var(--ff-heading);
        font-size: 1.25rem;
        font-weight: bold;
        margin-bottom: .625rem;
    }
    .card__meta {
        display: flex;
        flex-direction: column;
    }
    .card__meta p {
        margin: 0;
    }
    .card__meta span {
        font-weight: bold;
    }
</style>