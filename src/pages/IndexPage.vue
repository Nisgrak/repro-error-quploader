<template>
  <q-page class="column flex-center">
    <q-uploader>
      <template #header />
      <template #list="scope">
        <div
          v-if="scope.files.length === 0"
          class="
            column
            justify-center
            rounded-2xl
            items-center
            w-full
            cursor-pointer
            border-1 border-border-gray border-dashed
            p-5
          "
          @click="scope.pickFiles"
        >
          <span>
            Arrastra y suelta
          </span>
          <q-btn
            type="a"
            round
            unelevated
            color="primary"
            text-color="white"
            size="sm"
            @click="scope.pickFiles"
          >
            <q-uploader-add-trigger />
            +
          </q-btn>
        </div>
        <div v-else class="overflow-x-hidden">
          <div>
            <q-item v-for="file in scope.files" :key="file.__key">
              <q-item-section>
                <q-item-label>
                  {{ file.name }}
                </q-item-label>
              </q-item-section>

              <q-item-section v-if="file.__img" thumbnail>
                <img :src="file.__img.src" />
              </q-item-section>
            </q-item>
          </div>
        </div>
      </template>
    </q-uploader>
  </q-page>
</template>

<script setup lang="ts">
</script>
