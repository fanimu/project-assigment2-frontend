<template>
    <table class="table table-striped">
        <thead>
            <tr>
                <th>Name</th>
                <th>Description</th>
                <th>Stock</th>
                <th>Price</th>
                <th></th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(item, index) in listdata" :key="index">
                <td>{{ item.name }}</td>
                <td>{{ item.description }}</td>
                <td>{{ item.stock }}</td>
                <td>{{ item.price }}</td>
                <td>
                    <buttoncomp />
                    <button @click="addToCart(index)">Add To Cart</button>
                </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    emits: ["emit-add-to-cart"],
    props: {
        listdata: {
            type: Array,
            default: () => {
                return [];
            },
        },
    },
    methods: {
        addToCart(index) {
            if (this.listdata[index].stock > 0) {
                this.$emit("emit-add-to-cart", index);
                this.listdata[index].stock -= 1;
            } else {
                alert("Stock habis");
            }
        },
    },
};
</script>
