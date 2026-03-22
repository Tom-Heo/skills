---
name: button-controller
description: 부족한 정보를 확인하고 싶은 상황, 사용자에게 제안을 하고 싶은 상황, 사용자가 버튼을 누른 상황, 되돌리기 어려운 작업을 실행하기 전 승인을 받고자 하는 상황, 사용자의 현재 상황이나 맥락을 확인하고 싶은 상황에 사용하는 버튼형 메시지 SKILL
---
# button-controller


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
    - Template
    - Format Rules
    - Example
- Rules
    - Principles
    - Pitfalls
    - Edge Cases


## Foundation


### Overview
Telegram 버튼형 메시지를 통해 사용자에게 확인, 제안, 작업을 전달하는 스킬. 상황과 맥락을 본문에 담고, 선택지를 버튼으로 제시하여 사용자의 의사결정을 돕는다.


### Triggers
- 부족한 정보를 확인하고 싶은 상황
- 사용자에게 제안을 하고 싶은 상황
- 사용자가 버튼을 누른 상황
- 되돌리기 어려운 작업을 실행하기 전 승인을 받고자 하는 상황
- 사용자의 현재 상황이나 맥락을 확인하고 싶은 상황


### Usage
1. 현재 상황 및 맥락을 파악하기 위해 필요한 파일들을 읽는다.
2. 사용자에게 확인, 제안, 작업할 내용이 있는지 검토한다.
3. [확인], [제안], [작업] 중 적절한 형태로 버튼형 메시지를 작성한다.
4. 완성된 버튼형 메시지를 사용자에게 전송한다.
5. 사용자가 버튼을 누르면 편집 기능(edit)을 사용하여 해당 메시지의 버튼을 제거하고 본문 하단에 버튼 내용을 추가한다.


## Context


### Purpose
Telegram이 지원하는 버튼형 메시지로 사용자에게 더 나은 UIUX를 제공한다.


### Glossary
- [확인]: 사용자의 상태나 의사 혹은 사실관계를 확인하는 메시지
- [제안]: 상황이나 맥락상 사용자에게 도움이 될 만한 행동을 선제적으로 제안하는 메시지
- [작업]: 시스템 내 실제 조작 및 작업의 실행을 제시하는 메시지


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


### Template
- 2 buttons Template
```bash
openclaw message send --channel telegram --target {target_id} --message "**{[확인] | [제안] | [작업]}**\n\n{상황 및 맥락}\n\n{질문}" --buttons '[
    [
      {
        "text": "{버튼명1}",
        "callback_data": "{button1_action_key}",
        "style": "primary | success | danger"
      },
      {
        "text": "{버튼명2}",
        "callback_data": "{button2_action_key}",
        "style": "primary | success | danger"
      }
    ]
  ]'
```

- 3 buttons Template
```bash
openclaw message send --channel telegram --target {target_id} --message "**{[확인] | [제안] | [작업]}**\n\n{상황 및 맥락}\n\n{질문}" --buttons '[
    [
      {
        "text": "{버튼명1}",
        "callback_data": "{button1_action_key}",
        "style": "primary | success | danger"
      },
      {
        "text": "{버튼명2}",
        "callback_data": "{button2_action_key}",
        "style": "primary | success | danger"
      },
      {
        "text": "{버튼명3}",
        "callback_data": "{button3_action_key}",
        "style": "primary | success | danger"
      }
    ]
  ]'
```

- 4 buttons Template
```bash
openclaw message send --channel telegram --target {target_id} --message "**{[확인] | [제안] | [작업]}**\n\n{상황 및 맥락}\n\n{질문}" --buttons '[
    [
      {
        "text": "{버튼명1}",
        "callback_data": "{button1_action_key}",
        "style": "primary | success | danger"
      },
      {
        "text": "{버튼명2}",
        "callback_data": "{button2_action_key}",
        "style": "primary | success | danger"
      }
    ],
    [
      {
        "text": "{버튼명3}",
        "callback_data": "{button3_action_key}",
        "style": "primary | success | danger"
      },
      {
        "text": "{버튼명4}",
        "callback_data": "{button4_action_key}",
        "style": "primary | success | danger"
      }
    ]
  ]'
```

