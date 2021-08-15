<template>
    <div class="form">
        <b-form>
            <b-row v-for="(field,index) in formData" :key="index" class="mb-3">
                <b-col lg="3">
                    <b-form-group>
                        <b-form-input placeholder="Name" v-model="field.name" />
                    </b-form-group>
                </b-col>
                <b-col lg="3">
                    <b-form-group>
                        <b-form-input placeholder="Phone" type="number" v-model="field.phone" />
                    </b-form-group>
                </b-col>
                <b-col lg="3">
                    <b-form-group>
                        <b-form-input placeholder="Address"  v-model="field.address" />
                    </b-form-group>
                </b-col>
                <b-col lg="2" class="text-center d-flex justify-content-around align-items-center">
                    <b-btn v-if="index > 0" @click="$emit('remove',index)" class="btn-sm" variant="danger"><b-icon-x /></b-btn>
                    <b-btn v-if="index === formData.length -1" @click="$emit('addmore')" class="btn-sm" variant="success"><b-icon-plus /></b-btn>
                </b-col>
            </b-row>
        </b-form>
    </div>
</template>

<script>
    export default {
        props:['formData'],
        name: "Form"
    }
</script>

<style scoped>

</style>