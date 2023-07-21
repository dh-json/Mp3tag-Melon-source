# 설명
[Melon](https://www.melon.com/) html 파싱을 활용한 사용자 스크립트입니다.

API를 활용하지 않은 관계로, html 소스코드가 수정되는 경우 사용이 어려울 수 있습니다.

# 설치
사용에 앞서 [Mp3tag](https://www.mp3tag.de/en/download.html)가 필요합니다.

### 경로
```
%appdata%\Mp3tag\data\sources\
```
### 최신버전 링크
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/dh-json/Mp3tag-Melon-source)](https://github.com/dh-json/Mp3tag-Melon-source/releases)

# 사용

## 앨범 검색
5가지 옵션을 활용하여 검색이 가능합니다.
* 앨범 이름, 앨범 아티스트로 검색
* 앨범 이름으로 검색(정확도/인기/최신/가나다순)

### 적용 가능 태그
* 앨범 아트
* 앨범 이름
* 앨범 아티스트
* 발매사
* 발매년도
* 디스크 번호
* 곡 이름
* 곡 아티스트
* 트랙 번호

동일한 앨범의 수록곡들을 동시에 수정가능합니다.

## 곡 검색
5가지 옵션을 활용하여 검색이 가능합니다.
* 곡 이름, 곡 아티스트로 검색
* 곡 이름으로 검색(정확도/인기/최신/가나다순)

### 적용 가능 태그
* 앨범 아트
* 앨범 이름
* 곡 이름
* 곡 아티스트
* 장르
* 발매년도
* 비동기 가사
* 작곡가
* 작사가

# 발매년도 대신 발매일 사용

### 파일 목록
`Melon#1. 앨범, 앨범아티스트명으로 앨범 검색.src`,`Melon#2. 앨범명으로 앨범 검색(정확도순).src`, `Melon#3. 앨범명으로 앨범 검색(인기순).src`, `Melon#4. 앨범명으로 앨범 검색(최신순).src`, `Melon#5. 앨범명으로 앨범 검색(가나다순).src`,  `Melon#6. 곡, 아티스트명으로 곡 검색.src`,  `Melon#7. 곡명으로 곡 검색(정확도순).src`,  `Melon#8. 곡명으로 곡 검색(인기순).src`, `Melon#9. 곡명으로 곡 검색(최신순).src`, `Melon#10. 곡명으로 곡 검색(가나다순).src`

### 찾을 항목
```
# Year
RegexpReplace "<[^>]+>" ""
SayUntil "."
# Date
#RegexpReplace "[^0-9]" ""
#SayRest
```

### 수정 후
```
# Year
#RegexpReplace "<[^>]+>" ""
#SayUntil "."
# Date
RegexpReplace "[^0-9]" ""
SayRest
```
멜론상의 정보가 2022.01.01로 되어있는 경우 `20220101`로 출력됩니다.

# 참고 사항
[Tag Sources - Mp3tag Documentation](https://docs.mp3tag.de/tag-sources/development/)

[Mp3tag용 멜론 태그 검색 스크립트](https://blog.naver.com/hosang46/221126952898)
