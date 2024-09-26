<!-- eslint-disable prettier/prettier -->
<template>
    <div class="columns is-mobile is-centered is-vcentered">
        <div class="column is-narrow">
            <img
                class="image__oruga"
                src="https://raw.githubusercontent.com/oruga-ui/theme-bulma/master/public/logo.svg"
                alt="Logo Oruga Theme Bulma"
            />
        </div>
        <h1>Oruga Bulma Theme Demo</h1>
        <OModal
            v-model:active="isImportaRegistrosSIIActive"
            :cancelable="false"
            width="33rem"
            class="fix-overflow"
        >
            <div class="modal-card" style="width: 33rem">
                <header class="modal-card-head">
                    <p class="modal-card-title" style="margin-bottom: 0">
                        Importa registros de CV desde SII
                    </p>
                    <button class="delete" aria-label="close" />
                </header>

                <section class="modal-card-body">
                    <div class="columns">
                        <OField label="Período" class="column is-5">
                            <ODatepicker type="month" expanded />
                        </OField>
                        <OField label="Tipo de registro" class="column is-5">
                            <OSelect expanded>
                                <option value="1">Compras</option>
                                <option value="2">Ventas</option>
                            </OSelect>
                        </OField>
                    </div>
                </section>
                <footer class="modal-card-foot">
                    <div style="width: 100%; text-align: right">
                        <OButton class="mr-2"> Cancelar </OButton>
                        <OButton variant="link"> Importar </OButton>
                    </div>
                </footer>
            </div>
        </OModal>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isImportaRegistrosSIIActive = ref<boolean>(true);
</script>

<style scoped>
.image__oruga {
    height: 128px;
}
:deep(.fix-overflow) .modal-content {
    overflow: visible;
}
.modal-card {
    overflow: unset;
    overflow-y: visible;
}
.modal-card-body {
    overflow: visible;
}
</style>