- 2 or 3 buttons edit Template
```bash
openclaw message edit --channel telegram --target {target_id} --message-id {message_id} --message "**{[확인] | [제안] | [작업]}**\n\n{상황 및 맥락}\n\n{질문}\n\n\n**{선택한 버튼의 버튼명}**    ~~{선택하지 않은 버튼의 버튼명}~~    ~~{선택하지 않은 버튼의 버튼명}~~"
```

- 4 buttons edit Template
```bash
openclaw message edit --channel telegram --target {target_id} --message-id {message_id} --message "**{[확인] | [제안] | [작업]}**\n\n{상황 및 맥락}\n\n{질문}\n\n\n**{선택한 버튼의 버튼명}**    ~~{선택하지 않은 버튼의 버튼명}~~\n~~{선택하지 않은 버튼의 버튼명}~~    ~~{선택하지 않은 버튼의 버튼명}~~"
```


### Format Rules
- 헤더는 **[확인]**, **[제안]**, **[작업]** 중 하나
- 헤더와 본문 사이에 \n\n을 삽입
- 상황 및 맥락과 질문 사이에 \n\n을 삽입
- edit 시 질문과 버튼 내용 사이에 \n\n\n을 삽입
- edit 시 버튼 내용의 버튼 사이에 띄어쓰기 네 번 삽입
- 어떤 버튼이 눌렸든 간에 edit 시 버튼의 순서는 바꾸지 않고 유지
- 버튼 3개까지는 1행, 버튼 4개는 2행 × 2열
- 버튼은 2개부터 4개까지만 생성 가능
- style에서 success는 긍정, 수락, 실행
- style에서 danger는 파기, 삭제, 불참 등 되돌리기 어려운 선택
- style에서 primary는 중립
- 일정명, 과제명 등 고유 대상은 작은따옴표로 감싸기
- 질문은 한 문장, 반드시 물음표로 끝남
- edit 시 사용자가 클릭한 버튼은 볼드 처리
- edit 시 사용자가 클릭하지 않은 버튼은 취소선 처리



### Example
```bash
openclaw message send --channel telegram --target 8666564104 --message "**[확인]**\n\n현재 시각 오전 9시 39분입니다.\n잠시 후 오전 10시에 ‘기획 회의’가 시작됩니다.\n\n예정대로 참석하시나요?" --buttons '[
    [
      { "text": "참석", "callback_data": "button_attend", "style": "success" },
      { "text": "불참", "callback_data": "button_absent", "style": "danger" },
      { "text": "기타", "callback_data": "button_other", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 8666564104 --message "**[제안]**\n\n현재 시각 오전 9시 39분입니다.\n잠시 후 오전 10시에 ‘기획 회의’가 시작됩니다.\n\n회의 자료 검토를 도와드릴까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 8666564104 --message "**[작업]**\n\n현재 시각 오전 9시 39분입니다.\n잠시 후 오전 10시에 ‘기획 회의’가 시작됩니다.\n\n11분 후인 오전 9시 50분에 알림을 추가해 드릴까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message edit --channel telegram --target 8666564104 --message-id 6 --message "**[확인]**\n\n현재 시각 오전 9시 39분입니다.\n잠시 후 오전 10시에 ‘기획 회의’가 시작됩니다.\n\n예정대로 참석하시나요?\n\n\n**참석**    ~~불참~~    ~~기타~~"
```

```bash
openclaw message send --channel telegram --target 491837265 --message "**[확인]**\n\n토요일 오후부터 서울 지역에 강수 예보가 있습니다.\n‘신사 가로수길 데이트’에 차질이 생길 수 있습니다.\n\n일정을 예정대로 진행하시나요?" --buttons '[
    [
      { "text": "진행", "callback_data": "button_proceed", "style": "success" },
      { "text": "취소", "callback_data": "button_cancel", "style": "danger" },
      { "text": "조정", "callback_data": "button_adjust", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 491837265 --message "**[제안]**\n\n토요일 오후부터 서울 지역에 강수 예보가 있습니다.\n‘신사 가로수길 데이트’에 차질이 생길 수 있습니다.\n\n근처의 다른 데이트 장소를 검색해 드릴까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 491837265 --message "**[작업]**\n\n토요일 오후부터 서울 지역에 강수 예보가 있습니다.\n‘신사 가로수길 데이트’에 차질이 생길 수 있습니다.\n\n기상 예보가 바뀔 수 있으니 데이트 전 날에 해당 내용을 다시 알려드릴까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message edit --channel telegram --target 491837265 --message-id 34 --message "**[제안]**\n\n토요일 오후부터 서울 지역에 강수 예보가 있습니다.\n‘신사 가로수길 데이트’에 차질이 생길 수 있습니다.\n\n근처의 다른 데이트 장소를 검색해 드릴까요?\n\n\n~~예~~    **아니오**"
```

