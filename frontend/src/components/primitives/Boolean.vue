<template>
    <div>
        <div v-if="editMode">
            <v-radio-group 
                    v-model="value" 
                    row
                    @change="change">
                <template v-slot:label>
                    <div>{{label}}</div>
                </template>
                <v-radio
                        label="Y"
                        value="true"
                ></v-radio>
                <v-radio
                        label="N"
                        value="false"
                ></v-radio>
            </v-radio-group>
        </div>
        <div v-else>
            {{label}} :  {{value}}
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Boolean',
        components:{
        },
        props: {
            value:{
                type: Boolean,
                default: false
            },
            editMode: Boolean,
            label: String
        },
        methods:{
            change(){
                this.$emit("input", this.value);
            }
        }
    }
</script>
