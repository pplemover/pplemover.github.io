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

<hr>

## 왜 Jekyll Gitbook 테마를 써야 하나요?

Jekyll Gitbook을 사용하면 Markdown 파일을 사용하여 Jekyll 웹사이트를 보다 풍부하고 전문적인 문서로 변환할 수 있습니다. 

GitBook은 웹에서 책이나 블로그와 같이 여러 장을 구성된 콘텐츠를 효과적으로 제공하고 구성하기 위한 유용한 도구입니다. Jekyll은 정적 웹사이트 생성기입니다. GitBook Jekyll은 이 두가지를 결합하여 GitBook의  GitBook 스타일을 Jekyll 웹사이트에 통합하는 방법을 제공합니다. 이러한 통합을 통해 Jekyll을 사용하는 웹사이트에서 GitBook의 강력한 문서 작성 기능을 활용할 수 있으며, 사용자는 Markdown으로 문서를 작성하고 GitBook의 다양한 기능을 웹사이트에 추가할 수 있습니다.

일반적으로 GitBook을 [Github Pages][1]에 배포하는 방법은 로컬에서 HTML 파일을 빌드한 다음, gh-pages 브랜치에 푸시하는 것입니다. 하지만 수정사항이 생길 때마다 동일한 작업을 반복해야 하고, 생성된 HTML 파일을 Git으로 버전 관리하는 것이 어려워집니다. Jekyll Gitbook는 마크다운 문서를 HTML로 렌더링할 수 있는 템플릿을 제공합니다. 따라서 원래 저장소에 변경 사항이 있을 때마다 HTML 번들을 생성하고 업로드하는 번거로움을 없앨 수 있으며, 전체 사이트를 [Github Pages][1]에 배포할 수 있습니다.

<hr>

## 시작하는 방법

This theme can be used just as other [Jekyll themes][1] and support [remote theme][12], see [the official guide][13] as well.

Jekyll Gitbook 테마를 사용하기 위해서는 이 레포지토리를 [Fork][3]하여 마크다운 문서를 `_posts` 폴더에 추가하거나, 기존의 jekyll 프로젝트에서 테마를 전환하기 위해서는 [`_config.yml`][14]에서 remote theme 설정을 변경하면 됩니다. 

```yaml
remote_theme: sighingnow/jekyll-gitbook
```

<hr>

## 포스트 추가하는 방법

_posts 폴더에 markdown 문서를 추가하면 GitBook Jekyll의 빌드 프로세스는 자동으로 markdown을 html로 변환시켜줍니다. 아래의 단계를 따라 진행하면 됩니다.

1. 우선 터미널에서 `jekyll --version` 명령어를 실행하여 Jekyll의 설치 여부와 버전 정보를 확인합니다. (Jekyll은 Ruby 기반의 도구이므로, Ruby가 시스템에 설치되어 있어야 합니다. Ruby가 설치되어 있지 않은 경우 Ruby를 설치해야 합니다.)

2. _pages 폴더에 Markdown 파일을 추가합니다. 파일 이름은 마음대로 지을 수 있지만 확장자는 .md로 설정해야 합니다.

3. 프로젝트 폴더 내에서 `jekyll build` 명령어로 웹사이트를 빌드합니다. 이 명령어는 Jekyll이 _site 폴더에 정적인 HTML 파일을 생성하도록 합니다. _site 폴더는 Jekyll이 생성한 웹사이트의 결과물이 저장되는 곳입니다. 

