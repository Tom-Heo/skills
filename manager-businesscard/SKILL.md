---
name: manager-businesscard
description: manager-businesscard/SKILL.md는 사용자 본인의 명함 및 받은 명함을 skills/registry-businesscard/SKILL.md에 기록하여 관리하는 SKILL이다. registry-businesscard/SKILL.md에 항목 추가, 수정, 제거가 필요한 상황에 사용한다. 사용자가 명함 사진을 전송한 상황에도 사용한다.
---
# manager-businesscard


## Table of Contents
- Foundation
    - Overview
    - Triggers
    - Usage
- Context
    - Purpose
    - Glossary
    - Philosophy
- Format
    - Format Token
    - Format Rules
    - Example
- Rules
    - Principles
    - Pitfalls
    - Edge Cases


## Foundation


### Overview
manager-businesscard/SKILL.md는 사용자 본인의 명함 및 받은 명함을 skills/registry-businesscard/SKILL.md에 기록하여 관리하는 SKILL이다.


### Triggers
- registry-businesscard/SKILL.md의 업데이트가 필요한 상황
- registry-businesscard/SKILL.md에 문제가 있는 상황
- registry-businesscard/SKILL.md에 항목 추가 혹은 제거가 필요한 상황
- 사용자가 registry-businesscard/SKILL.md의 수정을 요청하는 상황
- 사용자가 명함 사진을 전송한 상황


### Usage
1. skills/registry-businesscard/SKILL.md를 읽는다.
2. 부족한 정보를 확인하고 필요한 정보를 사용자에게 요청한다.
3. 업데이트할 내용을 작성하여 사용자에게 확인받는다.
4. skills/registry-businesscard/SKILL.md를 업데이트한다.
5. 업데이트한 내용을 사용자에게 보고한다.


## Context


### Purpose
사용자 본인의 명함 및 받은 명함을 skills/registry-businesscard/SKILL.md에 기록하여 관리한다.


### Glossary
- 명함: 하나의 명함. '#### {회사명} {이름} 명함'으로 표기.
- 명함집: 명함대장 안에서 동일 회사의 명함을 묶는 단위. '### {회사명} 명함집'으로 표기.
- 명함지갑: 사용자 본인의 모든 명함을 기록 및 관리하는 공간. '## 명함지갑'으로 표기. 명함집 없이 명함이 직접 나열된다.
- 명함대장: 사용자가 받은 모든 타인의 명함을 명함집 단위로 기록 및 관리하는 공간. '## 명함대장'으로 표기.
- registry-businesscard/SKILL.md: 명함지갑과 명함대장을 포함하는 전체 저장공간.


### Philosophy
- 좋은 것엔 견고함이 있다.
- 그 어떤 표현도 다른 표현으로 대체할 수 없다.
- 공들임은 값지다.
- 좋은 물음엔 맥락이 흐른다.
- 절제는 깊이를 만든다.
- 차분함이 정확함을 만든다.
- 적당한 것은 적절하지 않다.
- 정확하기에 아름답다.
- 일관성이 신뢰를 만든다.
- 그냥은 없다.


## Format


### Format Token
```markdown
# registry-businesscard
Last Updated on {MMMM(en)} {DD}, {YYYY}.


## 명함지갑
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


### {회사명1} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


### {회사명2} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


## 명함대장
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


### {회사명a} 명함집
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


#### {회사명a} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명a}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


#### {회사명a} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명a}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


### {회사명b} 명함집
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


#### {회사명b} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명b}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}


#### {회사명b} {이름} 명함
- Name*: {이름}
- Company Name*: {회사명b}
- Job Title: {직함 | '(비어 있음)'}
- Department: {부서명 | '(비어 있음)'}
- Mobile*: {휴대폰 번호}
- Email*: {이메일}
- Office Phone: {사무실 직통 번호 | '(비어 있음)'}
- Fax: {팩스 번호 | '(비어 있음)'}
- Office Address: {사무실 주소 | '(비어 있음)'}
- Website: {웹사이트 URL | '(비어 있음)'}
- SNS: {SNS ID (Platform) | '(비어 있음)'}
- QR Code: {QR코드 URL | '(비어 있음)'}
- Note: {맥락이나 추가 정보 | '(비어 있음)'}
- Created Date*: {YYYY-MM-DD}
- Updated Date*: {YYYY-MM-DD}
```


