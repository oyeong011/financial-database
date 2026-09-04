# 금융 데이터베이스 (Financial Database)

자동 수집된 금융 재무제표 데이터입니다.

## 수집 현황 (최종 업데이트: 2026-09-05 03:08)

| 시장 | 기업 수 | 데이터 건수 |
|------|---------|------------|
| 미국 (NYSE+NASDAQ) | 4,160개 | 296,350건 |
| 한국 (코스피+코스닥) | 2,730개 | 191,084건 |
| **합계** | **6,890개** | **487,434건** |

## 데이터 구조

### SEC (미국)
- `data/sec/financial_data.csv` - 재무 데이터 (매출/이익/자산/부채 등 30개 항목)
- `data/sec/companies.csv` - 기업 목록

### DART (한국)
- `data/dart/financial_data.csv` - 재무 데이터 (매출/영업이익/당기순이익 등)
- `data/dart/companies.csv` - 기업 목록

## 수집 항목

**손익계산서**: 매출액, 매출원가, 매출총이익, 영업이익, 당기순이익, EPS
**재무상태표**: 총자산, 유동자산, 현금, 총부채, 자본총계
**현금흐름표**: 영업/투자/재무활동 현금흐름, CAPEX, 배당금

## 데이터 출처
- 미국: [SEC EDGAR XBRL API](https://data.sec.gov) (무료, 공개)
- 한국: [OpenDART API](https://opendart.fss.or.kr) (금융감독원 전자공시시스템)

## 이 데이터를 쓰는 프로젝트

### [MDFeed — 실시간 마켓데이터 FEED 플랫폼](https://github.com/oyeong011/market-feed-platform)

거래소 실시간 시세를 수집·정규화해 TCP/WebSocket/REST 세 프로토콜로 배포하는 피드 서비스입니다.
이 저장소의 재무제표를 **참조 데이터 평면**으로 연결해, 실시간 시세(밀리초 단위)와
분기 재무데이터(영속)를 한 플랫폼에서 다룹니다. 조인 키는 `DART stock_code` = `KIS 종목코드` 입니다.

- 데모 대시보드: <https://oyeong011.github.io/market-feed-platform/>
- 팩터 스크리닝: 이 데이터로 영업이익률·ROE·매출성장·FCF·부채비율을 계산해 순위화

---
*자동 수집 시스템으로 매일 업데이트됩니다.*
