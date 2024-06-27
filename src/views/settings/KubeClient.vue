<script lang="ts" setup>

import {FormControl, FormDescription, FormField, FormItem, FormLabel, FormMessage} from "@/components/ui/form";
import {Input} from "@/components/ui/input";
import {injectStrict} from "@/lib/utils";
import {SettingsContextStateKey} from "@/providers/SettingsContextProvider";


const { settings } = injectStrict(SettingsContextStateKey);

</script>

<template>
  <div class="flex items-center justify-between">
    <FormField
        v-slot="{ componentField }"
        v-model="settings.client.kubeconfig"
        name="kubeconfig"
    >
      <FormItem class="w-1/2">
        <FormLabel>Kubeconfig</FormLabel>
        <FormControl>
          <Input
              type="text"
              placeholder="Please specify which kubeconfig file to load"
              v-bind="componentField"
          />
        </FormControl>
        <FormDescription>
          The kubeconfig file to load
        </FormDescription>
        <FormMessage />
      </FormItem>
    </FormField>
  </div>
</template>
