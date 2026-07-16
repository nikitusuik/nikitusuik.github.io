# nikitusuik.github.io — опубликованное портфолио

Репозиторий **GitHub Pages**: готовый статический сайт после сборки Hugo.  
Живой сайт: [https://nikitusuik.github.io/](https://nikitusuik.github.io/)

Исходники (контент, конфиг, тема, CI) лежат отдельно:  
[nikitusuik/portfolio-src](https://github.com/nikitusuik/portfolio-src)

## Что это за репозиторий

| | |
| --- | --- |
| Назначение | Хостинг готового HTML/CSS после `hugo --minify` |
| Генератор | Hugo 0.154.3 + тема PaperMod |
| Обновление | Автоматически из `portfolio-src` через GitHub Actions |

Сюда **не** правят контент вручную: правки — в `portfolio-src`, деплой перезаписывает файлы в этом репо.

```text
portfolio-src  --(Actions: hugo build)-->  nikitusuik.github.io  -->  GitHub Pages
```

## Структура (сборка)

| Путь | Содержимое |
| --- | --- |
| `index.html` | Главная |
| `about/` | Страница «Обо мне» |
| `projects/` | Список проектов и карточки |
| `assets/css/` | Стили темы |
| `.nojekyll` | Отключает Jekyll на GitHub Pages |
| `sitemap.xml`, `index.xml` | Sitemap и RSS |

## Зачем так сделано

Разделение **source / publish**:

1. В `portfolio-src` — Markdown, `hugo.toml`, тема, workflow.
2. В `nikitusuik.github.io` — только результат сборки для Pages.
3. Пользовательский домен Pages по умолчанию: `https://<username>.github.io/`.

## Как изменить сайт

1. Откройте [portfolio-src](https://github.com/nikitusuik/portfolio-src).
2. Правите `content/`, `hugo.toml` и т.д.
3. После push в `main` Actions соберёт сайт и обновит этот репозиторий.
