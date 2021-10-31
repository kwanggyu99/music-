# music


## 프로젝트 계획 이유
자신이 찾고 싶어하는 노래의 제목을 알려주는 아이폰의 샤잠 기능이 개인적으로 매우 유용했다.
그런데 음악 듣는 것을 즐기는 사람들은 자신의 취향에 맞는 더 많은 노래를 찾는데 시간을 많이 사용한다.
그래서 샤잠 기능에 음악적 분석을 통한 유사한 노래 추천과 샤잠 자체 기능을 더 효율성 있게 만들기 위해 시작하게 되었다.

## music project 기능 설명 
자신의 원하는 노래의 제목을 찾아주는 샤잠 기능은 오디오 핑거프린팅 기술이 들어간다. 빠른 데이터 처리를 위해 샤잠은 음악 분석 그래프에서 3가지 종목을 데이터 베이스로 보내는데 이 그래프와 다른 알고리즘의 분석을 함께 사용하여 노래 장르 구분 및 유사한 노래 추천을 사용자에게 해준다.


## shazam 
깃허브 오픈소스로 현재 개발 중 이다.


[1](https://github.com/steven2358/Shazam-Matlab)  
2003년 샤잠 개발 당시 MATLAB언어로 짜진 프로그램  


[2](https://github.com/shazam)  
현재 샤잠 관련 깃허브

## 스펙트럼 활용
<img width="221" alt="5" src="https://user-images.githubusercontent.com/91644564/139565422-fa0546c7-b43d-432a-b378-550c444a2658.png">

## 활용할 알고리즘
오픈 소스 샤잠
 >python Librosa : 음악 분석, 유사도 활용을 통한 추천
   
## 음악 분석 알고리즘
python Librosa 라이브러리 활용
``` 
  import librosa
  y , sr = librosa.load('데이터 주소') 
  print(len(y))
  print('Sampling rate (Hz): %d' %sr)
  print('Audio length (seconds): %.2f' % (len(y) / sr)) 
 ``` 
오디오 파일 로드 및 음파의 길이 확인 

## 음악 유사 장르 추천
``` 
from sklearn.metrics.pairwise import cosine_similarity
similarity = cosine_similarity(df_30)   

sim_df = pd.DataFrame(similarity, index=labels.index, columns=labels.index)

sim_df.head()
 ``` 
가지고 있는 데이터 베이스에서 현재 음악과 유사도 높은 것을 추천

