# 네이버 블로그 포스팅 주제 분류
경희대학교 데이터분석 캡스톤디자인
산업경영공학과 박혜원
경희대학교 데이터분석 캡스톤디자인 산업경영공학과 박혜원

===

## overview

## 배경 및 필요성
네이버 블로그에서는 블로그 주제와 각 포스팅의 주제를 설정할 수 있으나, 이는 블로거가 직접 선택하는 것이기 때문에 실제 주제와 명목상 주제가 다른 경우가 있다. 또한, 여러 주제가 섞여 있는 경우는 블로거 자신도 블로그의 성향과 주제를 알지 못할 때가 있다.

네이버 블로그는 항상 전문성이 있을 수록 좋다. 최근 모집 중인 네이버 인플루언서(또는 이전의 파워블로거)는 전문성이 있어야만 지원할 수 있으며, 포스팅 품질 결정 및 노출 순위 등 여러 부분에서 블로거 전문성이 영향을 미치기 때문이다. 광고주 같은 경우에도 블로그의 주제가 일관된 전문 블로거에게 상품을 제공하는 것이 좋으며, 블로거의 전문성 및 전문 주제를 빠르게 파악할 수 있게 하기 위해 다음과 같은 프로젝트를 진행하게 되었다.

## 과제 목표
첫 번째는 내 블로그의 주제를 찾는 것이다. Decision Tree 와 LDA topic modeling을 이용해 어떤 주제의 포스팅이 가장 많은지 알아 보고 블로그 대주제를 선정한다. 두 번째는 이미 한 분야에 대한 전문성을 지닌 블로그들을 이용해 LDA topic modeling의 성능을 분석해 보는 것이다. 이 과정에서 Decision Tree분류기와 LDA 분류기의 장단점, 차이점에 대해 비교해 볼 수 있다.

## 수행방법
**데이터수집**
 * BeautifulSoup 이용, 네이버 블로그 (약 130명, 4000포스팅)와 내 블로그(약 180 포스팅) 제목 및 본문 크롤링

**자연어처리**
 * Konlpy Okt 이용한 형태소 분석, Bag of words, TF-IDF, 모든 주제에서 등장할 수 있는 단어 임의적으로 불용어 처리

**주제분류기**
 * Decision Tree, LDA

## schedule
**3월** 
 * 주제 선정 (수필 쓰는 AI → 주제 변경) ✔

**4월**
 * 데이터 크롤링 (타 블로거 포스팅 포함) ✔ 
 * 데이터 점검 및 정제 ✔ 
 * 데이터 토큰화 ✔ 
 * 데이터 전처리 ✔

**5월**
 * Decision Tree 모델링 🔺 
 * LDA 모델링 ✔

**6월**
 * 모델 평가 및 수정 🔺 
 * 블로그 주제 선정 🔺 
 * 모델 비교 및 분석 ❌