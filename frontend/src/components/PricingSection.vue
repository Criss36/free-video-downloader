<template>
  <section id="pricing" class="py-16 sm:py-20 bg-white" aria-labelledby="pricing-heading">
    <div class="max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-12">
        <h2 id="pricing-heading" class="text-2xl sm:text-3xl font-bold text-text-primary mb-3">
          完全免费的视频下载工具
        </h2>
        <p class="text-text-secondary text-base max-w-xl mx-auto">
          无需注册、无需付费，所有功能全部免费使用
        </p>
      </div>

      <div class="max-w-lg mx-auto">
        <div class="bg-white rounded-2xl border border-border p-7">
          <div class="mb-6 text-center">
            <h3 class="text-lg font-semibold text-text-primary mb-1">全部功能免费</h3>
            <p class="text-sm text-text-secondary">无限使用，没有任何限制</p>
          </div>
          <div class="mb-6 text-center">
            <span class="text-4xl font-bold text-text-primary">¥0</span>
            <span class="text-text-muted text-sm ml-1">/永久</span>
          </div>
          <ul class="space-y-3 mb-8 max-w-sm mx-auto">
            <li v-for="item in features" :key="item" class="flex items-start gap-2.5 text-sm text-text-secondary">
              <svg class="w-5 h-5 text-success flex-shrink-0 mt-0.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const features = [
  '无限次视频下载',
  '支持 1800+ 平台',
  '无限次 AI 视频总结',
  'AI 思维导图生成',
  'AI 视频问答',
  '字幕下载与导出',
]
</script>
