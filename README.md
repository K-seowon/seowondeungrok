# 서원등록 시맨틱 데이터

이 저장소는 『서원등록』 정책·청원 문건 분석을 위해 편찬한 연구용 시맨틱 데이터를 공개하기 위한 저장소입니다. 데이터는 RDF/Turtle 원본과 CSV 변환 파일로 구성되어 있으며, 연구 결과의 검증과 재현을 목적으로 합니다.

## 데이터 파일

- `datasets/seowondeungrok.ttl` : RDF/Turtle 원본 데이터입니다.
- `datasets/nodes.csv` : 문건·사건·행위·인물·서원·지역·청원결과 등 개체 목록입니다.
- `datasets/links.csv` : 주요 관계 목록입니다. 역방향 중복 관계 일부를 제외하여 분석과 확인이 쉽도록 정리한 파일입니다.
- `datasets/links_all.csv` : TTL에 포함된 모든 ObjectProperty 관계를 CSV로 변환한 전체 관계 파일입니다.
- `datasets/node_texts.csv` : 문건 원문과 번역문을 분리한 텍스트 파일입니다.


## nodes.csv 주요 컬럼

| 컬럼 | 설명 |
|---|---|
| `id` | 개체 식별자 |
| `label` | 개체 라벨 |
| `type` | 개체 유형 ID |
| `type_label` | 개체 유형 한글명 |
| `uri` | RDF URI |
| `gregorianDate`, `dateLabel`, `reignMonarch`, `reignYearLabel` | 문건 날짜 관련 속성 |
| `hanjaName`, `birthYear`, `deathYear`, `lifeSpan` | 인물 관련 속성 |
| `locationLabel`, `externalURL` | 서원·지역 등 참조 속성 |

## links.csv / links_all.csv 주요 컬럼

| 컬럼 | 설명 |
|---|---|
| `source` | 소스 개체 ID |
| `target` | 타겟 개체 ID |
| `relation` | 관계 유형 ID |
| `relation_label` | 관계 유형 한글명 |
| `source_label`, `target_label` | 소스·타겟 개체 라벨 |
| `source_type`, `target_type` | 소스·타겟 개체 유형 |
| `relation_uri` | RDF 관계 URI |

## 활용 방법

- RDF 기반 질의: Apache Jena Fuseki 등에 `seowondeungrok.ttl`을 로드한 뒤 SPARQL 질의를 실행할 수 있습니다.
- 표 형식 검토: `nodes.csv`, `links.csv`, `links_all.csv`를 엑셀, 구글 스프레드시트, Python 등에서 열어 개체와 관계를 확인할 수 있습니다.
- 문건 원문·번역문 확인: `node_texts.csv`를 사용하면 문건 단위의 원문과 번역문을 별도로 확인할 수 있습니다.
