<template>
    <div class="row">
        <div class="col">
            <h1>Keranjang Belanja</h1>
            <table class="table table-bordered table-striped">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Quantity</th>
                        <th>Price</th>
                        <th></th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(k, index) in keranjangbelanja" :key="index">
                        <td>{{ k.name }}</td>
                        <td>{{ k.quantity }}</td>
                        <td>{{ k.price }}</td>
                        <td class="text-center">
                            <button
                                @click="deleteProdukKeranjang(index)"
                                class="btn btn-danger"
                            >
                                Delete
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    emits: ["emit-deleteProdukKeranjang"],
    props: ["keranjangbelanja"],
    data() {
        return {};
    },
    methods: {
        deleteProdukKeranjang(index) {
            this.$emit("emit-deleteProdukKeranjang", index);
        },
    },
};
</script>
