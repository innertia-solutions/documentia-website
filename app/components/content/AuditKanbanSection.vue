<template>
  <section class="py-16 md:py-24 bg-white dark:bg-stone-950 overflow-hidden" id="producto-flujo">
    <div class="max-w-6xl px-4 sm:px-6 lg:px-8 mx-auto">

      <!-- Header -->
      <div class="mb-10 max-w-xl">
        <p class="mb-2 font-mono text-xs text-stone-400 uppercase tracking-widest">Flujo de trabajo</p>
        <h2 class="font-bold text-2xl md:text-3xl text-stone-900 dark:text-stone-100 leading-snug">
          Cada campaña, un flujo. Cada ciclo, más inteligencia.
        </h2>
        <p class="mt-3 text-stone-500 dark:text-stone-400 leading-relaxed">
          Crea campañas de auditoría dentro de tu programa, define los estados, recopila evidencia y compara cómo mejoró cada área respecto al ciclo anterior.
        </p>
      </div>

      <!-- Kanban board -->
      <div class="overflow-x-auto pb-2 -mx-4 px-4">
        <div class="grid gap-3 min-w-[700px]" style="grid-template-columns: repeat(5, 1fr)">
          <div
            v-for="col in columns"
            :key="col.id"
            class="flex flex-col gap-2"
          >
            <!-- Column header -->
            <div class="flex items-center gap-2 pb-2.5 border-b border-stone-200 dark:border-stone-700">
              <span class="w-2 h-2 rounded-full shrink-0" :style="{ background: col.color }" />
              <span class="text-xs font-bold text-stone-600 dark:text-stone-400 uppercase tracking-wide flex-1">{{ col.label }}</span>
              <span class="text-[10px] font-semibold text-stone-400 bg-stone-100 dark:bg-stone-800 rounded-full px-2 py-0.5">{{ col.cards.length }}</span>
            </div>

            <!-- Cards -->
            <div class="flex flex-col gap-2">
              <div
                v-for="card in col.cards"
                :key="card.title"
                class="bg-white dark:bg-stone-800 border border-stone-200 dark:border-stone-700 rounded-lg p-3 hover:border-stone-300 dark:hover:border-stone-600 hover:shadow-sm transition-all cursor-default"
                :style="{ borderLeftWidth: '3px', borderLeftColor: col.color }"
              >
                <div class="flex items-center justify-between mb-1.5">
                  <span class="text-[10px] font-bold text-stone-400 uppercase tracking-wide">{{ card.area }}</span>
                  <UIcon v-if="card.ai" name="i-lucide-brain-circuit" class="size-3 text-violet-500" />
                </div>
                <p class="text-xs font-semibold text-stone-800 dark:text-stone-200 leading-snug mb-2">{{ card.title }}</p>
                <div class="flex items-center gap-1.5">
                  <UIcon :name="card.icon" class="size-3 text-stone-400" />
                  <span class="text-[10px] text-stone-400">{{ card.meta }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- AI panel -->
      <div class="mt-5 grid sm:grid-cols-[auto_1fr] gap-5 items-start border border-stone-200 dark:border-stone-700 rounded-xl bg-stone-50 dark:bg-stone-900 p-5">
        <div class="flex items-start gap-3 sm:pr-5 sm:border-r sm:border-stone-200 dark:sm:border-stone-700">
          <div class="w-9 h-9 rounded-lg bg-stone-900 dark:bg-stone-800 border border-stone-800 dark:border-stone-700 flex items-center justify-center shrink-0">
            <UIcon name="i-lucide-brain-circuit" class="size-4 text-violet-400" />
          </div>
          <div>
            <p class="text-xs font-semibold text-stone-800 dark:text-stone-200">Copiloto IA</p>
            <p class="text-xs text-stone-500 mt-0.5 italic">"¿Qué falta para la auditoría ISO 9001?"</p>
          </div>
        </div>

        <div>
          <p class="text-sm text-stone-600 dark:text-stone-400 mb-3 leading-relaxed">
            Detecté <strong class="text-stone-900 dark:text-stone-100">3 brechas</strong> para ISO 9001: la Sección 6.1 no tiene evidencia adjunta, el Manual de calidad está pendiente de aprobación, y hay 2 registros vencidos en Operaciones.
          </p>
          <div class="flex flex-wrap gap-2">
            <div
              v-for="finding in findings"
              :key="finding.text"
              class="flex items-center gap-1.5 text-xs text-stone-500 dark:text-stone-400 bg-white dark:bg-stone-800 border border-stone-200 dark:border-stone-700 rounded-full px-3 py-1"
            >
              <span class="w-1.5 h-1.5 rounded-full shrink-0" :style="{ background: finding.color }" />
              {{ finding.text }}
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup lang="ts">
const columns = [
  {
    id: 'pending',
    label: 'Sin revisar',
    color: '#94a3b8',
    cards: [
      { title: 'Política HSSEQ v2.1', area: 'Seguridad', icon: 'i-lucide-file-text', meta: 'Sin asignar', ai: false },
      { title: 'Manual de proveedores', area: 'Contratos', icon: 'i-lucide-calendar', meta: 'Vence en 8d', ai: false },
    ],
  },
  {
    id: 'review',
    label: 'En revisión',
    color: '#f59e0b',
    cards: [
      { title: 'Manual de calidad ISO', area: 'Calidad', icon: 'i-lucide-user', meta: 'Laura M.', ai: false },
      { title: 'ISO 9001 — Sección 6.1', area: 'Normativa', icon: 'i-lucide-brain-circuit', meta: 'Brecha detectada', ai: true },
    ],
  },
  {
    id: 'evidence',
    label: 'Evidencia adjunta',
    color: '#6366f1',
    cards: [
      { title: 'Registro de capacitación', area: 'RR.HH.', icon: 'i-lucide-paperclip', meta: '3 archivos', ai: false },
    ],
  },
  {
    id: 'preaudit',
    label: 'Pre-auditoría',
    color: '#f97316',
    cards: [
      { title: 'Proc. de inspección', area: 'Operaciones', icon: 'i-lucide-list-checks', meta: 'Listo', ai: false },
      { title: 'Hoja operacional T3', area: 'Planta Norte', icon: 'i-lucide-user', meta: 'Pedro A.', ai: false },
    ],
  },
  {
    id: 'approved',
    label: 'Auditado',
    color: '#22c55e',
    cards: [
      { title: 'Contrato marco 2025', area: 'Proveedor A', icon: 'i-lucide-shield-check', meta: 'Aprobado', ai: false },
    ],
  },
]

const findings = [
  { text: 'Sección 6.1 sin evidencia', color: '#6d28d9' },
  { text: 'Manual pendiente aprobación', color: '#f59e0b' },
  { text: '2 registros vencidos', color: '#f59e0b' },
  { text: 'Estimado: 3–4 días para auditoría', color: '#22c55e' },
]
</script>
