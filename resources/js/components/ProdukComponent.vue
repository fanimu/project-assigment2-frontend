<template>
    <div class="container">
        <h1 class="title">Semua Produk</h1>
        <daftar-produk :listdata="list" />
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            list: [
                {
                    name: "Indomie Goreng Rendang",
                    description: "Masakan instan terenak di dunia",
                    stock: 10,
                    price: 3900,
                },
                {
                    name: "Mie Gelas Rendang",
                    description: "Mie instant khusus anak kosan",
                    stock: 3,
                    price: 1500,
                },
                {
                    name: "Bakmi mewah",
                    description: "Kalau anak kosan jangan macam2 deh",
                    stock: 80,
                    price: 10000,
                },
            ],
            input: "",
        };
    },
    mounted() {
        console.log("Component mounted.");
    },
};
</script>
