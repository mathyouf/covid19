<template>
  <ul :class="$style.container">
    <li :class="[$style.box, $style.parent]">
      <div :class="$style.content">
        <span>{{ $t('検査体制') }}</span>
      </div>
      <ul :class="$style.group">
        <li :class="[$style.box, $style.parent]">
          <div :class="$style.content">
            <span>{{ $t('(4)PCR・抗原検査') }}</span>
          </div>
          <ul :class="$style.group">
            <li :class="[$style.box]">
              <div :class="$style.content">
                <span>{{ $t('陽性率') }}</span>
                <monitoring-items-overview-table-value-with-translatable-unit
                  :value="items['(4)PCR・抗原検査（陽性率）'].value"
                  :unit="items['(4)PCR・抗原検査（陽性率）'].unit"
                />
              </div>
            </li>
            <li :class="[$style.box]">
              <div :class="$style.content">
                <span>{{ $t('検査人数') }}</span>
                <monitoring-items-overview-table-value-with-translatable-unit
                  :value="items['(4)PCR・抗原検査（検査人数）'].value"
                  :unit="items['(4)PCR・抗原検査（検査人数）'].unit"
                />
              </div>
            </li>
          </ul>
        </li>
      </ul>
    </li>
    <li :class="[$style.box, $style.parent]">
      <div :class="$style.content">
        <span>{{ $t('受入体制') }}</span>
      </div>
      <ul :class="$style.group">
        <li :class="[$style.box]">
          <div :class="$style.content">
            <span>{{ $t('(5)救急医療の東京ルールの適用件数') }}</span>
            <monitoring-items-overview-table-value-with-translatable-unit
              :value="items['(5)救急医療の東京ルールの適用件数'].value"
              :unit="items['(5)救急医療の東京ルールの適用件数'].unit"
            />
          </div>
        </li>
        <li :class="[$style.box, $style.parent]">
          <div :class="$style.content">
            <span>{{ $t('(6)入院患者数') }}</span>
            <monitoring-items-overview-table-value-with-translatable-unit
              :value="items['(6)入院患者数'].value"
              :unit="items['(6)入院患者数'].unit"
            />
          </div>
          <ul :class="$style.group">
            <li :class="[$style.box]">
              <div :class="$style.content">
                <span>{{ $t('確保病床') }}</span>
                <span>{{ items['(6)入院患者確保病床数'].value }}</span>
              </div>
            </li>
          </ul>
        </li>
        <li :class="[$style.box, $style.parent]">
          <div :class="$style.content">
            <span>{{ $t('(7)重症患者数') }}</span>
            <monitoring-items-overview-table-value-with-translatable-unit
              :value="items['(7)重症患者数'].value"
              :unit="items['(7)重症患者数'].unit"
            />
          </div>
          <ul :class="$style.group">
            <li :class="[$style.box]">
              <div :class="$style.content">
                <span>{{ $t('確保病床') }}</span>
                <span>{{ items['(7)重症患者確保病床数'].value }}</span>
              </div>
            </li>
          </ul>
        </li>
      </ul>
    </li>
  </ul>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
import { MonitoringItems } from '@/utils/formatMonitoringItems'
import MonitoringItemsOverviewTableValueWithTranslatableUnit from '@/components/MonitoringItemsOverviewTableValueWithTranslatableUnit.vue'

export default Vue.extend({
  components: {
    MonitoringItemsOverviewTableValueWithTranslatableUnit,
  },
  props: {
    items: {
      type: Object as PropType<MonitoringItems>,
      required: true,
    },
  },
})
</script>

<style lang="scss" module>
@import '@/assets/monitoringItemsTableCommon.scss';
</style>
