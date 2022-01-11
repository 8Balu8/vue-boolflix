<template>
<main>
    <div class="container">
        <div class="card-contain">
            <div class="card">
                <ul>
                    <li>title</li>
                    <li>title</li>
                    <li>title</li>
                    <li>title</li>
                </ul>
            </div>
        </div>
    </div>
</main>
</template>

<script>
export default {
    name: "Main"
}
</script>

<style lang="scss" scoped>
main {
    padding: 50px;

    .card-contain {
        display: flex;
        flex-wrap: wrap;

        .card {
            width: calc((100% / 3) - 40px);
            margin: 10px 20px;
        }
    }
}
</style>