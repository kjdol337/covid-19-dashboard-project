# COVID-19 Comprehensive Data Analysis Dashboard
보건복지부 코로나19 감염현황 공공데이터 API를 활용하여 확진자 데이터를 수집하고, 이를 바탕으로 연령대별 확진율, 이동량 추이, 치명률 등을 다각도로 분석하는 종합 데이터 분석 웹 대시보드 프로젝트입니다.

## 주요 기능 (Key Features)
자동화된 데이터 파이프라인 구축
보건복지부 코로나19 공공데이터 API 연동 및 XML 데이터 파싱
수집된 원시 데이터를 R을 통해 전처리하고 로컬 MySQL 데이터베이스(my_covid19)에 자동 적재
다차원 데이터 시각화 및 대시보드 생성
데이터베이스와 연동하여 RMarkdown 기반의 정적 웹 대시보드(HTML) 생성
연령대별 누적 확진율, 인구 이동량과 감염의 상관관계, 연령별 치명률 등 심층적인 시각화(ggplot2) 및 통계 분석 제공

## 기술 스택 (Tech Stack)
Language: R
Database: MySQL
Data Collection: Public Data API (공공데이터포털)
Libraries (R): httr, XML, jsonlite, dplyr, DBI, odbc, ggplot2, rmarkdown, knitr

## 프로젝트 파일 구조
API데이터 불러오기 및 MySQL에 저장하는 코드.R : 공공 API 데이터를 호출하고 MySQL DB에 테이블 형태로 적재하는 스크립트
dashboard.txt (RMarkdown) : 저장된 데이터를 불러와 통계 분석 및 그래프를 그리고 HTML 문서로 변환하기 위한 마크다운 코드
covid19.html : RMarkdown 파일이 빌드(Knit)되어 최종적으로 생성된 웹 대시보드 결과물

## 사전 준비사항 (Prerequisites)
MySQL 서버 설치 및 설정
로컬 환경에 MySQL 설치 (Port: 3306)
my_covid19 데이터베이스 생성
MySQL ODBC 8.0 Unicode Driver 설치 필요
공공데이터포털 API Key
보건복지부_코로나19 감염현황 총괄 통계 API 서비스 키 발급 및 코드 내 반영 필요

## 실행방법
1. 데이터 수집 및 DB 저장
먼저 R 환경(RStudio 등)에서 데이터를 수집하고 데이터베이스에 저장하는 스크립트를 실행합니다.

```bash
# API데이터 불러오기 및 MySQL에 저장하는 코드.R 파일을 엽니다.
# 코드 내의 API Key(my_key)와 MySQL 접속 정보(UID, PWD)를 본인의 환경에 맞게 수정합니다.
# 스크립트 전체를 실행하여 'Connection Successful!' 메시지와 함께 데이터가 DB에 정상 적재되는지 확인합니다.
```

2. 대시보드 생성 (HTML)
데이터 적재가 완료되면, RMarkdown 코드를 실행하여 분석 결과가 담긴 웹 문서를 생성합니다.

```bash
# dashboard.txt 파일의 확장자를 .Rmd (예: dashboard.Rmd)로 변경합니다.
# RStudio에서 해당 파일을 열고 상단의 'Knit' 버튼(Knit to HTML)을 클릭합니다.
# 분석과 시각화가 완료되면 최종 결과물인 HTML 웹 대시보드가 생성됩니다.
```


