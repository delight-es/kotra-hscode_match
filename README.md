# [대한무역투자진흥공사 (KOTRA)] HSCODE 매칭 서비스
🏅 **KOTRA 이사장상 수상** <br>
> 🕒 `2023.10.01` - `11.16` <미래내일일경험><br>
> 📖 프로젝트 기획  |  데이터 수집/정제 |  예측 모델 개발 <br>
> 💻 서비스 : (준비중)
<br>
<br>

![코트라](https://github.com/user-attachments/assets/3d36977e-8fa5-41c1-83ce-cc8f8e5a3065)
<br>


> #### ❓WHY
- 기획배경 : 수출주도형 경제성장의 기반이 되는 지속적인 **국내 수출 경쟁력 강화시스템** 필요
  - HS CODE : 국제적으로 사용하는 상품 분류 체계 (국제공통 6단위)
    - **관세율, 상품품목, 무역통계량**을 위한 지표로 활용 가능
    - HSK CODE : HS CODE에서 확장되어 우리나라에서 사용되는 분류체계 (한국 10단위)
- 기획의도 : **국제 HS CODE**와 상품 설명으로 **국내 HSK CODE를 매칭**해 해외와 국내기업을 서로 연결
  - 수출 다변화와 경쟁력의 지속적인 강화
<br>
<br>

> #### ❓HOW
> **개발 주요사항**
  - 데이터셋 수집
    - 관세청 - 속견표 설명서 크롤링 (HS CODE 10단위 각 계층별 정보)
    - TRADLINX - 거래품 데이터 140만건 크롤링 (HS CODE 10단위, 상품 설명)
    - Ciel - 테스트 데이터 1590건 크롤링 (HS CODE 10단위, 상품 설명)
    - 국내외 HS/K 및 상품설명 데이터 (제공)
  - 데이터셋 구축
    - 상품설명 정제 - 특수기호, 타언어, 불용어 제거, 어간통일, 오타 검수
    - HS CODE 정제 - 노이즈 데이터 제거 //
  - 주요 키워드 추출
    - 직업종 단어사전(3000개) 제작, 정규표현식 활용 기법 확립
  - 모델링
    - 직업종 예측 모델(Bert-Kor-Base) Fine-Tuning
    - 판정서 요약 BERT 모델 Fine-Tuning
  - 유사도 알고리즘 개발
     - 사용자 입력과 판정서 키워드 간 TF-IDF + Bert Embedding 유사점수 계산 기술 개발
  - 웹 애플리케이션 구축
<br>

> **담당**<br>

  - 데이터셋 수집(업무상 질병 판정서 공개 데이터 크롤링),<br>
  데이터셋 정제(판정서 정제, 복합상병 분리),<br>
  주요 키워드 추출 기술 (직업종 단어사전 제작, 정규표현식 기법 확립),<br>
  웹 애플리케이션 개발
<br>

> **개발 환경** :
  - PYTHON 3.9(언어), Mecab(단어사전), Stream-lit(웹), SVN(형상관리)
    - Streamlit (version): 1.37.1
    - pandas (version): 2.0.0
    - numpy (version): 1.24.2
    - torch (version): 1.12.1+cu113
    - transformers (version): 4.27.4
    - scikit-learn (version): 1.2.2
    - matplotlib (version): 3.7.1
<br>
<br>

> #### ❓TEST
> **실무자 검증**
- 정확도 : 80%