```bash
openclaw message send --channel telegram --target 5123847690 --message "**[확인]**\n\n내일 오후 5시에 ‘기초통계학 과제’가 마감됩니다.\n마감 기한까지 과제 수행 및 제출 일정이 없는 것으로 확인됩니다.\n\n과제를 이미 제출하셨나요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" },
      { "text": "기타", "callback_data": "button_other", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 5123847690 --message "**[제안]**\n\n내일 오후 5시에 ‘기초통계학 과제’가 마감됩니다.\n마감 기한까지 과제 수행 및 제출 일정이 없는 것으로 확인됩니다.\n\n오늘 저녁 9시에 ’기초통계학 과제 수행 및 제출‘ 일정을 추가할까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 5123847690 --message "**[작업]**\n\n내일 오후 5시에 ‘기초통계학 과제’가 마감됩니다.\n마감 기한까지 과제 수행 및 제출 일정이 없는 것으로 확인됩니다.\n\n캘린더 내 해당 할 일의 비고란에 ‘미제출’ 상태를 기록할까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message edit --channel telegram --target 5123847690 --message-id 2 --message "**[확인]**\n\n내일 오후 5시에 ‘기초통계학 과제’가 마감됩니다.\n마감 기한까지 과제 수행 및 제출 일정이 없는 것으로 확인됩니다.\n\n과제를 이미 제출하셨나요?\n\n\n~~예~~    **아니오**    ~~기타~~"
```

```bash
openclaw message send --channel telegram --target 3346719820 --message "**[확인]**\n\n‘조형준 교수님 면담’ 일정 추가를 내일 오전 11시로 요청하셨습니다.\n해당 시간은 기존 루틴인 ‘통계수학’의 강의 시간(09:00-11:45)과 겹칩니다.\n\n이대로 일정을 추가할까요?" --buttons '[
    [
      { "text": "추가", "callback_data": "button_add", "style": "success" },
      { "text": "보류", "callback_data": "button_hold", "style": "primary" },
      { "text": "취소", "callback_data": "button_cancel", "style": "danger" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 3346719820 --message "**[제안]**\n\n‘조형준 교수님 면담’ 일정 추가를 내일 오전 11시로 요청하셨습니다.\n해당 시간은 기존 루틴인 ‘통계수학’의 강의 시간(09:00-11:45)과 겹칩니다.\n\n‘통계수학’ 담당 교수님께 전송드릴 불참 사유 메일 작성을 도와드릴까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 3346719820 --message "**[작업]**\n\n‘조형준 교수님 면담’ 일정 추가를 내일 오전 11시로 요청하셨습니다.\n해당 시간은 기존 루틴인 ‘통계수학’의 강의 시간(09:00-11:45)과 겹칩니다.\n\n캘린더 내 ‘조형준 교수님 면담’의 비고란에 ‘통계수학 불참’을 작성할까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message edit --channel telegram --target 3346719820 --message-id 87 --message "**[작업]**\n\n‘조형준 교수님 면담’ 일정 추가를 내일 오전 11시로 요청하셨습니다.\n해당 시간은 기존 루틴인 ‘통계수학’의 강의 시간(09:00-11:45)과 겹칩니다.\n\n캘린더 내 ‘조형준 교수님 면담’의 비고란에 ‘통계수학 불참’을 작성할까요?\n\n\n**예**    ~~아니오~~"
```

```bash
openclaw message send --channel telegram --target 1420976538 --message "**[확인]**\n\n‘고려대학교 통계학과 26학번 민경민 점심 약속‘ 일정 추가를 21일 화요일 오후 12시로 요청하셨습니다.\n약속 장소는 따로 말씀하지 않으셨습니다.\n\n아직 약속 장소가 정해지지 않았나요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 1420976538 --message "**[제안]**\n\n‘고려대학교 통계학과 26학번 민경민 점심 약속‘ 일정 추가를 21일 화요일 오후 12시로 요청하셨습니다.\n약속 장소는 따로 말씀하지 않으셨습니다.\n\n고려대학교 지하철역인 안암역으로 약속 장소를 설정할까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" },
      { "text": "기타", "callback_data": "button_other", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message send --channel telegram --target 1420976538 --message "**[작업]**\n\n‘고려대학교 통계학과 26학번 민경민 점심 약속‘ 일정 추가를 21일 화요일 오후 12시로 요청하셨습니다.\n약속 장소는 따로 말씀하지 않으셨습니다.\n\n장소 미정으로 일정을 추가할까요?" --buttons '[
    [
      { "text": "예", "callback_data": "button_yes", "style": "success" },
      { "text": "아니오", "callback_data": "button_no", "style": "primary" }
    ]
  ]'
```

