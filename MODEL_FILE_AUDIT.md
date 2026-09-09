# Аудит соответствия моделей и HTML-результатов

Проверено: 2026-09-09 по таблице «Performance Model Ranking» (<https://docs.google.com/spreadsheets/d/1p5qP3V7fjXSbrdtDDQ6SgDxBsYxhlo21-lys-UicUxw/edit>), выгрузка от 2026-09-09 11:01.

## Правила

1. Одна строка модели в таблице = один HTML-файл в `Результаты моделей/<вендор>/`. Количество строк и файлов должно совпадать, у каждого своя пара.
2. Если в файле есть контент — в столбце `C` (Time A) обязано стоять время.
3. Если время пусто — файл обязан существовать и иметь размер 0 байт (плейсхолдер, модель не запущена).
4. Расхождение в любую сторону (контент без времени / время без контента) — обнуляем оба варианта: файл в 0 байт, ячейку времени очищаем.
5. Коммиты: один файл — один коммит, `results(<вендор>): add|update|rename|remove|reset <slug>`.

## Итог

| Показатель | Значение |
|---|---:|
| Строк в таблице | 223 |
| HTML-файлов на диске | 227 |
| Корректные непустые результаты | 182 |
| Корректные плейсхолдеры (0 байт) | 37 |
| Контент без времени | 3 |
| Время без контента | 1 |
| Строк без файла | 0 |
| Файлов без строки | 4 |
| **Нарушений правила** | **8** |

## Нарушение: контент есть, время пусто

| Строка | Вендор | Модель | Файл | Размер |
|---:|---|---|---|---:|
| 110 | MiniMax | MiniMax 3.0 | `minimax/minimax-3.html` | 125967 |
| 111 | meta | Muse Spark 1.2 | `meta/muse-spark-1-2.html` | 58239 |
| 209 | Hunyuan | Hy4 | `hunyuan/hy4.html` | 191686 |

## Нарушение: время есть, файл пустой

| Строка | Вендор | Модель | Time A | Файл |
|---:|---|---|---|---|
| 123 | Nvidia | Nemotron 3.5 Lightning | 2,10 | `nvidia/nemotron-3-5-lightning.html` |

## Файлы без строки в таблице

- `alibaba/qwen3-7-plus-thinking.html`, 31556 байт
- `inclusionai/ring-2-6-1t-high.html`, 31505 байт
- `inclusionai/ring-2-6-1t-low.html`, 27335 байт
- `thinking-machines/inkling.html`, 34034 байт

## Нормализация имён

Файлы, чьё имя не выводится из имени модели напрямую:

- `DeepSeek v3` → `deepseek/deepseek-3.html` (прямое имя было бы `deepseek-v3.html`)
- `DeepSeek v3.2` → `deepseek/deepseek-3-2.html` (прямое имя было бы `deepseek-v3-2.html`)
- `DeepSeek v3.2 DeepThink` → `deepseek/deepseek-3-2-thinking.html` (прямое имя было бы `deepseek-v3-2-deepthink.html`)
- `KAT Coder 2.5 Air` → `kwaipilot/kat-coder-air-v2.5.html` (прямое имя было бы `kat-coder-2-5-air.html`)
- `KAT Coder 2.5 Pro` → `kwaipilot/kat-coder-pro-v2.5.html` (прямое имя было бы `kat-coder-2-5-pro.html`)
- `MiniMax 3.0` → `minimax/minimax-3.html` (прямое имя было бы `minimax-3-0.html`)

## Все модели и их файлы

| Строка | Вендор | Модель | Time A | HTML-файл | Размер | Состояние |
|---:|---|---|---|---|---:|---|
| 2 | Alibaba | Qwen3 VL 235b A22B | 3,46 | `alibaba/qwen3-vl-235b-a22b.html` | 38063 | READY |
| 3 | Alibaba | Qwen3 VL 235b A22B Thinking | 6,00 | `alibaba/qwen3-vl-235b-a22b-thinking.html` | 38704 | READY |
| 4 | Alibaba | Qwen3 Coder Next | 0,52 | `alibaba/qwen3-coder-next.html` | 39890 | READY |
| 5 | Alibaba | Qwen3 Coder Plus | 1,52 | `alibaba/qwen3-coder-plus.html` | 50847 | READY |
| 6 | Alibaba | Qwen3 Max | 3,35 | `alibaba/qwen3-max.html` | 41066 | READY |
| 7 | Alibaba | Qwen3 Max Thinking | 4,50 | `alibaba/qwen3-max-thinking.html` | 43447 | READY |
| 8 | Alibaba | Qwen3.5 9b | 1,29 | `alibaba/qwen3-5-9b.html` | 16152 | READY |
| 9 | Alibaba | Qwen3.5 27b | 0,59 | `alibaba/qwen3-5-27b.html` | 28063 | READY |
| 10 | Alibaba | Qwen3.5 397B A17b | 2,52 | `alibaba/qwen3-5-397b-a17b.html` | 38821 | READY |
| 11 | Alibaba | Qwen3.6 27b | 1,06 | `alibaba/qwen3-6-27b.html` | 23199 | READY |
| 12 | Alibaba | Qwen3.6 27b Thinking | 2,45 | `alibaba/qwen3-6-27b-thinking.html` | 56526 | READY |
| 13 | Alibaba | Qwen3.6 Plus | 2,18 | `alibaba/qwen3-6-plus.html` | 33447 | READY |
| 14 | Alibaba | Qwen3.6 Max | 1,39 | `alibaba/qwen3-6-max.html` | 24568 | READY |
| 15 | Alibaba | Qwen3.6 Plus Thinking | 2,53 | `alibaba/qwen3-6-plus-thinking.html` | 46273 | READY |
| 16 | Alibaba | Qwen3.6 Max Thinking | 4,50 | `alibaba/qwen3-6-max-thinking.html` | 56660 | READY |
| 17 | Alibaba | Qwen3.7 Plus | пусто | `alibaba/qwen3-7-plus.html` | 0 | PLACEHOLDER |
| 18 | Alibaba | Qwen3.7 Max | 10,46 | `alibaba/qwen3-7-max.html` | 29957 | READY |
| 19 | Alibaba | Qwen3.8 27b | пусто | `alibaba/qwen3-8-27b.html` | 0 | PLACEHOLDER |
| 20 | Alibaba | Qwen3.8 Max | пусто | `alibaba/qwen3-8-max.html` | 0 | PLACEHOLDER |
| 21 | Anthropic | Claude Sonnet 4 | 1,37 | `anthropic/claude-sonnet-4.html` | 42480 | READY |
| 22 | Anthropic | Claude Sonnet 4 Thinking | 2,00 | `anthropic/claude-sonnet-4-thinking.html` | 32770 | READY |
| 23 | Anthropic | Claude Haiku 4.5 | 0,33 | `anthropic/claude-haiku-4-5.html` | 20049 | READY |
| 24 | Anthropic | Claude Haiku 4.5 Thinking | 0,42 | `anthropic/claude-haiku-4-5-thinking.html` | 19271 | READY |
| 25 | Anthropic | Claude Sonnet 4.5 | 1,27 | `anthropic/claude-sonnet-4-5.html` | 18045 | READY |
| 26 | Anthropic | Claude Sonnet 4.5 Thinking | 1,55 | `anthropic/claude-sonnet-4-5-thinking.html` | 28696 | READY |
| 27 | Anthropic | Claude Opus 4.5 | 4,32 | `anthropic/claude-opus-4-5.html` | 47952 | READY |
| 28 | Anthropic | Claude Opus 4.5 Thinking | 4,37 | `anthropic/claude-opus-4-5-thinking.html` | 56314 | READY |
| 29 | Anthropic | Claude Sonnet 4.6 Low | 2,58 | `anthropic/claude-sonnet-4-6-low.html` | 37064 | READY |
| 30 | Anthropic | Claude Sonnet 4.6 Medium | 9,21 | `anthropic/claude-sonnet-4-6-medium.html` | 22934 | READY |
| 31 | Anthropic | Claude Sonnet 4.6 High | 45,29 | `anthropic/claude-sonnet-4-6-high.html` | 28393 | READY |
| 32 | Anthropic | Claude Opus 4.6 Low | пусто | `anthropic/claude-opus-4-6-low.html` | 0 | PLACEHOLDER |
| 33 | Anthropic | Claude Opus 4.6 Medium | 9,59 | `anthropic/claude-opus-4-6-medium.html` | 18716 | READY |
| 34 | Anthropic | Claude Opus 4.6 Max | 10,22 | `anthropic/claude-opus-4-6-max.html` | 20322 | READY |
| 35 | Anthropic | Claude Opus 4.7 Low | 4,02 | `anthropic/claude-opus-4-7-low.html` | 20053 | READY |
| 36 | Anthropic | Claude Opus 4.7 Medium | пусто | `anthropic/claude-opus-4-7-medium.html` | 0 | PLACEHOLDER |
| 37 | Anthropic | Claude Opus 4.7 Max | 29,35 | `anthropic/claude-opus-4-7-max.html` | 35524 | READY |
| 38 | Anthropic | Claude Opus 4.8 Low | пусто | `anthropic/claude-opus-4-8-low.html` | 0 | PLACEHOLDER |
| 39 | Anthropic | Claude Opus 4.8 Medium | пусто | `anthropic/claude-opus-4-8-medium.html` | 0 | PLACEHOLDER |
| 40 | Anthropic | Claude Opus 4.8 Max | 24,58 | `anthropic/claude-opus-4-8-max.html` | 31207 | READY |
| 41 | Anthropic | Claude Opus 4.8 Ultracode | пусто | `anthropic/claude-opus-4-8-ultracode.html` | 0 | PLACEHOLDER |
| 42 | Anthropic | Claude Sonnet 5 Low | 1,15 | `anthropic/claude-sonnet-5-low.html` | 22997 | READY |
| 43 | Anthropic | Claude Sonnet 5 High | 8,56 | `anthropic/claude-sonnet-5-high.html` | 28245 | READY |
| 44 | Anthropic | Claude Sonnet 5 Max | 61,20 | `anthropic/claude-sonnet-5-max.html` | 19755 | READY |
| 45 | Anthropic | Claude Sonnet 5 Ultracode | 72,07 | `anthropic/claude-sonnet-5-ultracode.html` | 32161 | READY |
| 46 | Anthropic | Claude Opus 5 Low | 17,00 | `anthropic/claude-opus-5-low.html` | 72524 | READY |
| 47 | Anthropic | Claude Opus 5 Medium | 38,22 | `anthropic/claude-opus-5-medium.html` | 127105 | READY |
| 48 | Anthropic | Claude Opus 5 Max | 50,00 | `anthropic/claude-opus-5-max.html` | 178224 | READY |
| 49 | Anthropic | Claude Opus 5 Ultracode | 73,00 | `anthropic/claude-opus-5-ultracode.html` | 223963 | READY |
| 50 | Anthropic | Claude Fable 5 Max | 37,47 | `anthropic/claude-fable-5-max.html` | 27144 | READY |
| 51 | Anthropic | Claude Fable 5 Ultracode | 314,18 | `anthropic/claude-fable-5-ultracode.html` | 235917 | READY |
| 52 | Anthropic | Claude Fable 5.1 Low | пусто | `anthropic/claude-fable-5-1-low.html` | 0 | PLACEHOLDER |
| 53 | Anthropic | Claude Fable 5.1 Medium | пусто | `anthropic/claude-fable-5-1-medium.html` | 0 | PLACEHOLDER |
| 54 | Anthropic | Claude Fable 5.1 Max | пусто | `anthropic/claude-fable-5-1-max.html` | 0 | PLACEHOLDER |
| 55 | Anthropic | Claude Fable 5.1 Ultracode | пусто | `anthropic/claude-fable-5-1-ultracode.html` | 0 | PLACEHOLDER |
| 56 | Baidu | ERNIE X1.1 Thinking | 4,06 | `baidu/ernie-x1-1-thinking.html` | 15196 | READY |
| 57 | Baidu | ERNIE 4.5 Turbo Thinking | 2,27 | `baidu/ernie-4-5-turbo-thinking.html` | 19234 | READY |
| 58 | Baidu | ERNIE 5 Thinking | 4,14 | `baidu/ernie-5-thinking.html` | 31377 | READY |
| 59 | Baidu | ERNIE 5.1 Thinking | пусто | `baidu/ernie-5-1-thinking.html` | 0 | PLACEHOLDER |
| 60 | Cursor | Composer 1 | 0,25 | `cursor/composer-1.html` | 29571 | READY |
| 61 | Cursor | Composer 2.5 | 1,45 | `cursor/composer-2-5.html` | 33823 | READY |
| 62 | DeepSeek | DeepSeek v3 | 0,35 | `deepseek/deepseek-3.html` | 8915 | READY |
| 63 | DeepSeek | DeepSeek v3.2 | 5,34 | `deepseek/deepseek-3-2.html` | 46903 | READY |
| 64 | DeepSeek | DeepSeek v3.2 DeepThink | 5,20 | `deepseek/deepseek-3-2-thinking.html` | 47386 | READY |
| 65 | DeepSeek | DeepSeek v4 Flash | 72,27 | `deepseek/deepseek-v4-flash.html` | 98919 | READY |
| 66 | DeepSeek | DeepSeek v4 Pro | пусто | `deepseek/deepseek-v4-pro.html` | 0 | PLACEHOLDER |
| 67 | Google | Gemini 2 Flash | 0,24 | `google-deepmind/gemini/gemini-2-flash.html` | 14135 | READY |
| 68 | Google | Gemini 2.5 Flash | 0,15 | `google-deepmind/gemini/gemini-2-5-flash.html` | 14874 | READY |
| 69 | Google | Gemini 2.5 Pro | 0,52 | `google-deepmind/gemini/gemini-2-5-pro.html` | 17364 | READY |
| 70 | Google | Gemma 3 27b | 1,11 | `google-deepmind/gemma/gemma-3-27b.html` | 8988 | READY |
| 71 | Google | Gemma 4 31b | 2,57 | `google-deepmind/gemma/gemma-4-31b.html` | 19572 | READY |
| 72 | Google | Gemini 3 Flash Minimal | 0,22 | `google-deepmind/gemini/gemini-3-flash-minimal.html` | 12727 | READY |
| 73 | Google | Gemini 3 Flash High | 0,28 | `google-deepmind/gemini/gemini-3-flash-high.html` | 13869 | READY |
| 74 | Google | Gemini 3 Pro Low | 0,56 | `google-deepmind/gemini/gemini-3-pro-low.html` | 20225 | READY |
| 75 | Google | Gemini 3 Pro High | 1,14 | `google-deepmind/gemini/gemini-3-pro-high.html` | 18390 | READY |
| 76 | Google | Gemini 3.1 Flash Lite Minimal | 0,08 | `google-deepmind/gemini/gemini-3-1-flash-lite-minimal.html` | 7560 | READY |
| 77 | Google | Gemini 3.1 Flash Lite High | 0,15 | `google-deepmind/gemini/gemini-3-1-flash-lite-high.html` | 8672 | READY |
| 78 | Google | Gemini 3.1 Pro Low | 1,00 | `google-deepmind/gemini/gemini-3-1-pro-low.html` | 20759 | READY |
| 79 | Google | Gemini 3.1 Pro Med | 1,51 | `google-deepmind/gemini/gemini-3-1-pro-med.html` | 21635 | READY |
| 80 | Google | Gemini 3.1 Pro High | 2,30 | `google-deepmind/gemini/gemini-3-1-pro-high.html` | 24523 | READY |
| 81 | Google | Gemini 3.5 Flash Lite Low | 0,22 | `google-deepmind/gemini/gemini-3-5-flash-lite-low.html` | 32083 | READY |
| 82 | Google | Gemini 3.5 Flash Lite Medium | 0,33 | `google-deepmind/gemini/gemini-3-5-flash-lite-medium.html` | 38054 | READY |
| 83 | Google | Gemini 3.5 Flash Lite High | 0,37 | `google-deepmind/gemini/gemini-3-5-flash-lite-high.html` | 51108 | READY |
| 84 | Google | Gemini 3.5 Flash Minimal | 0,31 | `google-deepmind/gemini/gemini-3-5-flash-minimal.html` | 36716 | READY |
| 85 | Google | Gemini 3.5 Flash Medium | 1,42 | `google-deepmind/gemini/gemini-3-5-flash-medium.html` | 40879 | READY |
| 86 | Google | Gemini 3.5 Flash High | 2,22 | `google-deepmind/gemini/gemini-3-5-flash-high.html` | 51064 | READY |
| 87 | Google | Gemini 3.6 Flash Low | 0,50 | `google-deepmind/gemini/gemini-3-6-flash-low.html` | 48339 | READY |
| 88 | Google | Gemini 3.6 Flash Medium | 1,11 | `google-deepmind/gemini/gemini-3-6-flash-medium.html` | 53487 | READY |
| 89 | Google | Gemini 3.6 Flash High | 0,43 | `google-deepmind/gemini/gemini-3-6-flash-high.html` | 63221 | READY |
| 90 | Google | Gemini 3.7 Flash Low | 0,59 | `google-deepmind/gemini/gemini-3-7-flash-low.html` | 103411 | READY |
| 91 | Google | Gemini 3.7 Flash Medium | 1,03 | `google-deepmind/gemini/gemini-3-7-flash-medium.html` | 105103 | READY |
| 92 | Google | Gemini 3.7 Flash High | 2,15 | `google-deepmind/gemini/gemini-3-7-flash-high.html` | 114511 | READY |
| 93 | Google | Gemini 3.8 Flash Low | 1,07 | `google-deepmind/gemini/gemini-3-8-flash-low.html` | 58626 | READY |
| 94 | Google | Gemini 3.8 Flash Medium | 6,20 | `google-deepmind/gemini/gemini-3-8-flash-medium.html` | 137294 | READY |
| 95 | Google | Gemini 3.8 Flash High | 8,13 | `google-deepmind/gemini/gemini-3-8-flash-high.html` | 132085 | READY |
| 96 | inception | Mercury 2 | 0,03 | `inception/mercury-2.html` | 12151 | READY |
| 97 | inception | Mercury 2 High | 0,13 | `inception/mercury-2-high.html` | 12005 | READY |
| 98 | Kimi | Kimi 2 Thinking | 4,27 | `kimi/kimi-2-thinking.html` | 41436 | READY |
| 99 | Kimi | Kimi 2.5 | 1,33 | `kimi/kimi-2-5.html` | 31916 | READY |
| 100 | Kimi | Kimi 2.5 Thinking | 1,37 | `kimi/kimi-2-5-thinking.html` | 32065 | READY |
| 101 | Kimi | Kimi 2.6 | пусто | `kimi/kimi-2-6.html` | 0 | PLACEHOLDER |
| 102 | Kimi | Kimi 2.7 Code | 1,00 | `kimi/kimi-2-7-code.html` | 38789 | READY |
| 103 | Kimi | Kimi 3 Max | 23,48 | `kimi/kimi-3-max.html` | 93864 | READY |
| 104 | KwaiPilot | KAT Coder 2.5 Air | 1,29 | `kwaipilot/kat-coder-air-v2.5.html` | 42122 | READY |
| 105 | KwaiPilot | KAT Coder 2.5 Pro | пусто | `kwaipilot/kat-coder-pro-v2.5.html` | 0 | PLACEHOLDER |
| 106 | Liquid | LFM 2.5 1.2b Thinking | пусто | `liquid/lfm-2-5-1-2b-thinking.html` | 0 | PLACEHOLDER |
| 107 | meiTuan | LongCat 2.0 | 10,44 | `meituan/longcat-2-0.html` | 34629 | READY |
| 108 | MiniMax | MiniMax 2.5 | 1,17 | `minimax/minimax-2-5.html` | 25295 | READY |
| 109 | MiniMax | MiniMax 2.7 | 3,39 | `minimax/minimax-2-7.html` | 61220 | READY |
| 110 | MiniMax | MiniMax 3.0 | пусто | `minimax/minimax-3.html` | 125967 | НАРУШЕНИЕ: контент без времени |
| 111 | meta | Muse Spark 1.2 | пусто | `meta/muse-spark-1-2.html` | 58239 | НАРУШЕНИЕ: контент без времени |
| 112 | meta | Muse Spark 1.3 | 5,14 | `meta/muse-spark-1-3.html` | 69048 | READY |
| 113 | Mistral | Devstral 2 | 1,50 | `mistral/devstral-2.html` | 71326 | READY |
| 114 | Mistral | Ministral 3 14b | 1,53 | `mistral/ministral-3-14b.html` | 56827 | READY |
| 115 | Mistral | Mistral Large 3 | 1,32 | `mistral/mistral-large-3.html` | 42490 | READY |
| 116 | Mistral | Mistral Medium 3.1 | 1,26 | `mistral/mistral-medium-3-1.html` | 72655 | READY |
| 117 | Mistral | Mistral Medium 3.5 | 0,51 | `mistral/mistral-medium-3-5.html` | 48412 | READY |
| 118 | Mistral | Mistral Small 4 | 1,10 | `mistral/mistral-small-4.html` | 79328 | READY |
| 119 | Nex AGI | Nex N2 Pro | 8,57 | `nex-agi/nex-n2-pro.html` | 51163 | READY |
| 120 | Nvidia | Nemotron 3 Nano | 0,52 | `nvidia/nemotron-3-nano.html` | 23136 | READY |
| 121 | Nvidia | Nemotron 3 Super | 2,32 | `nvidia/nemotron-3-super.html` | 23911 | READY |
| 122 | Nvidia | Nemotron 3 Ultra | пусто | `nvidia/nemotron-3-ultra.html` | 0 | PLACEHOLDER |
| 123 | Nvidia | Nemotron 3.5 Lightning | 2,10 | `nvidia/nemotron-3-5-lightning.html` | 0 | НАРУШЕНИЕ: время без контента |
| 124 | OpenAI | GPT OSS 20b | пусто | `openai/gpt-oss/gpt-oss-20b.html` | 0 | PLACEHOLDER |
| 125 | OpenAI | GPT OSS 120b | 1,12 | `openai/gpt-oss/gpt-oss-120b.html` | 10698 | READY |
| 126 | OpenAI | GPT 4o | 0,23 | `openai/gpt/gpt-4o.html` | 8497 | READY |
| 127 | OpenAI | GPT o3 | 0,50 | `openai/gpt/gpt-o3.html` | 7617 | READY |
| 128 | OpenAI | GPT 4.1 | 1,10 | `openai/gpt/gpt-4-1.html` | 6477 | READY |
| 129 | OpenAI | GPT 5 | 0,20 | `openai/gpt/gpt-5.html` | 7316 | READY |
| 130 | OpenAI | GPT 5 High | 1,13 | `openai/gpt/gpt-5-high.html` | 22022 | READY |
| 131 | OpenAI | GPT 5.1 | 0,57 | `openai/gpt/gpt-5-1.html` | 16040 | READY |
| 132 | OpenAI | GPT 5.1 High | 3,44 | `openai/gpt/gpt-5-1-high.html` | 23981 | READY |
| 133 | OpenAI | Codex 5.1 Max Medium | 2,50 | `openai/codex/codex-5-1-max-medium.html` | 21814 | READY |
| 134 | OpenAI | Codex 5.1 Max Extra High | 2,20 | `openai/codex/codex-5-1-max-extra-high.html` | 20367 | READY |
| 135 | OpenAI | GPT 5.2 | 1,11 | `openai/gpt/gpt-5-2.html` | 8021 | READY |
| 136 | OpenAI | GPT 5.2 High | 5,12 | `openai/gpt/gpt-5-2-high.html` | 32828 | READY |
| 137 | OpenAI | GPT 5.2 Pro | 11,46 | `openai/gpt/gpt-5-2-pro.html` | 39022 | READY |
| 138 | OpenAI | Codex 5.2 Medium | 2,19 | `openai/codex/codex-5-2-medium.html` | 14404 | READY |
| 139 | OpenAI | Codex 5.2 Extra High | 11,55 | `openai/codex/codex-5-2-extra-high.html` | 27813 | READY |
| 140 | OpenAI | GPT 5.3 | 0,23 | `openai/gpt/gpt-5-3.html` | 8869 | READY |
| 141 | OpenAI | Codex 5.3 Low | 2,45 | `openai/codex/codex-5-3-low.html` | 23210 | READY |
| 142 | OpenAI | Codex 5.3 Medium | 4,23 | `openai/codex/codex-5-3-medium.html` | 23014 | READY |
| 143 | OpenAI | Codex 5.3 Extra High | 21,10 | `openai/codex/codex-5-3-extra-high.html` | 42273 | READY |
| 144 | OpenAI | Codex 5.3 Spark Extra High | пусто | `openai/codex/codex-5-3-spark-extra-high.html` | 0 | PLACEHOLDER |
| 145 | OpenAI | GPT 5.4 Nano | 1,06 | `openai/gpt/gpt-5-4-nano.html` | 46636 | READY |
| 146 | OpenAI | GPT 5.4 Nano Medium | 1,07 | `openai/gpt/gpt-5-4-nano-medium.html` | 47079 | READY |
| 147 | OpenAI | GPT 5.4 Nano Extra High | пусто | `openai/gpt/gpt-5-4-nano-extra-high.html` | 0 | PLACEHOLDER |
| 148 | OpenAI | GPT 5.4 Mini | 0,16 | `openai/gpt/gpt-5-4-mini.html` | 19536 | READY |
| 149 | OpenAI | GPT 5.4 Mini Medium | 5,01 | `openai/gpt/gpt-5-4-mini-medium.html` | 36628 | READY |
| 150 | OpenAI | GPT 5.4 Mini Extra High | 42,20 | `openai/gpt/gpt-5-4-mini-extra-high.html` | 80328 | READY |
| 151 | OpenAI | GPT 5.4 | 1,14 | `openai/gpt/gpt-5-4.html` | 30076 | READY |
| 152 | OpenAI | GPT 5.4 Low | 4,08 | `openai/gpt/gpt-5-4-low.html` | 32392 | READY |
| 153 | OpenAI | GPT 5.4 Medium | 4,33 | `openai/gpt/gpt-5-4-medium.html` | 31582 | READY |
| 154 | OpenAI | GPT 5.4 Extra High | 21,56 | `openai/gpt/gpt-5-4-extra-high.html` | 48443 | READY |
| 155 | OpenAI | GPT 5.4 Pro | 42,00 | `openai/gpt/gpt-5-4-pro.html` | 712004 | READY |
| 156 | OpenAI | GPT 5.5 | 0,43 | `openai/gpt/gpt-5-5.html` | 26806 | READY |
| 157 | OpenAI | GPT 5.5 Low | 1,34 | `openai/gpt/gpt-5-5-low.html` | 14518 | READY |
| 158 | OpenAI | GPT 5.5 Medium | 3,06 | `openai/gpt/gpt-5-5-medium.html` | 21943 | READY |
| 159 | OpenAI | GPT 5.5 Extra High | 4,10 | `openai/gpt/gpt-5-5-extra-high.html` | 35595 | READY |
| 160 | OpenAI | GPT 5.5 Pro | 13,23 | `openai/gpt/gpt-5-5-pro.html` | 25120 | READY |
| 161 | OpenAI | GPT 5.6 Luna | 0,13 | `openai/gpt/gpt-5-6-luna.html` | 9889 | READY |
| 162 | OpenAI | GPT 5.6 Luna Medium | 2,59 | `openai/gpt/gpt-5-6-luna-medium.html` | 16261 | READY |
| 163 | OpenAI | GPT 5.6 Luna Extra High | 12,08 | `openai/gpt/gpt-5-6-luna-extra-high.html` | 39241 | READY |
| 164 | OpenAI | GPT 5.6 Luna Pro | 11,14 | `openai/gpt/gpt-5-6-luna-pro.html` | 41318 | READY |
| 165 | OpenAI | GPT 5.6 Terra | пусто | `openai/gpt/gpt-5-6-terra.html` | 0 | PLACEHOLDER |
| 166 | OpenAI | GPT 5.6 Terra Medium | 3,49 | `openai/gpt/gpt-5-6-terra-medium.html` | 13247 | READY |
| 167 | OpenAI | GPT 5.6 Terra Pro | пусто | `openai/gpt/gpt-5-6-terra-pro.html` | 0 | PLACEHOLDER |
| 168 | OpenAI | GPT 5.6 Terra Ultra | 14,57 | `openai/gpt/gpt-5-6-terra-ultra.html` | 45661 | READY |
| 169 | OpenAI | GPT 5.6 Sol | пусто | `openai/gpt/gpt-5-6-sol.html` | 0 | PLACEHOLDER |
| 170 | OpenAI | GPT 5.6 Sol Medium | 6,18 | `openai/gpt/gpt-5-6-sol-medium.html` | 18054 | READY |
| 171 | OpenAI | GPT 5.6 Sol Extra High | 9,49 | `openai/gpt/gpt-5-6-sol-extra-high.html` | 50085 | READY |
| 172 | OpenAI | GPT 5.6 Sol Max | 26,40 | `openai/gpt/gpt-5-6-sol-max.html` | 120357 | READY |
| 173 | OpenAI | GPT 5.6 Sol Ultra | 23,08 | `openai/gpt/gpt-5-6-sol-ultra.html` | 74921 | READY |
| 174 | OpenAI | GPT 5.6 Sol Pro | 26,48 | `openai/gpt/gpt-5-6-sol-pro.html` | 89321 | READY |
| 175 | OpenAI | GPT 6 Astra | пусто | `openai/gpt/gpt-6-astra.html` | 0 | PLACEHOLDER |
| 176 | OpenAI | GPT 6 Astra Medium | пусто | `openai/gpt/gpt-6-astra-medium.html` | 0 | PLACEHOLDER |
| 177 | OpenAI | GPT 6 Astra Extra High | пусто | `openai/gpt/gpt-6-astra-extra-high.html` | 0 | PLACEHOLDER |
| 178 | OpenAI | GPT 6 Astra Max | пусто | `openai/gpt/gpt-6-astra-max.html` | 0 | PLACEHOLDER |
| 179 | OpenAI | GPT 6 Astra Ultra | пусто | `openai/gpt/gpt-6-astra-ultra.html` | 0 | PLACEHOLDER |
| 180 | OpenAI | GPT 6 Astra Pro | 30,52 | `openai/gpt/gpt-6-astra-pro.html` | 131116 | READY |
| 181 | Poolside | Laguna XS 2.1 | 2,25 | `poolside/laguna-xs-2-1.html` | 29318 | READY |
| 182 | Poolside | Laguna S 2.1 | пусто | `poolside/laguna-s-2-1.html` | 0 | PLACEHOLDER |
| 183 | Sakana | Fugu Ultra | пусто | `sakana/fugu-ultra.html` | 0 | PLACEHOLDER |
| 184 | StepFun | Step 3.5 Flash | 5,08 | `stepfun/step-3-5-flash.html` | 47212 | READY |
| 185 | StepFun | Step 3.7 Flash | 3,16 | `stepfun/step-3-7-flash.html` | 54292 | READY |
| 186 | Windsurf | SWE-1.5 Fast | 0,14 | `windsurf/swe-1-5-fast.html` | 35408 | READY |
| 187 | Windsurf | SWE-1.5 | 0,57 | `windsurf/swe-1-5.html` | 26301 | READY |
| 188 | xAI | Grok 4 | 1,49 | `xai/grok-4.html` | 15670 | READY |
| 189 | xAI | Grok 4.1 Fast | 0,40 | `xai/grok-4-1-fast.html` | 25927 | READY |
| 190 | xAI | Grok 4.1 Fast Thinking | 2,12 | `xai/grok-4-1-fast-thinking.html` | 28885 | READY |
| 191 | xAI | Grok 4.1 | 0,47 | `xai/grok-4-1.html` | 17002 | READY |
| 192 | xAI | Grok 4.1 Thinking | 4,07 | `xai/grok-4-1-thinking.html` | 18012 | READY |
| 193 | xAI | Grok 4.20 Medium | 1,46 | `xai/grok-4-20-medium.html` | 21887 | READY |
| 194 | xAI | Grok 4.20 Extra High | 1,44 | `xai/grok-4-20-extra-high.html` | 33458 | READY |
| 195 | xAI | Grok 4.3 | пусто | `xai/grok-4-3.html` | 0 | PLACEHOLDER |
| 196 | xAI | Grok 4.3 Low | пусто | `xai/grok-4-3-low.html` | 0 | PLACEHOLDER |
| 197 | xAI | Grok 4.3 High | пусто | `xai/grok-4-3-high.html` | 0 | PLACEHOLDER |
| 198 | xAI | Grok Build 0.1 | 3,11 | `xai/grok-build-0-1.html` | 22350 | READY |
| 199 | xAI | Grok 4.5 High | 6,42 | `xai/grok-4-5-high.html` | 58089 | READY |
| 200 | xAI | Grok 4.6 Extra High (OpenCode) | 9,43 | `xai/grok-4-6-extra-high-opencode.html` | 58671 | READY |
| 201 | xAI | Grok 4.6 Extra High (Codex) | 63,28 | `xai/grok-4-6-extra-high-codex.html` | 43921 | READY |
| 202 | xAI | Grok 4.6 Extra High (Grok Build) | 22,49 | `xai/grok-4-6-extra-high-grok-build.html` | 116867 | READY |
| 203 | Xiaomi | MiMo v2 Flash | 0,43 | `xiaomi/mimo-v2-flash.html` | 35345 | READY |
| 204 | Xiaomi | MiMo v2 Omni | 1,30 | `xiaomi/mimo-v2-omni.html` | 36611 | READY |
| 205 | Xiaomi | MiMo v2 Pro | 3,13 | `xiaomi/mimo-v2-pro.html` | 32130 | READY |
| 206 | Xiaomi | MiMo v2.5 Flash | 3,24 | `xiaomi/mimo-v2-5-flash.html` | 22175 | READY |
| 207 | Xiaomi | MiMo v2.5 Pro | 4,59 | `xiaomi/mimo-v2-5-pro.html` | 26219 | READY |
| 208 | Alpha | Ox Alpha | пусто | `alpha/ox-alpha.html` | 0 | PLACEHOLDER |
| 209 | Hunyuan | Hy4 | пусто | `hunyuan/hy4.html` | 191686 | НАРУШЕНИЕ: контент без времени |
| 210 | Z.AI | GLM 4.5 Air Thinking | 1,28 | `z-ai/glm-4-5-air-thinking.html` | 26093 | READY |
| 211 | Z.AI | GLM 4.5 Thinking | 1,40 | `z-ai/glm-4-5-thinking.html` | 28913 | READY |
| 212 | Z.AI | GLM 4.6 Thinking | 4,35 | `z-ai/glm-4-6-thinking.html` | 38595 | READY |
| 213 | Z.AI | GLM 4.6v Thinking | 1,50 | `z-ai/glm-4-6v-thinking.html` | 26355 | READY |
| 214 | Z.AI | GLM 4.7 Flash | 1,21 | `z-ai/glm-4-7-flash.html` | 21828 | READY |
| 215 | Z.AI | GLM 4.7 | 2,27 | `z-ai/glm-4-7.html` | 35817 | READY |
| 216 | Z.AI | GLM 4.7 Thinking | 2,51 | `z-ai/glm-4-7-thinking.html` | 29023 | READY |
| 217 | Z.AI | GLM 5 | 2,57 | `z-ai/glm-5.html` | 42193 | READY |
| 218 | Z.AI | GLM 5 Turbo | пусто | `z-ai/glm-5-turbo.html` | 0 | PLACEHOLDER |
| 219 | Z.AI | GLM 5 Thinking | 6,35 | `z-ai/glm-5-thinking.html` | 34580 | READY |
| 220 | Z.AI | GLM 5.1 | 1,48 | `z-ai/glm-5-1.html` | 35978 | READY |
| 221 | Z.AI | GLM 5.1 Thinking | 17,20 | `z-ai/glm-5-1-thinking.html` | 37950 | READY |
| 222 | Z.AI | GLM 5.2 Thinking | пусто | `z-ai/glm-5-2-thinking.html` | 0 | PLACEHOLDER |
| 223 | Z.AI | GLM 5.3 Flash | 108,00 | `z-ai/glm-5-3-flash.html` | 116684 | READY |
| 224 | Z.AI | GLM 5.3 | 27,49 | `z-ai/glm-5-3.html` | 94094 | READY |
