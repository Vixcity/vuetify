<template>
  <v-defaults-provider
    :defaults="{
      VIcon: {
        color: one.isSubscriber && user.pins ? 'primary' : 'disabled'
      }
    }"
  >
    <SettingsSwitch
      v-model="user.pins"
      :disabled="!one.isSubscriber"
      :messages="t('dashboard.perks.enable-pins-message')"
    >
      <template #label>
        {{ t('dashboard.perks.enable-pins') }}

        <v-chip
          :text="t('new').toUpperCase()"
          class="ms-2"
          color="success"
          size="x-small"
          variant="outlined"
        />
      </template>
    </SettingsSwitch>
  </v-defaults-provider>
</template>

<script setup>
  const { t } = useI18n()
  const one = useOneStore()
  const user = useUserStore()
</script>
