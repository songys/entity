# Entity
# 구축과정  

 1. 한글형태소 사전 NIADic에 사람과 장소 등의 정보를 참조했음      
https://kbig.kr/portal/kbig/knowledge/files/bigdata_report.page?bltnNo=10000000016451

2. 세종 2007과 공개 말뭉치를 파싱해서 2차 사전 구축              

3. 1과 2를 수작업으로 검수하여 최종 사전 구축         

https://github.com/kmounlp/NER 등의 정보를 추가 보강하면 좀 더 완결된 사전이 가능할 것으로 여겨짐



# 저작권 표기 

크리에이티브 커먼즈 저작자표시-  동일조건변경허락 2.0 국제 라이선스(CC BY-SA)​
(https://creativecommons.org/licenses/by-sa/3.0/deed.ko)

-----------------------------------------------------------------------------------
참고

## 개체명 인식 정의
개체명 인식(Named Entity Recognition, 이하 NER)은 자연어처리의 하위 분야로  특정한 이름들에  태깅 값을 주어 그 정보를 가시화하는 작업이다. 개체명 인식이 어려운 이유는 새로운 개체명이 계속 만들어지고 있어서 완성된 사전을 가지기 어렵기 때문이다. 또한  같은 단어라도 사용되는 상황에 따라 다른 의미로 해석되는 중의성이 발생할 수 있다.                     

## Open domain 또는 Closed domain
도메인을 구분하는 이유 역시 쉽게 중의성을 해소하기 위해서다.  가령, '여자 친구'의 '여름여름해'라는 곡이 있다면 사전적 의미로는 올바른 정보를 추출하기 어려울 수도 있다. 이를 대중가요라는 Closed domain에 가수와 곡명으로 분류하여 개체로 태깅해 주면 빠르게 정보에 접근할 수 있을 것이다.                
또한 병원 차트, 법원 녹취록 등은 특정한 목적을 위해 데이터를 별도로 구축하기 때문에 댜수의 전문 용어들이 특정한 의미로 쓰이게 된다. 아스피린과 같이 일반적으로 많이 쓰이는 용어도 있지만 대체로는 특정한 용어들을 개체로 태깅해 주는 것이 데이터 구축시 주요 작업이 것이다. 이 때 결과물은 개체명와 범주로 이루어진 사전 또는 태깅된 문서가 된다.               

## 역사
1. 1995년 는 년1995 , MUC-6(the Sixth Message Understanding Conference)
(https://cs.nyu.edu/faculty/grishman/muc6.html) 에서 시작되었는데 당시 분류의 기준은 5 가지 개체명 즉, 인명(PS), 기관명(OG), 장소(LC), 날짜(DT), 시간(TI) 분류 및 BIO(Begin, in, out) tag 를 붙이는 과제였다.                  

2. 이후 CoNLL(2003) shared task에서 Language-Independent Named Entity Recognition 과제가 이루어졌다.       

3. 국내에서는 2016년과 2017년 국어정보처리 시스템 경진대회에서도 개체명 인식이 저정 분야였다. (https://ithub.korean.go.kr/user/contest/contestIntroView.do)     

4. Naver NLP Challenge 2018에서도 개채명 인식이 주요 과제중 하나였고 1위를 한 State_Of_The_Art팀은 F1 score가	90.4219로 성능 개선을 보였다.
(http://air.changwon.ac.kr/?page_id=10)          


## 영어 NER 성능 
영어를 위한 최신 NER 시스템은 인간에 근접한 성능을 낸다. 이를테면 MUC-7에 진입한 최고의 시스템은 F-measure 기준 93.39%을 받았으며 인간 주석자는 97.60%과 96.95%점을 받았다(https://ko.wikipedia.org/wiki/%EA%B0%9C%EC%B2%B4%EB%AA%85_%EC%9D%B8%EC%8B%9D)


## 사용 
영어의 경우 nltk 패키지를 통해 다음의 4단계를 거치면 입력 문장에서 사람, 조직, 장소 이름을 추출할 수 있다. 
* 문장분리 nltk.sent_tokenize
* 어절분리 nltk.word_tokenize
* 형태소 태깅 nltk.pos_tag
* 개체명 인식 nltk.chunk.ne_chunk

 (https://towardsdatascience.com/named-entity-recognition-with-nltk-and-spacy-8c4a7d88e7da)





