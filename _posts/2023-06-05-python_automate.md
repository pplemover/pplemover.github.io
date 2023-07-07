---
title: 파이썬으로 업무자동화하기
author: pplemover
date: 2023-06-05
category: Jekyll
layout: post
---

## 파이썬으로 PDF 파일에서 텍스트 추출하기 (PDFMiner 라이브러리)

- PDFMiner은 Python 프레임워크에서 PDF 문서를 처리하는 데 사용되는 라이브러리입니다. PDFMiner를 사용하면 PDF 문서에서 텍스트, 레이아웃 및 메타데이터를 추출할 수 있습니다. 이를 통해 PDF 문서를 효과적으로 분석하고 텍스트로 변환하여 다양한 작업에 활용할 수 있습니다. 필요한 경우 PDFMiner의 [공식 문서](https://pdfminersix.readthedocs.io/)를 확인하세요. 

- PDFMiner를 사용하여 PDF를 텍스트로 변환하려면 다음 단계를 따르면 됩니다:

1. PDFMiner 설치하기
   - `pip install pdfminer.six` 명령을 실행하여 PDFMiner 패키지를 설치할 수 있습니다.

<br>

1. PDFMiner로 PDF 문서 읽기
   - PDFMiner를 사용하여 PDF 문서를 읽기 위해서는 'pdfminer.high_level' 모듈을 임포트해야 합니다. 아래 코드를 사용하여 PDF 문서를 읽고 텍스트로 변환할 수 있습니다.
      ```
      from pdfminer.high_level import extract_text

      pdf_path = 'path/to/pdf/document.pdf'
      (PDF 파일 경로 지정)

      text = extract_text(pdf_path)
      ```
    - extract_text 함수는 PDF에서 텍스트를 추출하여 문자열로 반환합니다. 

<br>

3. 이제 추출된 텍스트를 원하는 방식으로 처리하고 분석할 수 있습니다. 
   - 단, 추출된 텍스트를 새로운 txt 파일에 저장하고자 한다면 다음 명령어를 사용합니다.  
      ```
      file = open("sample.txt", "w", encoding="utf16")
      ```
      `encoding="utf16"`은 파일을 작성할 때 사용할 인코딩을 지정하는 파라미터입니다. 여기서는 UTF-16 인코딩을 사용하도록 지정하였습니다. 

      ```
      file.write(text)
      ```
      위의 명령을 실행했을 때 반환되는 숫자는 파일에 성공적으로 쓰여진 문자의 개수를 나타냅니다. 이를 통해 파일에 실제로 몇 개의 문자가 쓰여졌는지 확인할 수 있습니다.

      ```
      file.close()
      ```
      작업을 마친 후에는 `close()`를 호출하여 해당 파일과의 연결을 닫습니다. `close()` 메서드를 호출하지 않는다면 파일이 열린 상태로 유지되어 다른 문제가 발생할 수도 있습니다. 

      ```
      for line in file:
         print(line)
      ```
      위 코드는 주어진 파일을 한 줄씩 읽어와서 각 줄을 출력하는 역할을 합니다. 

<br>
<br>


## 파이썬으로 가상 인물 개인 정보 (txt 파일) 1천 개 생성하기

<br>

- 가상 인물 정보 생성은 보안 기법 중 하나입니다. 온라인 서비스에서 개인 정보를 수집하거나 저장할 때 실제 개인 정보를 사용하지 않고, 대신 가상의 정보를 활용하여 개인 식별을 어렵게 만드는 것입니다.따라서 개인 정보의 노출과 악용을 방지하여 개인정보를 보호하기 위한 목적으로 사용될 수 있습니다. 

<br>

- 우선 알아야 할 것은 파이썬에서 파일을 생성하고, 데이터를 기록하는 방법입니다. 
   ```
      myFile = open("test.txt", "w")

      myFile.write("test")

      myFile.close()
   ```  

   - 위 코드는 'text.txt' 라는 파일을 쓰기 모드('w')로 열고, 'test'라는 문자열을 파일에 씁니다. 그다음, 파일 객체를 안전하게 닫습니다. 

<br>

- 무작위로 사람 이름을 생성하는 코드는 다음과 같습니다.
   ```
   import random

   first_name_samples = "김이박최정강조윤장임나"
   middle_name_samples = "민서선예지도하주윤채현지휘"
   last_name_samples = "준윤우원호홍후서연아은진수"

   def random_name():
      result = ""
      result += random.choice(first_name_samples)
      result += random.choice(middle_name_samples)
      result += random.choice(last_name_samples)
      return result

   random_name()
   ```
   - 이는 파이썬에서 제공하는 random 모듈을 사용하여 리스트 항목 중 임의의 항목을 선택하는 원리를 차용한 것입니다. 
   - 다음으로, 결과물을 저장할 임의의 폴더를 생성합니다.
      ```
         import os
         os.mkdir("personal_info")
      ```
   -  마지막으로, 개인정보 파일을 자동으로 생성하는 부분입니다. NUM_SAMPLES 회수만큼 무작위 개인정보 생성을 반복합니다. 
      ```
      NUM_SAMPLES = 100

      for i in range(NUM_SAMPLES):
         # 무작위로 사람 이름을 생헙니다. 
         name = randome_name()

         # 결과물 파일의 이름을 정의합니다(자동생성).
         filename = "personal_info/" + str(i) + "_" + name + ".txt"

         # 결과물 파일을 생성합니다. 텅 빈 파일이 생성됩니다.
      ```
<br>

- 무작위로 이메일 주소를 생성하는 코드는 다음과 같습니다. 
   ```
      alphabet_samples = "abcdefghizklmnopqrstuvwxyz1234567890"
      
      def alphabet
   ```  