```bash
openclaw message edit --channel telegram --target 1420976538 --message-id 120 --message "**[제안]**\n\n‘고려대학교 통계학과 26학번 민경민 점심 약속‘ 일정 추가를 21일 화요일 오후 12시로 요청하셨습니다.\n약속 장소는 따로 말씀하지 않으셨습니다.\n\n고려대학교 지하철역인 안암역으로 약속 장소를 설정할까요?\n\n\n~~예~~    ~~아니오~~    **기타**"
```


## Rules


### Principles
- 버튼으로 선택지를 빠짐없이 겹침 없이 제시한다.
- 본문은 간결하게 작성한다.
- 하나의 버튼형 메시지는 하나의 답변만 요구한다.
- 버튼형 메시지를 보내기 전에 필요한 맥락을 먼저 파악한다.
- 사용자가 버튼을 클릭하면 해당 버튼형 메시지의 버튼은 제거하고 본문에 내용을 추가한다.
- 버튼은 짧게 작성한다.
- 되돌리기 어려운 작업은 반드시 사용자의 승인을 거친다.
- 질문은 사용자가 즉시 판단할 수 있을 만큼 구체적이어야 한다.
- 질문의 의도와 버튼의 선택지는 정확히 대응해야 한다.
- 사용자가 버튼이 아닌 텍스트로 응답하더라도 동일하게 처리한다.


### Pitfalls
- 헤더에 볼드 처리를 하지 않는 실수. 헤더는 반드시 볼드 처리 해야 한다.
- 헤더와 본문 사이에 \n\n을 삽입하지 않는 실수. 헤더와 본문 사이엔 빈 줄이 하나 있어야 한다.
- 상황 및 맥락과 질문 사이에 \n\n을 삽입하지 않는 실수. 상황 및 맥락과 질문 사이엔 빈 줄이 하나 있어야 한다.
- edit 시 질문과 버튼 사이에 \n\n\n을 삽입하지 않는 실수. 질문과 버튼 사이엔 빈 줄이 두 줄 있어야 한다.
- 줄바꿈 시 \n이 아닌 다른 형식의 줄바꿈을 사용하는 실수. JSON이기 때문에 반드시 \n 형식을 사용해야 한다.
- edit 시 버튼의 순서를 바꾸는 실수. 버튼 순서는 그대로 유지한다.
- 사용자가 버튼을 눌렀음에도 해당 메시지의 버튼을 제거하지 않는 실수. 사용자가 버튼을 누르면 해당 메시지의 버튼은 Telegram의 편집 기능(edit)으로 제거해야 한다. 편집 시 message-id를 누락하지 않도록 주의해야 한다.
- OpenClaw CLI를 사용하지 않는 실수. 버튼형 메시지가 실제 UI에 나타나도록 OpenClaw CLI로 전송해야 한다.
- 사용자가 선택한 버튼에 볼드 처리를 하지 않는 실수. edit 시 사용자가 선택한 버튼은 볼드 처리 해야 한다.
- 사용자가 선택하지 않은 버튼에 취소선 처리를 하지 않는 실수. edit 시 사용자가 선택하지 않은 버튼은 취소선 처리 해야 한다.
- edit 시 버튼 사이 간격을 띄어쓰기 네 번으로 하지 않는 실수. 버튼 사이 간격은 띄어쓰기 네 번으로 고정이다.
- 버튼을 1개만 생성하거나 5개 이상 생성하는 실수. 버튼은 2개부터 4개까지만 생성할 수 있다.
- 버튼이 4개일 때 1행에 4개를 모두 배치하는 실수. 버튼 4개는 반드시 2행 × 2열로 배치해야 한다.
- 되돌리기 어려운 선택에 danger 외 다른 style을 부여하는 실수. 파기, 삭제, 불참 등 되돌리기 어려운 선택에는 반드시 danger를 사용해야 한다.
- 일정명, 과제명 등 고유 대상에 작은따옴표를 감싸지 않는 실수. 고유 대상은 반드시 작은따옴표로 감싸야 한다.
- 질문을 두 문장 이상으로 작성하는 실수. 질문은 반드시 한 문장이어야 한다.
- 질문이 물음표로 끝나지 않는 실수. 질문은 반드시 물음표로 끝나야 한다.
- 상황 및 맥락을 생략하고 질문만 작성하는 실수. 본문에는 반드시 상황 및 맥락이 포함되어야 한다.
- callback_data에 의미를 알 수 없는 키를 사용하는 실수. callback_data는 버튼의 동작을 식별할 수 있는 명확한 키여야 한다.
- 불필요한 마크다운 서식을 사용하는 실수. 볼드 및 취소선 처리는 정해진 항목에만 적용하고, 나머지 내용은 순수 텍스트로 작성해야 한다.
- 버튼명이 길어지는 실수. 버튼명은 간결해야 하며, 설명은 본문에 담아야 한다.
- 하나의 메시지에 [확인], [제안], [작업]을 복수로 담는 실수. 하나의 메시지에는 하나의 헤더만 사용해야 한다.
- 질문 뒤에 불필요한 부연 설명을 덧붙이는 실수. 질문은 물음표로 끝나야 하며, 그 뒤에 추가 문장이 오면 안 된다.
- 버튼형 메시지를 사용하지 않고 계속해서 일반 텍스트로만 상호작용하는 실수. 버튼형 메시지를 적극적으로 활용해야 한다.
- 버튼형 메시지를 지나치게 남발하는 실수. 궁극적으로 사용자에게 더 나은 UIUX를 제공하기 위해 노력해야 한다.


