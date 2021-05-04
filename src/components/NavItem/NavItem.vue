<template>
    <li class="item"><a v-bind:href=link>{{link.name}}</a></li>
</template>

<script>
export default {
    name: "NavItem",
    props: {
        link: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
    .item {
        list-style: none;
        color: #ffffff;
        font-size: 15px;
        line-height: 1.75;
    }

    a {
        color: #ffffff;
        text-decoration: none;
        font-weight: 600;
        letter-spacing: 0.05em;
        font-size: 12px;
        padding: 0;
        white-space: nowrap;
        transition: .3s;
    }

    a:hover {
        text-decoration: none;
        color: grey;
    }

    @media (max-width: 992px) {
        .item {
            padding: 7px 36px 7px 36px;
            display: flex;
        }
        a {
            text-transform: uppercase;
            letter-spacing: 0.05em;
            font-size: 12px;
            font-weight: 600;
        }
    }
</style>