4. 빌드가 완료되면 _site 폴더 내에 생성된 HTML 파일을 호스팅하거나 로컬 웹 서버를 사용하여 확인할 수 있습니다. 만약 로컬 웹 서버를 사용하려면, `jekyll serve` 명령어를 실행합니다. 이 웹사이트를 브라우저에서 확인할 수 있는 주소(일반적으로 http://localhost:4000)를 출력합니다. 

This theme can be ran locally using Ruby and Gemfiles.

[Jekyll로 로컬에서 GitHub Pages를 테스트하려면 이 문서를 참고하세요](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) - GitHub

<hr>

## 빌드 과정에서 생기는 문제 해결하기

GitBook Jekyll에서 Markdown 파일을 _pages에 추가하고 jekyll build 명령어를 실행했음에도 불구하고 _site 폴더에 생성된 정적 HTML 파일이 보이지 않는 경우에는 다음 사항을 확인하세요:

- Markdown 파일의 YAML 프론트 매터(Front Matter) 가 제대로 작성되었는지 확인해야 합니다. YAML 프론트 매터는 Markdown 파일의 레이아웃, 제목, 카테고리 등의 메타데이터를 정의하는 블록입니다. Jekyll은 YAML 프론트 매터를 읽고 해당 내용을 기반으로 정적 사이트를 생성합니다. 파일에 YAML 프론트 매터가 없으면 Jekyll이 해당 파일을 처리하지 않을 수 있습니다. YAML 프론트 매터의 형식은 ---으로 시작하고 끝나야 하며, 내용은 키와 값의 쌍으로 구성되어야 합니다 

  ```
  ---
  title: Tips, Warnings, and Dangers
  author: Tao He
  date: 2022-06-30
  category: Jekyll
  layout: post
  ---
  ```

- Markdown 파일의 확장자가 .md인지 확인하세요. Jekyll은 Markdown 파일의 확장자를 .md로 기대합니다. 다른 확장자를 사용하는 경우 Jekyll이 해당 파일을 처리하지 않을 수 있습니다.
- date를 현재 시점 이후로 설정하면 `Future published date specified` 오류가 발생할 수 있습니다. date를 현재 날짜 이전으로 수정하거나, 오늘 날짜로 설정하면 게시물이 정상적으로 표시될 것입니다. _config.yaml 파일에서 future 옵션을 true로 설정하면 정상적으로 표시할 수 있습니다. 하지만 그럴 경우 시간이 지남에 따라 게시물이 자동으로 공개될 수 있음에 대해 주의해야 합니다. 이를 이용하여 게시물을 향후 원하는 특정 날짜에 자동으로 공개하고자 할 수도 있습니다. 최선의 경우에는 게시물의 date를 설정할 때 현재 날짜와 시간을 확인하고, 미래 날짜로 설정되지 않도록 주의해야 합니다.
- _config.yml 파일 확인: Jekyll의 설정 파일인 _config.yml에 include 옵션으로 _pages 디렉토리를 포함하도록 설정되어 있는지 확인하세요. _config.yml 파일을 열고 아래와 같은 설정이 있는지 확인해 보세요.
- jekyll build 명령을 실행했을 때 오류 메시지가 출력되는지 확인해 보세요. Markdown 파일에 오류가 있거나 Jekyll 설정 파일(_config.yml)에 문제가 있을 수 있습니다. jekyll build 명령을 실행할 때 -V 또는 --verbose 옵션을 추가하면 빌드 과정의 상세한 로그를 확인할 수 있습니다. 로그를 통해 어떤 파일이 처리되고 있는지, 어떤 오류가 발생하는지 등을 파악할 수 있습니다.

<hr>

## Full-text search

jekyll-gitbook 테마의 검색 기능은 [gitbook-plugin-search-pro][5] 플러그인으로 구동됩니다. (바로 사용할 수 있도록 설정값은 default로 되어 있습니다.)

[https://sighingnow.github.io/jekyll-gitbook/?q=generated](https://sighingnow.github.io/jekyll-gitbook/?q=generated)

<hr>

## 코드 스니펫 스타일 변경하기

코드 스니펫 스타일은 `_config.yaml` 에서 다음을 수정함으로써 변경할 수 있습니다.

```yaml
syntax_highlighter_style: colorful
```

default 값은 `colorful` 인데, 적용 가능한 모든 스타일을 살펴보기 위해서는 [the rouge repository][6] 를 참고하세요. [./assets/gitbook/rouge/](./assets/gitbook/rouge/)에 커스터마이징된 스타일을 추가할 수 있습니다.

<hr>

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

<hr>

## Google Analytics 와 같은 웹 분석 도구 임베딩하는 방법

Jekyll-Gitboook 테마는 `_config.yaml` 파일에서 다음과 같은 최소한의 설정으로 [Google Analytics][7], [CNZZ][8], [Application Insights][9] 웹 분석 도구를 통합할 수 있습니다.

- Google Analytics
  ```yaml
  tracker:
    google_analytics: "<YOUR GOOGLE ANALYTICS KEY, e.g, UA-xxxxxx-x>"
  ```
- CNZZ
  ```yaml
  tracker:
    cnzz: "<YOUR CNZZ ANALYTICS KEY, e.g., xxxxxxxx>"
  ```
- Application Insights
  ```yaml
  tracker:
    application_insights: "<YOUR APPLICATION INSIGHTS CONNECTION STRING>"
  ```

<hr>

## Disqus comments

Disqus는 https://disqus.com/에서 제공하는 댓글 관리 플랫폼입니다. 사용자는 Disqus를 사용하여 웹 사이트나 블로그에 댓글 기능을 추가할 수 있습니다. 댓글 기능을 활성화하려면 `_config.yaml` 파일을 다음과 같이 수정하면 됩니다.

```yaml
disqushandler: "<YOUR DISQUS SHORTNAME>"
```

<hr>

## 필요한 CSS나 JavaScript 요소를 추가하기

- 추가 CSS 파일 지정하기 
  <br> 아래와 같이 css 항목 아래에 추가적인 css 파일의 경로를 배열 형태로 지정합니다. 파일 경로는 사이트의 루트를 기준으로 상대 경로로 지정되어야 합니다. 앞에 `/` 를 붙이지 않음에 주의합니다.
  ```
  css:
  - assets/css/custom.css
  ```
  위의 예시에서 assets/css/custom.css는 추가적인 CSS 파일의 상대 경로를 나타냅니다. 이 파일은 사이트의 루트 디렉토리에서 assets/css 폴더 안에 위치해야 합니다.
  <br> 이후 설정을 저장하고 지킬-깃북 테마를 빌드하거나 로컬 서버를 실행하여 변경 사항을 적용하면 됩니다.


- extra_header_js
  <br> 아래와 같이 `extra_header_js` 항목 아래에 추가적인 스크립트 파일의 경로를 배열 형태로 지정합니다. 파일 경로는 사이트의 루트를 기준으로 상대 경로로 지정되어야 합니다. 앞에 `/` 를 붙이지 않음에 주의합니다.
  ```
  extra_header_js:
  - assets/js/custom-header.js
  ```
  `extra_footer_js`도 위의 방식과 동일합니다. 단, assets/js/custom-header.js와 assets/js/custom-footer.js는 추가적인 스크립트 파일의 상대 경로를 나타내어야 함에 주의합니다. 이 파일들은 사이트의 루트 디렉토리에서 각각 assets/js 폴더 안에 위치해야 합니다.
  <br>
  설정을 저장하고 지킬-깃북 테마를 빌드하거나 로컬 서버를 실행하여 변경 사항을 적용하면 됩니다.

<hr>

## 원하는 폰트로 수정하는 방법

폰트는 [`./assets/gitbook/custom.css`][10] 파일의 `.book.font-family-0` 및 `.book.font-family-1` 항목을 수정하여 사용자 정의할 수 있습니다.

  ```css
  .book.font-family-0 {
      font-family: Georgia, serif;
  }
  .book.font-family-1 {
      font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  }
  ```
위의 코드에서 `.book.font-family-0`는 Georgia, serif 폰트 패밀리를 나타내며, `.book.font-family-1`은 "Helvetica Neue", Helvetica, Arial, sans-serif 폰트 패밀리를 나타냅니다.

해당 CSS 코드를 수정하여 원하는 폰트 패밀리로 변경한 후, 변경 사항을 저장하고 적용할 때 지킬-깃북 테마를 빌드하거나 로컬 서버를 실행하면 커스텀 폰트가 적용됩니다.

<hr>

## 팁, 경고, 위험 블록

Jekyll-Gitbook 테마는 팁(Tip), 경고(Warning), 위험(Danger) 블록과 같은 사용자 정의 kramdown 속성인 `{: .block-tip }`, `{: .block-warning }`, `{: .block-danger }`를 지원합니다. 해당 마커는 다음과 같이 사용할 수 있습니다.

```markdown
> ##### TIP
>
> This guide is last tested with @napi-rs/canvas^0.1.20, so make sure you have
> this or a similar version after installation.
{: .block-tip }
```

[데모 보기](https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-06-30-tips_warnings_dangers.html)

<hr>

## 페이지 상단에 커버 이미지 부착하기

jekyll-gitbook 테마는 특정 페이지에 커버 이미지를 추가하기 위해 (아래와 같이) 페이지 메타데이터에 `cover` 필드를 추가하는 방법을 지원합니다. [데모 보기](https://sighingnow.github.io/jekyll-gitbook/jekyll/2022-05-24-page_cover.html)

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

<hr>

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