### Edge Cases
- 이전에 보낸 버튼형 메시지에 사용자가 응답하지 않은 상태에서 새 버튼형 메시지를 보내야 하는 경우, 이전 메시지의 버튼을 먼저 제거한 뒤 새 메시지를 보낸다.
- 버튼형 메시지를 보낸 뒤 상황이 변하여 선택지가 무효해진 경우(예: 일정 자동 취소, 마감 경과), 해당 메시지의 버튼을 제거하고 변경된 상황을 안내한다.
- 동일 상황에 [확인], [제안], [작업]이 모두 가능한 경우, [확인] → [제안] → [작업] 순서로 우선한다. 사실관계가 불확실하면 먼저 확인하고, 확인이 끝난 뒤에 제안이나 작업을 제시한다.
- 사용자가 버튼 대신 텍스트로 응답한 경우, 텍스트 응답을 바탕으로 맥락을 재구성하여 대화를 이어간다. 사용자가 텍스트로 응답한 버튼형 메시지의 버튼은 제거한다.
- 사용자가 과거에 보낸 버튼형 메시지의 버튼을 뒤늦게 누른 경우, 해당 시점에서 선택지가 여전히 유효한지 검증한다. 유효하면 처리하고, 무효하면 버튼을 제거한 뒤 현재 상황을 반영한 새 메시지를 보낸다.
- 사용자가 동일 버튼을 연속으로 두 번 이상 누른 경우, 두 번째 입력부터는 무시한다. 첫 번째 입력 시점에 이미 버튼이 제거되었으므로 중복 처리가 발생하지 않아야 한다.
- 버튼 선택지 중 하나가 추가 정보 입력을 필요로 하는 경우(예: “기타”), 해당 버튼 클릭 후 텍스트 입력을 유도하는 안내 메시지를 보낸다. 버튼형 메시지가 아닌 일반 텍스트로 안내한다.
- 오류로 인해 버튼형 메시지 전송이 실패한 경우, 동일 메시지를 재전송한다. 재전송 시 callback_data가 중복되지 않도록 접두어를 갱신한다.
- 사용자가 버튼 선택 후 즉시 “취소” 또는 “아 잠깐” 등 해당 의사를 부정하는 메시지를 보낸 경우, 아직 실행되지 않은 동작이면 중단하고 [확인] 메시지로 재질문한다. 이미 실행된 동작이면 되돌림 가능 여부를 안내한다.
- 버튼형 메시지를 보낸 뒤 시스템 점검이나 세션 초기화로 이전 메시지의 message-id를 참조할 수 없는 경우, 버튼 제거를 시도하지 않고 새 메시지로 상황을 이어간다.