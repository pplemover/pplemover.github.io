---
title: 브라우저의 능력을 최대로! 크롬 확장앱 만들기
author: Tao He
date: 2023-06-14
category: Jekyll
layout: post
---

### <b>크롬 브라우저 익스텐션이란</b>

업무 생산성을 높이거나 일상을 재미있게 바꾸어줄 크롬 브라우저 익스텐션 앱을 만들어 보겠습니다. 크롬 브라우저 익스텐션이란 여러분이 사용하시는 구글 크롬 웹 브라우저에 기능을 추가하거나 수정할 수 있는 소프트웨어 프로그램입니다. 일반적으로는 크롬 웹 스토어에서 다운로드하여 설치할 수 있습니다.

크롬 익스텐션은 다양한 목적을 위해 개발될 수 있습니다. 일부 익스텐션은 웹 페이지에서 광고를 차단하거나 보안 기능을 강화하는 것과 같이 브라우저의 기능을 향상시키는 역할을 합니다. 또한, 익스텐션을 통해 뉴스, 날씨, 할일 목록 등과 같은 사용자 맞춤 정보를 표시하거나 소셜 미디어 공유 버튼을 추가할 수도 있습니다. 

개발자들은 JavaScript, HTML, CSS 등을 사용하여 다양한 크롬 익스텐션을 개발하고 있습니다. 크롬 브라우저 익스텐션은 사용자가 브라우저를 보다 효율적으로 사용하고 웹 환경을 개인화하는 데에 도움을 주는 강력한 도구입니다.

이 페이지에서는 다양한 환경의 업무에 도움이 될 만한 크롬 브라우저 익스텐션을 만드는 가이드를 제공해드리겠습니다. 

<br>

### <b>`맛보기` - My Pet Photo, Anytime, Anywhere</b>
> ##### TIP
>이 가이드는 VS코드 사용을 포함하고 있습니다
{: .block-tip }

   클릭 두어번으로 사전에 등록한 반려동물 사진을 브라우저 화면에서 퀵 액세스할 수 있도록 하는 앱을 만들어 보겠습니다. 쉬운 예제이니, 쉽게 감을 익히실 수 있을 것입니다.

<details>
<summary><b>1. 폴더구조 살펴보기</b></summary>

   프로젝트의 루프 폴더 경로에 아래 사항들이 포함되어야 합니다. 
   
   - manifest.json 파일은 크롬 확장 프로그램의 설정 파일로, 확장 프로그램의 기본 정보, 권한, 아이콘, 배경 페이지 등을 정의합니다. 
   - popup.html: 앱의 메인 HTML 파일로, 앱의 인터페이스를 구성하는데 사용됩니다.
   - 스타일시트(CSS) 파일: 앱의 스타일과 레이아웃을 정의하는 CSS 파일입니다. 원하는 디자인과 사용자 경험을 구현하는 데 사용됩니다.
   - 스크립트 파일 (JavaScript): 앱의 동작을 처리하기 위한 JavaScript 파일입니다. 사용자의 상호작용, 데이터 처리, 앱 로직 등을 구현하는 데 사용됩니다.
   - images 폴더와 이미지 파일: 앱에서 사용되는 이미지 파일들을 포함합니다. 아이콘, 배경 이미지 등의 그래픽 리소스를 제공하는 데 사용됩니다.
</details>

<details>
<summary><b>2. popup.html</b></summary>
   - popup.html 파일을 수정하여 images 폴더 내에 있는 16개 이미지를 4x4 배열로 표시하고, 그에 맞는 CSS 속성과 효과를 적용하려면 다음과 같이 할 수 있습니다.

   ```
   <div class="image-grid">
      <img src="images/image1.jpg">
      <img src="images/image2.jpg">
      <!-- 나머지 이미지들도 추가 -->
   </div>
   ```


</details>

<details>
<summary><b>3. manifest.json</b></summary>

   ```
   {
   "manifest_version": 2,
   "name": "나의 확장 프로그램 이름",
   "version": "1.0",
   "description": "나의 확장 프로그램 소개 설명",
   "icons": {
      "16": "icon16.png",
      "48": "icon48.png",
      "128": "icon128.png"
   },
   "permissions": [
      "tabs",
      "storage"
   ],
   "background": {
      "scripts": ["background.js"],
      "persistent": false
   },
   "content_scripts": [
      {
         "matches": ["https://example.com/*"],
         "js": ["contentScript.js"],
         "css": ["styles.css"]
      }
   ],
   "browser_action": {
      "default_icon": "icon16.png",
      "default_popup": "popup.html"
   },
   "options_page": "options.html",
   "manifest_url": "https://example.com/manifest.json"
   }
   ```
</details>

<details>
<summary><b>4. popup.js</b></summary>

   popup.js는 클릭한 이미지를 파악하여, 해당 선택 항목을 유저 디스크에 저장합니다. 유저의 디스크에 데이터를 저장하려면 '저장' 권한을 요청해야 하는데, 이에 대한 설정은 manifest.json에서 할 수 있습니다.

   ```diff
   ---
   {
   "manifest_version": 3,
   "name": "Borify",
   "description": "See a random Bori Image",
   "version": "1.0",
   "icons": {
      "16": "images/16.png",
      "32": "images/32.png",
      "48": "images/48.png",
      "128": "images/128.png"
   },
   "action": {
      "default_icon": "images/32.png",
      "default_title": "Borify",
      "default_popup": "popup/popup.html"
   },
   + "permissions": ["storage"]
   }  
   ---
   ```

   아래 코드는 'images'란 변수에 문서 내의 모든 이미지 요소를 배열로 저장합니다. 그런 다음, 각 이미지 요소에 클릭 이벤트 리스너를 추가하여 각 이미지를 클릭했을 때 `chrome.storage.local`에 해당 이미지의 주소값(`src`)을 저장합니다.
   ```
   const images = Array.from(document.querySelectorAll("img"))

      images.forEach((img) => {
      img.addEventListener("click", ()=>{
         chrome.storage.local.set({image: img.src});
      })
   })
   ```

</details>