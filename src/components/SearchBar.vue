<script>
import { store } from '../store';

export default {
    name: "SearchBar",
    emits: ["filter"],
    data() {
        return {
            store,
            archetypeOptions: ["alien", "ally of justice", "ancient gear"]
        }
    }
}
</script>

<template>
    <div class="container my-3">
        <div class="d-flex justify-content-end">
            <select class="form-select w-25" name="status" id="status" v-model="store.selectedStatus" @change="$emit('filter')">
                <option value="">All</option>
                <option :value="status" v-for="status in archetypeOptions">{{ status }}</option>
            </select>
        </div>
    </div>
</template>

