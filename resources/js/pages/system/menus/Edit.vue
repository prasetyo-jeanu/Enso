<template>

    <div class="columns is-centered">
        <div class="column is-three-quarters-desktop is-full-touch">
            <vue-form-ss class="box has-background-light raises-on-hover animated fadeIn"
                :route-params="[$route.name, $route.params.id, false]">
                <template slot="icon" slot-scope="{ field, errors }">
                    <div class="control has-icons-right">
                        <input class="input"
                            :class="{ 'is-danger': errors.has('icon') }"
                            @keydown="errors.clear(field.name)"
                            v-model="field.value"
                            type="text">
                        <span class="icon is-small is-right"
                            v-if="errors.has('icon')">
                            <fa icon="exclamation-triangle"/>
                        </span>
                    </div>
                </template>
            </vue-form-ss>
        </div>
    </div>

</template>

<script>

import { library } from '@fortawesome/fontawesome-svg-core';
import { faExclamationTriangle } from '@fortawesome/free-solid-svg-icons';
import VueFormSs from '../../../components/enso/vueforms/VueFormSs.vue';

library.add(faExclamationTriangle);

export default {
    components: { VueFormSs },
};

</script>
