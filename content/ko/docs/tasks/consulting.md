---
title: 상담사 상담 화면
description: >
  상담사는 상담 화면에서 고객의 '상담사 연결'에 응답합니다.
date: 2024-01-05
weight: 4
---

{{% pageinfo %}}
고객이 상담사 연결을 선택하면 상담사는 자동/수동으로 연결되어 응대합니다.
{{% /pageinfo %}}

1. 챗봇과 대화하던 고객이 '상담사와 연결'을 선택합니다.
2. 상담사는 좌측 상담 대기 리스트에서 상담 시작을 선택합니다.
3. 가운데 상담 화면에 고객과 챗봇간의 대화 내용이 표시됩니다.
4. 고객 창에 '상담사가 연결되었습니다' 는 메시지가 표시됩니다.
5. 고객과 상담사 간의 채팅이 진행됩니다.

![상담사 화면](image-1.png)

--------------------------

```mermaid
sequenceDiagram
    autonumber
    loop 질답 이력
    사용자->>챗봇: 질문
    챗봇->>회사 정보: 회사 정보 검색
    회사 정보->>챗봇: 회사 정보 반환
    loop LLM 생성 호출
    챗봇->>LLM: 답변 요청 ( 질문 + 회사 정보 + 질답 이력 )
    LLM->>챗봇: 답변 반환
    end
    챗봇->>사용자: LLM 답변 + 회사 정보
    Note right of 챗봇: 질문과 답변의 저장
    end
    사용자->>챗봇: 상담사 연결 선택
    챗봇->>사용자: 전화번호, 이름 요청
    사용자->>챗봇: 전화번호, 이름 입력
    챗봇->>상담사: 상담사 연결 대기
    상담사->>챗봇: 상담 시작
    챗봇->>상담사: 챗봇 대화 정보 제공
    상담사->>사용자: 채팅, 혹은 전화
    Note right of 챗봇: 질문과 답변의 저장
    
    
```

--------------------------

* 아래 동영상은 사용자와 챗봇 간의 상담 시연입니다. 

<iframe width="1000" height="700" src="https://www.youtube.com/embed/RW-2kjcbLGI?si=zoV89iY3H3PNS7yk&amp;controls=0&autoplay=1&mute=0&controls=0&loop=1&playlist=RW-2kjcbLGI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
