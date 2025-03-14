<template>
    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <p class="text-center font-semibold">Clinic Review</p>
      <div class="space-y-4 flex flex-col justify-center">
        <UButton color="red" label="Login with Google" icon="i-heroicons-globe-alt-16-solid" block />
      </div>
    </UCard>

    <!-- <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800 bg-white">
      <template #default="{ link }">
        <span class="group-hover:text-primary relative">{{ link.label }}</span>
      </template>
    </UHorizontalNavigation> -->

    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <div class="flex">
        <div
          class="relative flex items-center p-1 shadow-sm bg-white dark:bg-gray-900 ring-1 ring-inset ring-gray-300 dark:ring-gray-700 rounded-md">
          <UInput icon="i-heroicons-magnifying-glass-20-solid" color="white" :trailing="false" placeholder="Search..."
            class="w-full h-fit" size="md" :ui="{ color: { white: { outline: 'ring-0 focus:ring-0 shadow-none' } } }" />
        </div>
        <BizShareActionNormal label="ค้นหา" :blocked="false" size="md" color="gray" />
      </div>

      <div v-for="item in items">
        <div class="flex justify-center"><span
            class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full">
            <div>
              <img class="mx-auto my-auto" :src="item" width="150" height="180" draggable="false">
              <div class="absolute top-0 bottom-0 left-0 right-0 py-5 bg-gray-500 opacity-70">
                <div class="text-center mt-16">
                  <UIcon name="i-heroicons-play-circle-16-solid" class="w-5 h-5  bg-white" />
                </div>
              </div>
            </div>
          </span>
        </div>
      </div>

      <div class="flex justify-center items-center">
        <UButton color="red" label="Home" />
        <UButton class="mx-10" color="red" label="Upload" />
        <UButton color="red" label="Profile" />
      </div>
    </UCard>


    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <div class="flex justify-center items-center">
        <UIcon class="w-24 h-24" name="i-heroicons-cloud-arrow-down" />
      </div>
      <UInput type="file" />
      <div class="flex justify-center items-center">
        <UButton color="red">Upload</UButton>
      </div>
    </UCard>

    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

      <div class="flex"><span class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full">
          <div>
            <img src="https://picsum.photos/1920/1080?random=1" width="200" height="200" draggable="false">
            <div class="absolute top-0 bottom-0 left-0 right-0 py-5 bg-gray-500 opacity-70">
              <div class="text-center mt-8">
                <UIcon name="i-heroicons-play-circle-16-solid" class="w-5 h-5  bg-white" />
              </div>
            </div>
          </div>
        </span>
      </div>

      <UFormGroup label="clinic" />
      <USelect v-model="country" :options="countries" />

      <UFormGroup label="description" />
      <UInput />

      <div class="flex justify-center items-center">
        <UButton color="red">post</UButton>
      </div>
    </UCard>

    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <div class="text-center mx-auto">
        <UAvatar src="https://picsum.photos/1920/1080?random=1" size="3xl" class="mx-auto mb-2" />
        <p>clinic M</p>
      </div>
    </UCard>

    <UAlert description="ทำจมูก" title="Course A"
      :close-button="{ label: 'ดูละเอียดเพิ่มเติม', color: 'gray', variant: 'link', padded: false }" />

    <UAlert description="ทำตา" title="Course B"
      :close-button="{ label: 'ดูละเอียดเพิ่มเติม', color: 'gray', variant: 'link', padded: false }" />


    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <div class="flex justify-center items-center" @click="isOpen = true">
        <img src="https://failfast.blob.core.windows.net/mcontent-imgs/temps/delivery/dfqr.png" width="200" height="200"
          draggable="false">
      </div>
      <div class="flex justify-center items-center">
        <UButton color="red">Save</UButton>
      </div>

    </UCard>
    <UModal v-model="isOpen" :preventClose='true' :ui="{ container: 'items-center sm:items-center' }">
      <UCard>
        <BizShareText class="text-center pb-6" text="ทำการจ่ายเงินสำเร็จ" />
        <BizShareGroupButton :right-alignment="true">
          <BizShareActionNormal label="ปิด" :block="false" color="gray" variant="ghost" @click="isOpen = false" />
        </BizShareGroupButton>
      </UCard>
    </UModal>
</template>

<script setup lang="ts">

const links = [{
  label: 'Home',
  // to: '/delivery/3rd/shopSelect',
}, {
  label: 'Profile',
}, {
  label: 'MyOrders',
}]


const items = [
  'https://picsum.photos/600/800?random=1',
  'https://picsum.photos/600/800?random=2',
]

const isOpen = ref(false);
const countries = ['United States', 'Canada', 'Mexico']
const country = ref(countries[0])
</script>