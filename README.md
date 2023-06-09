---
layout: home
title: Jekyll Gitbook Theme
permalink: /
---

Jekyll 테마 중 간편하고 직관적인 Gitbook 테마. 

## 개요 

GitBook Jekyll을 사용하면 Markdown 파일을 사용하여 무엇이든 전문적으로 문서화(Documentation)할 수 있습니다.

라이브 데모: [https://sighingnow.github.io/jekyll-gitbook](https://sighingnow.github.io/jekyll-gitbook)

[![Jekyll Themes](https://img.shields.io/badge/featured%20on-JekyllThemes-red.svg)](https://jekyll-themes.com/jekyll-gitbook/)

## 왜 Jekyll Gitbook 테마를 써야 하나요?

GitBook은 웹에서 책이나 블로그와 같이 여러 장을 구성된 콘텐츠를 효과적으로 제공하고 구성하기 위한 유용한 도구입니다. Jekyll은 정적 웹사이트 생성기입니다. GitBook Jekyll은 이 두가지를 결합하여 GitBook의  GitBook 스타일을 Jekyll 웹사이트에 통합하는 방법을 제공합니다. 이러한 통합을 통해 Jekyll을 사용하는 웹사이트에서 GitBook의 강력한 문서 작성 기능을 활용할 수 있으며, 사용자는 Markdown으로 문서를 작성하고 GitBook의 다양한 기능을 웹사이트에 추가할 수 있습니다

일반적으로 GitBook을 [Github Pages][1]에 배포하는 방법은 로컬에서 HTML 파일을 빌드한 다음, gh-pages 브랜치에 푸시하는 것입니다. 하지만 수정사항이 생길 때마다 동일한 작업을 반복해야 하고, 생성된 HTML 파일을 Git으로 버전 관리하는 것이 어려워집니다. Jekyll Gitbook는 마크다운 문서를 HTML로 렌더링할 수 있는 템플릿을 제공합니다. 따라서 원래 저장소에 변경 사항이 있을 때마다 HTML 번들을 생성하고 업로드하는 번거로움을 없앨 수 있으며, 전체 사이트를 [Github Pages][1]에 배포할 수 있습니다. 

요약하면, Jekyll Gitbook을 사용하면 Markdown 파일을 사용하여 Jekyll 웹사이트를 보다 풍부하고 전문적인 문서로 변환할 수 있습니다. 

## 시작하는 방법

This theme can be used just as other [Jekyll themes][1] and support [remote theme][12],
see [the official guide][13] as well.

You can introduce this jekyll theme into your own site by either

- [Fork][3] this repository and add your markdown posts to the `_posts` folder.
- Use as a remote theme in your [`_config.yml`][14](just like what we do for this
  site itself),

```yaml
remote_theme: sighingnow/jekyll-gitbook
```

### 포스트 추가하는 방법

_posts 폴더에 markdown 문서를 추가하면 GitBook Jekyll의 빌드 프로세스는 자동으로 markdown을 html로 변환시켜줍니다. 아래의 단계를 따라 진행하면 됩니다.

1. 우선 터미널에서 `jekyll --version` 명령어를 실행하여 Jekyll의 설치 여부와 버전 정보를 확인합니다. (Jekyll은 Ruby 기반의 도구이므로, Ruby가 시스템에 설치되어 있어야 합니다. Ruby가 설치되어 있지 않은 경우 Ruby를 설치해야 합니다.)

2. _pages 폴더에 Markdown 파일을 추가합니다. 파일 이름은 마음대로 지을 수 있지만 확장자는 .md로 설정해야 합니다.

3. 프로젝트 폴더 내에서 `jekyll build` 명령어로 웹사이트를 빌드합니다. 이 명령어는 Jekyll이 _site 폴더에 정적인 HTML 파일을 생성하도록 합니다. _site 폴더는 Jekyll이 생성한 웹사이트의 결과물이 저장되는 곳입니다. 

4. 빌드가 완료되면 _site 폴더 내에 생성된 HTML 파일을 호스팅하거나 로컬 웹 서버를 사용하여 확인할 수 있습니다. 만약 로컬 웹 서버를 사용하려면, `jekyll serve` 명령어를 실행합니다. 이 웹사이트를 브라우저에서 확인할 수 있는 주소(일반적으로 http://localhost:4000)를 출력합니다. 

This theme can be ran locally using Ruby and Gemfiles.

[Testing your GitHub Pages site locally with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) - GitHub


## Troubleshooting

GitBook Jekyll에서 Markdown 파일을 _pages에 추가하고 jekyll build 명령어를 실행했음에도 불구하고 _site 폴더에 생성된 정적 HTML 파일이 보이지 않는 경우 몇 가지 가능한 이유가 있을 수 있습니다. 여기에 몇 가지 확인해야 할 사항을 안내해 드리겠습니다:

Markdown 파일의 YAML 프론트 매터(Front Matter) 확인: Markdown 파일의 맨 위에 YAML 프론트 매터가 있는지 확인해야 합니다. YAML 프론트 매터는 Markdown 파일의 메타데이터를 정의하는 블록입니다. Jekyll은 YAML 프론트 매터를 읽고 해당 내용을 기반으로 정적 사이트를 생성합니다. 예를 들어, 파일의 레이아웃, 제목, 카테고리 등을 지정할 수 있습니다. 파일에 YAML 프론트 매터가 없으면 Jekyll이 해당 파일을 처리하지 않을 수 있습니다. YAML 프론트 매터의 형식은 다음과 같아야 합니다:
yaml
Copy code
---
layout: default
title: My Page
---
이 예제에서는 layout과 title 필드를 포함하고 있습니다. 필요에 따라 추가적인 필드를 정의할 수 있습니다.

YAML 프론트 매터의 구문을 다음과 같이 확인해 보세요:

YAML 프론트 매터는 ---으로 시작해야 합니다. 이것은 YAML 프론트 매터의 시작을 나타냅니다.
YAML 프론트 매터는 ---로 끝나야 합니다. 이것은 YAML 프론트 매터의 끝을 나타냅니다.
YAML 프론트 매터의 내용은 키와 값의 쌍으로 구성되어야 합니다. 각 키와 값은 콜론(:)으로 구분되어야 합니다.
YAML 문법에서 들여쓰기는 중요합니다. 들여쓰기에는 공백 문자(스페이스 또는 탭)를 사용할 수 있으며, 들여쓰기 수준에 따라 구조가 형성됩니다.
예를 들어, 아래는 유효한 YAML 프론트 매터의 예시입니다:

yaml
Copy code
---
layout: post
title: My Test Post
date: 2023-06-05
categories:
  - Blog
  - Testing
tags:
  - Jekyll
  - GitBook
---






Markdown 파일의 확장자 확인: Markdown 파일의 확장자가 .md인지 확인하세요. Jekyll은 Markdown 파일의 확장자를 .md로 기대합니다. 다른 확장자를 사용하는 경우 Jekyll이 해당 파일을 처리하지 않을 수 있습니다.

_config.yml 파일 확인: Jekyll의 설정 파일인 _config.yml에 include 옵션으로 _pages 디렉토리를 포함하도록 설정되어 있는지 확인하세요. _config.yml 파일을 열고 아래와 같은 설정이 있는지 확인해 보세요:

makefile
Copy code
include:
  - _pages
위 설정은 Jekyll에게 _pages 디렉토리의 내용을 포함하여 사이트를 빌드하도록 지시합니다.

Jekyll 빌드 오류 확인: jekyll build 명령을 실행했을 때 오류 메시지가 출력되는지 확인해 보세요. Markdown 파일에 오류가 있거나 Jekyll 설정 파일(_config.yml)에 문제가 있을 수 있습니다. 오류 메시지를 통해 문제의 원인을 파악하고 수정할 수 있습니다.
위의 사항을 확인하고 여전히 문제가 발생하는 경우, 추가적인 디버깅이 필요할 수 있습니다. 터미널에서 jekyll build 명령을 실행할 때 -V 또는 --verbose 옵션을 추가하여 상세한 출력을 확인할 수 있습니다. 예를 들어, jekyll build -V 명령을 실행하면 빌드 과정의 상세한 로그를 확인할 수 있습니다. 로그를 통해 어떤 파일이 처리되고 있는지, 어떤 오류가 발생하는지 등을 파악할 수 있습니다.

## Full-text search

The search functionality in jekyll-gitbook theme is powered by the [gitbook-plugin-search-pro][5] plugin and is enabled by default.

[https://sighingnow.github.io/jekyll-gitbook/?q=generated](https://sighingnow.github.io/jekyll-gitbook/?q=generated)

## Code highlight

The code highlight style is configurable the following entry in `_config.yaml`:

```yaml
syntax_highlighter_style: colorful
```

The default code highlight style is `colorful`, the full supported styles can be found from [the rouge repository][6]. Customized
style can be added to [./assets/gitbook/rouge/](./assets/gitbook/rouge/).

## 목차(TOC) 생성하는 방법

The jekyll-gitbook theme leverages [jekyll-toc][4] to generate the *Contents* for the page.
The TOC feature is not enabled by default. To use the TOC feature, modify the TOC
configuration in `_config.yml`:

```yaml
toc:
    enabled: true
    h_min: 1
    h_max: 3
```

## Google Analytics 임베딩이 가능하다. 

The jekyll-gitboook theme supports embedding the [Google Analytics][7], [CNZZ][8] and [Application Insights][9] website analytical tools with the following
minimal configuration in `_config.yaml`:

```yaml
tracker:
  google_analytics: "<YOUR GOOGLE ANALYTICS KEY, e.g, UA-xxxxxx-x>"
```

Similarly, CNZZ can be added with the following configuration in `_config.yaml`

```yaml
tracker:
  cnzz: "<YOUR CNZZ ANALYTICS KEY, e.g., xxxxxxxx>"
```

Application Insights can be added with the following configuration in `_config.yaml`

```yaml
tracker:
  application_insights: "<YOUR APPLICATION INSIGHTS CONNECTION STRING>"
```

## Disqus comments

Disqus는 https://disqus.com/에서 제공하는 댓글 관리 플랫폼입니다. 사용자는 Disqus를 사용하여 웹 사이트나 블로그에 댓글 기능을 추가할 수 있습니다. 댓글 기능을 활성화하려면 _config.yaml 파일에 다음과 같은 구성을 추가해야 합니다.

[Disqus](https://disqus.com/) comments can be enabled by adding the following configuration in `_config.yaml`:

```yaml
disqushandler: "<YOUR DISQUS SHORTNAME>"
```

## Extra StyleSheet or Javascript elements

You can add extra CSS or JavaScript references using configuration collections:

- extra_css: for additional style sheets. If the url does not start by http, the path must be relative to the root of the site, without a starting `/`.
- extra_header_js: for additional scripts to be included in the `<head>` tag, after the `extra_css` has been added. If the url does not start by http, the path must be relative to the root of the site, without a starting `/`.
- extra_footer_js: for additional scripts to be included at the end of the HTML document, just before the site tracking script. If the url does not start by http, the path must be relative to the root of the site, without a starting `/`.

## Customizing font settings

The fonts can be customized by modifying the `.book.font-family-0` and `.book.font-family-1` entry in [`./assets/gitbook/custom.css`][10],

```css
.book.font-family-0 {
    font-family: Georgia, serif;
}
.book.font-family-1 {
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

## Tips, Warnings and Dangers blocks

The jekyll-gitbook theme supports customized kramdown attributes (`{: .block-tip }`, `{: .block-warning }`,
`{: .block-danger }`) like that displayed in [the discord.js website][11]. The marker can be used like

```markdown
> ##### TIP
>
> This guide is last tested with @napi-rs/canvas^0.1.20, so make sure you have
> this or a similar version after installation.
{: .block-tip }
```

Rendered page can be previewed from

[https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-06-30-tips_warnings_dangers.html](https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-06-30-tips_warnings_dangers.html)

## 페이지 상단에 커버 이미지 부착하기

jekyll-gitbook 테마는 특정 페이지에 커버 이미지를 추가하기 위해 (아래와 같이) 페이지 메타데이터에 `cover` 필드를 추가하는 방법을 지원합니다.

```diff
  ---
  title: Page with cover image
  author: Tao He
  date: 2022-05-24
  category: Jekyll
  layout: post
+ cover: /assets/jekyll-gitbook/dinosaur.gif
  ---
```

The effect can be previewed from

[https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-05-24-page_cover.html](https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-05-24-page_cover.html)

## License

This work is open sourced under the Apache License, Version 2.0.

Copyright 2019 Tao He.

[1]: https://pages.github.com
[2]: https://pages.github.com/themes
[3]: https://github.com/sighingnow/jekyll-gitbook/fork
[4]: https://github.com/allejo/jekyll-toc
[5]: https://github.com/gitbook-plugins/gitbook-plugin-search-pro
[6]: https://github.com/rouge-ruby/rouge/tree/master/lib/rouge/themes
[7]: https://analytics.google.com/analytics/web/
[8]: https://www.cnzz.com/
[9]: https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview
[10]: https://github.com/sighingnow/jekyll-gitbook/blob/master/gitbook/custom.css
[11]: https://discordjs.guide/popular-topics/canvas.html#setting-up-napi-rs-canvas
[12]: https://rubygems.org/gems/jekyll-remote-theme
[13]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll
[14]: https://github.com/sighingnow/jekyll-gitbook/blob/master/_config.yml
