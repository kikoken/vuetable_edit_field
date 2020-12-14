<template>
    <b-container>
        <b-row>
            <b-col>
                <h2>Users</h2>
                <hr>
            </b-col>
        </b-row>
        <b-row>
            <b-col>
                <vuetable ref="vuetable"
                :fields="columns"
                :api-mode="false"
                :data="rows"
                >
                    <template slot="actions" slot-scope="props">
                        <div class="custom-actions">
                            <b-button
                                @click="onClick('edit-item',  props.rowIndex)"
                            >Button</b-button>
                        </div>
                    </template>
                </vuetable>
            
            </b-col>
        </b-row>
  </b-container>
</template>

<script>
import Vuetable from 'vuetable-2'
import usersData from '../data/users.json'


export default {
    name: "TableUsers",
    components: {
        Vuetable
    },
    data() {
        return {
            columns: ['name', 'nickname', 'email', 'gender', 'actions'],
            rows: usersData
        }
    },
    methods: {
        onClick (action, index) {
            this.rows[index].name = "Carlos Godoy"
        }
    }
}
</script>