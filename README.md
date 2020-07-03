# 네이버 블로그 포스팅 주제 분류
경희대학교 데이터분석 캡스톤디자인 산업경영공학과 박혜원


## overview

## 배경 및 필요성
 * 네이버 블로그에서는 블로그 주제와 각 포스팅의 주제를 설정할 수 있으나, 이는 블로거가 직접 선택하는 것이기 때문에 실제 주제와 명목상 주제가 다른 경우가 많다. 또한, 여러 주제가 섞여 있는 경우는 블로거 자신도 블로그의 주제와 방향성을 알지 못할 때가 있다.  

 * 네이버 블로그는 항상 전문성이 있을수록 좋다. 최근 모집 중인 네이버 인플루언서(또는 이전의 파워블로거)는 전문성이 있어야만 지원할 수 있으며, 포스팅 품질 결정 및 노출 순위 등 여러 부분에서 블로거 전문성이 영향을 미치기 때문이다.  

 * 광고주 같은 경우에도 블로그의 주제가 일관된 전문 블로거에게 상품을 제공하는 것이 좋다. 토픽 모델링을 한다면 블로거의 전문성 및 전문 주제를 빠르게 파악할 수 있다. 

<br>
<br>

## 과제 목표
 * 첫 번째는 내 블로그의 주제를 찾는 것이다. KMeans와 LDA topic modeling을 이용해 어떤 주제의 포스팅이 가장 많은지 알아보고 블로그 대주제를 선정한다.  

 * 두 번째는 이미 한 분야에 대한 전문성을 지닌 블로그들을 이용해 각 모델의 성능을 분석해 보는 것이다.  

 * 이후 각 모델을 통한 결과를 시각화한다.  

 * 두 모델의 과정과 결과를 비교하여 블로그 토픽 모델링에 있어 어떤 것이 더 적합할지 알아본다.

<br>
<br>

## 수행방법
**데이터 수집**
 * BeautifulSoup 이용, 네이버 블로그 (약 130명, 4000포스팅)와 내 블로그(약 180 포스팅) 제목 및 본문 크롤링

**데이터 전처리**
 * Konlpy Okt 이용한 형태소 분석, 명사만 추출, 토큰화, TF-IDF, 모든 주제에서 등장할 수 있는 단어 임의적으로 불용어 처리

**주제분류기**
 * LDA, Kmeans

**평가**
 * LDA: Topic Coherence (0.62)
 * Kmeans: Average of Word2Vec Similarity (0.43)

<br>
<br>

## 과제 수행 결과
**내 블로그 주제 비율**
 * LDA: 맛집(71) / 육아&애완동물(35) / 뷰티(11) / 음악(10)
 * Kmeans: 맛집(52) / IT(21) / 여행(10) / 음악(8) / 뷰티(7)  

 * LDA와 Kmeans 모두 1순위 주제는 ‘맛집’이라는 동일한 결과가 나왔지만, 2순위부터는 상당히 다른 결과가 나왔다. 실제 나의 블로그는 Kmeans의 결과와 더 비슷하다. 

**실제 블로그 주제와의 비교**
 * LDA는 65.15%의 정답률을 보였다. 군집이 만들어지지 않은 DIY, Book, Animation 주제를 제외하면 73.50%의 정답률을 보인다.
 * KMeans는 처음 계획했던 18개 주제 모두 군집이 만들어졌으며, 정답률은 74.24%를 보인다.

**군집화 시간**
 * LDA: 약 5분 소요
 * K-means: 약 15분 소요  

 * 하지만 LDA는 단어 수를 1200개로 고정해둔 상태이며, K-means는 별도의 설정 없이 30000개를 사용한 상태이기 때문에 단순 비교는 어렵다.

**시각화자료**
 
file:///C:/Users/Hyennnnnnnnnnnn/Documents/GitHub/BlogTopic/vis/LDA.html
![LDA](https://user-images.githubusercontent.com/64299475/86433234-1fa45080-bd35-11ea-89c9-b2a3daffc87d.PNG)

file:///C:/Users/Hyennnnnnnnnnnn/Documents/GitHub/BlogTopic/vis/kmeans.html#topic=0&lambda=1&term=
![Kmeans](https://user-images.githubusercontent.com/64299475/86433246-2763f500-bd35-11ea-8b56-95af66d74bb8.PNG)
![Kmeans](https://user-images.githubusercontent.com/64299475/86433261-321e8a00-bd35-11ea-8a91-24a30b833b53.PNG)

 <br>
 <br>

## 결론
**LDA**
 * 장점 및 추천 용도: 블로그나 트위터 문서처럼 한 문서당 주제가 여러 개일 때 사용하기 적합하다. 또한, 분석 비용이 많이 들기 때문에 소량의 문서, 적은 주제를 군집화할 때 적합해 보인다.  

 * Kmeans 에 비해 other(기타) 군집을 처리하기가 어렵기 때문에 최대한 주제가 확실하고 깔끔한 Data를 사용할 때 사용하기 좋다. 

**Kmeans**
 * 장점 및 추천 용도: 한 문서당 하나의 주제만 담을 수 있다고 가정된 모델이기 때문에 신문기사처럼 주제가 하나인 경우에 사용하기 적합하다. 또한, Input data 대비 분석이 빠르게 이루어지기 때문에 다량의 문서 / 많은 주제를 군집화할 때 적합하다고 생각한다.  
 
 * LDA와 반대로 other(기타) 군집을 선별하고 처리하기가 편리하다.  

<br>

<br>

## schedule
**3월** 
 * 주제 선정 (수필 쓰는 AI → 주제 변경) ✔

**4월**
 * 데이터 크롤링 (타 블로거 포스팅 포함) ✔ 
 * 데이터 점검 및 정제 ✔ 
 * 데이터 토큰화 ✔ 
 * 데이터 전처리 ✔

**5월**
 * Kmeans 모델링 (Decision Tree  → 모델 변경) ✔ 
 * LDA 모델링 ✔

**6월**
 * 모델 평가 및 수정 ✔
 * 블로그 주제 선정 ✔
 * 모델 비교 및 분석 ✔
