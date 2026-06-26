# 서원등록 시맨틱 데이터

이 저장소는 『서원등록』 정책·청원 문건 분석을 위해 편찬한 연구용 시맨틱 데이터를 공개하기 위한 저장소입니다. 데이터는 RDF/Turtle 원본과 CSV 변환 파일로 구성되어 있으며, 연구 결과의 검증과 재현을 목적으로 합니다.

## 데이터 파일

- `datasets/seowondeungrok.ttl` : RDF/Turtle 원본 데이터입니다.
- `datasets/nodes.csv` : 문건·사건·행위·인물·서원·지역·청원결과 등 개체 목록입니다.
- `datasets/links.csv` : 주요 관계 목록입니다. 역방향 중복 관계 일부를 제외하여 분석과 확인이 쉽도록 정리한 파일입니다.
- `datasets/links_all.csv` : TTL에 포함된 모든 ObjectProperty 관계를 CSV로 변환한 전체 관계 파일입니다.
- `datasets/node_texts.csv` : 문건 원문과 번역문을 분리한 텍스트 파일입니다.
- `ontology/seowondeungrok_ontology_design.ttl` : 『서원등록』 온톨로지 설계 파일
- `analysis/queries/` : Apache Jena Fuseki에서 실행한 SPARQL 질의문을 질의별 CSV 파일로 정리한 폴더입니다.
- `analysis/results/` : 각 SPARQL 질의의 실행 결과를 질의별 CSV 파일로 정리한 폴더입니다.
- `analysis/manifest.csv` : 질의 파일과 결과 파일의 대응 관계를 정리한 목록입니다.  
 

## 활용 방법

- RDF 기반 질의: Apache Jena Fuseki 등에 `seowondeungrok.ttl`을 로드한 뒤 SPARQL 질의를 실행할 수 있습니다.
- 표 형식 검토: `nodes.csv`, `links.csv`, `links_all.csv`를 엑셀, 구글 스프레드시트, Python 등에서 열어 개체와 관계를 확인할 수 있습니다.
- 문건 원문·번역문 확인: `node_texts.csv`를 사용하면 문건 단위의 원문과 번역문을 별도로 확인할 수 있습니다.
