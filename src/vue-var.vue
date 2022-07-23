<script>
export default {
    name: 'VueVar',
    props: {
        data: {
            type: [Object, Array, Number, Boolean, String],
            required: true,
        },
    },
    render() {
        return this.$scopedSlots.default({
            data: this.data,
        });
    },
};
</script>