### Format Rules
- 정렬1: 명함지갑 → 명함대장
- 정렬2: 명함집 단위로 Created Date 오름차순.
- 정렬3: 명함 단위로 Created Date 오름차순
- 필수 인자: Name*, Company Name*, Mobile*, Email*, Created Date*, Updated Date*
- 헤더(##, ###, ####) 위로 빈 줄 2개. 그 외 빈 줄 없음
- 휴대폰 번호는 E.123 국제 표기법으로 표기. 그 외 표기법으로 표기되어 있어도 반드시 E.123 국제 표기법으로 변환하여 표기.
- 값이 없어도 필드 작성
- 값이 없어도 비우지 말고 '(비어 있음)'을 작은 따옴표 없이 작성
- SNS ID는 앞에 적절한 태그를 포함 및 추가하여 작성
- SNS 필드엔 반드시 Platform도 같이 작성
- 이름은 명함에 작성되어 있는 한글 및 영문 이름 모두 그대로 작성
- 문서 최상단에 Last Updated on {MMMM(en)} {DD}, {YYYY} 반드시 작성.
- 필수 인자는 반드시 필드명에 '*'를 작은 따옴표 없이 표기
- 회사명은 명함에 적힌 그대로 작성
- 섹션명에 명함지갑, 명함대장, 명함집, 명함은 생략 없이 작성


### Example
```markdown
# registry-businesscard
Last Updated on March 20, 2026.


## 명함지갑
- Created Date*: 2025-04-10
- Updated Date*: 2026-03-20


### 주식회사 제너러티브랩 허문영 명함
- Name*: 허문영
- Company Name*: 주식회사 제너러티브랩
- Job Title: 매니저
- Department: 신규개발2팀
- Mobile*: +82 10 2369 7428
- Email*: tom@generativelab.co.kr
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: 서울특별시 성북구 고려대로24길 32, 5층
- Website: (비어 있음)
- SNS: (비어 있음)
- QR Code: (비어 있음)
- Note: 현재는 사용하지 않는 명함
- Created Date*: 2025-04-10
- Updated Date*: 2025-09-29


### Bake 허문영 명함
- Name*: 허문영
- Company Name*: Bake
- Job Title: CTO
- Department: Engineering Team
- Mobile*: +82 10 2369 7428
- Email*: imtomheo@bake.com
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: (비어 있음)
- Website: https://www.bake.com
- SNS: @heoiv (Instagram)
- QR Code: (비어 있음)
- Note: 현재는 사용하지 않는 명함
- Created Date*: 2025-12-22
- Updated Date*: 2026-03-20


### Kkachi 허문영 명함
- Name*: 허문영
- Company Name*: Kkachi
- Job Title: 대표 이사
- Department: (비어 있음)
- Mobile*: +82 10 2369 7428
- Email*: imtomheo@kkachi.com
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: (비어 있음)
- Website: https://www.kkachi.com
- SNS: @heoiv (Instagram)
- QR Code: https://kkachi.com/team/tom
- Note: 사무실 주소 없음
- Created Date*: 2026-03-10
- Updated Date*: 2026-03-10


## 명함대장
- Created Date*: 2025-04-10
- Updated Date*: 2026-03-10


### 주식회사 제너러티브랩 명함집
- Created Date*: 2025-04-10
- Updated Date*: 2025-09-27


#### 주식회사 제너러티브랩 정영헌 명함
- Name*: 정영헌
- Company Name*: 주식회사 제너러티브랩
- Job Title: 매니저
- Department: 신규개발1팀
- Mobile*: +82 10 8515 6351
- Email*: eric@generativelab.co.kr
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: 서울특별시 성북구 고려대로24길 32, 5층
- Website: (비어 있음)
- SNS: (비어 있음)
- QR Code: (비어 있음)
- Note: (비어 있음)
- Created Date*: 2025-04-10
- Updated Date*: 2025-09-27


### (주)비바리퍼블리카 명함집
- Created Date*: 2025-05-23
- Updated Date*: 2025-05-23


#### (주)비바리퍼블리카 유송희 Songhee Yoo 명함
- Name*: 유송희 Songhee Yoo
- Company Name*: (주)비바리퍼블리카
- Job Title: (비어 있음)
- Department: Commerce Business Team
- Mobile*: +82 10 9646 5789
- Email*: songheeyoo@toss.im
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: 서울특별시 강남구 테헤란로 142, 아크 12층(역삼동, 아크플레이스)
- Website: (비어 있음)
- SNS: (비어 있음)
- QR Code: (비어 있음)
- Note: (비어 있음)
- Created Date*: 2025-05-23
- Updated Date*: 2025-05-23


#### (주)비바리퍼블리카 남정아 Jeongah Nam 명함
- Name*: 남정아 Jeongah Nam
- Company Name*: (주)비바리퍼블리카
- Job Title: (비어 있음)
- Department: Sales Operations
- Mobile*: +82 10 2859 2947
- Email*: jeongahnam@toss.im
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: 서울특별시 강남구 테헤란로 142, 아크 12층(역삼동, 아크플레이스)
- Website: (비어 있음)
- SNS: (비어 있음)
- QR Code: (비어 있음)
- Note: (비어 있음)
- Created Date*: 2025-05-23
- Updated Date*: 2025-05-23


### Kkachi 명함집
- Created Date*: 2026-03-10
- Updated Date*: 2026-03-10


#### Kkachi 최지우 명함
- Name*: 최지우
- Company Name*: Kkachi
- Job Title: 기획 팀장
- Department: 기획 팀
- Mobile*: +82 10 9584 1712
- Email*: jwchoi0712@kkachi.com
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: (비어 있음)
- Website: https://www.kkachi.com
- SNS: uzi_choi (Instagram)
- QR Code: https://kkachi.com/team/max
- Note: jwchoi0712@gmail.com
- Created Date*: 2026-03-10
- Updated Date*: 2026-03-10


#### Kkachi 민경민 명함
- Name*: 민경민
- Company Name*: kkachi
- Job Title: 개발 팀장
- Department: 개발 팀
- Mobile*: +82 10 7220 5917
- Email*: mkm0530@kkachi.com
- Office Phone: (비어 있음)
- Fax: (비어 있음)
- Office Address: (비어 있음)
- Website: https://www.kkachi.com
- SNS: @mgm136044 (Github)
- QR Code: https://kkachi.com/team/min
- Note: mkm0530@koreatech.ac.kr
- Created Date*: 2026-03-10
- Updated Date*: 2026-03-10
```


## Rules


### Principles
- registry-businesscard/SKILL.md는 유일한 원본이다. 명함 정보의 확인, 조회, 수정은 반드시 이 문서를 기준으로 한다.
- 읽기가 쓰기보다 먼저다. 기록하기 전에 반드시 registry-businesscard/SKILL.md의 현재 상태를 확인한다.
- 명함에 적힌 것이 기준이다. 추측, 보정, 축약 없이 원문 그대로 기록한다.
- 기록 전 확인은 생략할 수 없다. 명함 사진에서 읽은 정보든 사용자가 직접 전달한 정보든, 기록 전에 반드시 사용자 확인을 거친다.
- 구조가 데이터를 보호한다. 명함지갑과 명함대장의 분리, 명함집의 존재, 헤딩 계층은 임의로 변경하지 않는다.
- 변경은 위로 전파된다. 항목이 변경되면 해당 항목의 Updated Date와 상위 항목의 Updated Date, 문서 최상단 Last Updated on을 함께 갱신한다.
- 필드는 삭제하지 않는다. 값이 없어도 필드를 유지하고 (비어 있음)을 기록한다.
- 정렬은 기록의 일부다. 새 항목을 추가할 때 Created Date 오름차순 정렬이 유지되도록 올바른 위치에 삽입한다.
- 부족한 정보는 추측하지 않고 물어본다. 필수 인자가 누락되었거나 판독이 불확실하면 사용자에게 확인을 요청한다.
- 보고는 기록 및 관리의 마무리 단계다. 업데이트를 완료한 뒤 변경 내용을 사용자에게 반드시 안내한다.


### Pitfalls
- 주식회사를 (주)로 기록하는 실수. 회사명은 명함에 적힌 그대로를 기록해야 한다.
- 휴대폰 번호를 국내 표기(010-1234-5678)로 기록하는 실수. 반드시 E.123 국제 표기법(+82 10 1234 5678)으로 변환하여 기록해야 한다.
- 값이 없는 필드를 비워 두거나 삭제하는 실수. 값이 없어도 필드를 유지하고 (비어 있음)을 기록해야 한다.
- SNS ID만 기록하고 Platform을 누락하는 실수. @heoiv (Instagram)처럼 반드시 Platform을 함께 기록해야 한다.
- 명함지갑의 명함 헤딩에 회사명을 빠뜨리는 실수. ### {회사명} {이름} 명함 형식을 지켜야 한다.
- 명함대장에 명함집 없이 명함을 바로 나열하는 실수. 명함 한 장뿐이라도 반드시 명함집을 먼저 만들고 그 안에 기록해야 한다.
- 명함을 추가하거나 수정했음에도 상위 섹션(명함지갑, 명함대장, 명함집)의 Updated Date를 현재 날짜로 갱신하지 않는 실수. 하위 항목이 변경되면 상위 섹션의 Updated Date도 함께 갱신해야 한다.
- 문서 최상단의 Last Updated on 날짜를 갱신하지 않는 실수. 해당 날짜는 문서에 변경이 발생할 때마다 반드시 현재 날짜로 갱신해야 한다.
- 한글 이름만 기록하고 영문 이름을 누락하는 실수. 명함에 한글과 영문이 함께 적혀 있으면 모두 그대로 기록해야 한다.
- 명함집의 회사명과 그 안 명함의 회사명을 다르게 기록하는 실수. 명함집 헤딩과 해당 명함집 내부의 명함 헤딩은 같은 회사명을 포함해야 한다.
- 헤딩 위 빈 줄을 1개만 두거나 3개 이상 두는 실수. ##, ###, #### 헤딩 위로는 정확히 빈 줄 2개를 유지해야 한다.
- 섹션명에서 명함지갑, 명함대장, 명함집, 명함 등의 단위 명칭을 생략하는 실수. 매 항목마다 단위 명칭을 작성해야 한다.
- 명함을 추가하면서 기존 명함의 정렬 순서를 흐트러뜨리는 실수. 새 명함은 올바른 정렬로 정확한 위치에 삽입해야 한다.
- 명함 정보를 수정하면서 Created Date까지 현재 날짜로 바꾸는 실수. Created Date는 최초 등록일이므로 변경하면 안 된다.
- 명함지갑 안에 명함집 계층을 만드는 실수. 명함지갑은 명함이 직접 나열되는 구조이므로 명함집 없이 ### {회사명} {이름} 명함으로 바로 기록해야 한다.
- 명함대장에 사용자 본인의 명함을 기록하는 실수. 본인 명함은 명함지갑에, 타인의 명함은 명함대장에 기록해야 한다.
- E.123 국제 표기법에서 하이픈을 사용하는 실수. +82-10-1234-5678이 아니라 +82 10 1234 5678처럼 공백으로 구분해야 한다.
- 명함대장의 명함 헤딩을 ###으로 쓰는 실수. 명함대장의 명함은 명함집(###) 아래에 위치하므로 ####로 기록해야 한다.
- 명함 사진에서 읽은 정보를 사용자 확인 없이 바로 기록하는 실수. 오류 가능성이 있으므로 반드시 사용자에게 확인을 받은 뒤 기록해야 한다.
- 명함지갑의 정렬을 회사명 가나다순으로 하는 실수. 명함지갑도 명함 단위 Created Date 오름차순이 기준이다.


### Edge Cases
- 동일 인물이 서로 다른 회사의 명함을 가진 경우: 각각 별도의 명함으로 기록한다. 명함대장 내 각 회사의 명함집에 따로 기록한다.
- 명함의 직함이나 부서가 변경된 경우: 기존 명함을 수정하고 Updated Date를 갱신한다. 새 명함으로 추가하지 않는다.
- 명함에 회사명이 없는 경우(프리랜서, 개인): 사용자에게 회사명 대신 사용할 표기를 확인받는다. Company Name은 필수 인자이므로 비워 둘 수 없다.
- 명함에 휴대폰 번호 또는 이메일이 없는 경우: 필수 인자이므로 사용자에게 확인을 요청한다. 사용자도 모르면 기록을 보류하고 그 사유를 안내한다.
- 명함에 전화번호나 이메일이 여러 개인 경우: Mobile, Email 필드에는 각각 주요한 하나의 값만 기록하고, 나머지는 Note에 기록한다.
- 명함에 SNS가 여러 개인 경우: SNS 필드에 쉼표로 구분하여 모두 기록한다. 각 항목마다 Platform을 함께 표기한다.
- 이미 등록된 명함과 동일한 명함을 다시 받은 경우: 새로 추가하지 않는다. 정보가 달라진 부분이 있으면 기존 명함을 수정한다.
- 사용자 본인의 명함인지 타인의 명함인지 불분명한 경우: 사용자에게 명함지갑과 명함대장 중 어디에 기록할지 확인받는다.
- 명함의 전화번호가 한국 번호가 아닌 경우: 해당 국가의 국가 코드를 적용하여 E.123 국제 표기법으로 변환한다.
- 명함 사진의 해상도가 낮거나 정보가 일부만 판독 가능한 경우: 판독된 정보를 사용자에게 제시하고, 판독 불가 항목은 명시적으로 알린 뒤 사용자에게 보완을 요청한다.