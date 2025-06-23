---
layout: home
title: Agent Innovator Lab (Korean)
nav_order: 1
permalink: /
---
# Agent Innovator Lab
{: .no_toc }

[Requirements](#requirements){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[View it on GitHub](https://github.com/Azure/agent-innovator-lab){: .btn .fs-5 .mb-4 .mb-md-0 }

# Agent Innovoator Lab

Agent Innovator Lab은 화이트보딩과 핸즈온을 통해 프로덕션 런칭에 필요한 에이전트 설계 패턴, 평가 중심 방법론을 같이 고민하고 체험하는 1-day 워크숍입니다. 기존 핸즈온과 달리 코드베이스 일방향 진행이 아니라 (고객마다 적용할 에이전트 패턴이 다르고 목표도 다르고 에이전트 프레임워크도 다르기 때문입니다.) 브레인스토밍 및 화이트보딩 세션을 진행하게 됩니다.


1. 1일 워크샵 (청중 수준에 따라 4시간에서 7시간 정도 소요)
2. 해커톤 스타터 코드
3. RAG/멀티 에이전트 디자인 패턴 참조 가이드

[**요구 사항**](#requirements) | [**시작하기**](#get-started) 

----------------------------------------------------------------------------------------

## 핸즈온 목록

Agent Innovator Lab은 현재 5개의 핸즈온을 제공하고 있습니다. 각 핸즈온은 아래와 같은 주제를 다루고 있습니다.:

| 제목  | 설명 및 링크  |
|-------|-----|
| Lab 0. RAG 기본 | [Azure AI Search기반 기본 RAG 환경 설정](https://github.com/Azure/agent-innovator-lab/tree/main/0_basic-rag)  |
| Lab 0. 에이전트 기본 | [기본 에이전트 체험 (SK, AutoGen, LangGraph)](https://github.com/Azure/agent-innovator-lab/tree/main/0_basic-agent) |
| Lab 1. 에이전틱 디자인 패턴 | [4가지 주요 에이전틱 패턴인 Reflection, Tool Usage, Planning, and Multi-Agent Systems을  톺아보기](https://github.com/Azure/agent-innovator-lab/tree/main/1_agentic-design-ptn) |
| Lab 2. 디자인 패턴 평가 | [Evaluation-driven 핸즈온을 통해 1회성 개발이 아닌 평가 파이프라인을 구축](https://github.com/Azure/agent-innovator-lab/tree/main/2_eval-design-ptn)  |
| Lab 3. 디자인 패턴 최적화 | [cache, prompt, 메모리 관리 등 특정 영역 최적화 실험](https://github.com/Azure/agent-innovator-lab/tree/main/2_eval-design-ptn)  |
| Lab Intermission. 에이전틱 워크플로우 디자인 랩 | [에이전틱 패턴 화이트보딩](lab_intermission) |


## 사전 준비 사항
시작하기 전 아래의 요구 사항을 충족해야 합니다.:

### 접근 및 테스트해야 할 URL
1. Azure OpenAI Service 액세스: https://go.microsoft.com/fwlink/?linkid=2222006
2. Azure AI Foundry Getting Started (AI Hub 및 프로젝트 생성): https://int.ai.azure.com/explore/gettingstarted
3. 필수 설정 및 권한 부여 필요 사항
- Storage Blob Data Contributor 역할 할당
- Azure ML 및 Storage Account 접근 권한 필요
- 환경 변수 수정 (.env 파일 적용 필요)
4. Agent Innovator Lab 기본 코드 수행
- https://github.com/Azure/agent-innovator-lab/blob/main/0_basic-agent/SK/1_basic-concept-with-sk.ipynb
- https://github.com/Azure/agent-innovator-lab/blob/main/2_eval-design-ptn/02_azure-evaluation-sdk/01.2_batch-eval-with-your-data.ipynb
 
## Agentic Architecture 고도화 필수 원칙
- 처음부터 전체 데이터를 넣지 않고 소규모(50~100건) 데이터로 실험
- 점진적으로 200건 → 전체 데이터로 확장
- 단계별 실험 후 확장
- 튜닝 방식:
    - RAG 구성
    - Evaluation-Driven Design Pattern 적용 (Human-in-the-loop 활용)
    - Intent classification포함한 Agentic Design Pattern 적용
    - 핵심 Task별 개발/고도화
    - Tracing, cache를 활용한 구간별 최적화
    - content safety 및 cost control
    - 답변 품질과 응답속도 사이 의 trade-off 고려

### 로컬 환경 구축
```bash
# Python 가상 환경을 만듭니다.
python -m venv venv

# 가상 환경을 활성화합니다.
# Windows에서 활성화하는 방법
venv\Scripts\activate

# macOS 또는 리눅스에서 활성화하는 방법
source venv/bin/activate

# 실습 환경을 설정합니다.
git clone https://github.com/Azure/agent-innovator-lab.git

cd agent-innovator-lab 

pip install -r requirements.txt

```

### Azure ML Compute Instance
```bash
conda create -n venv_agentlab python=3.11

# 실습 환경을 설정합니다.
git clone https://github.com/Azure/agent-innovator-lab.git

cd agent-innovator-lab 

pip install -r requirements.txt
```


## 기여

이 프로젝트는 다양한 기여와 제안을 환영합니다. 대부분의 기여는 Contributor License Agreement(이하 CLA, 기여자 라이선스 계약)에 동의하셔야 하며, 이를 통해 귀하가 해당 기여를 할 권리가 있고 실제로 그렇게 함으로써 저희에게 해당 기여물을 사용할 권리를 부여함을 선언하게 됩니다. 자세한 내용은 https://cla.opensource.microsoft.com에서 확인하실 수 있습니다.

Pull Request(이하 PR)를 제출하시면 CLA 봇이 자동으로 CLA 제출 필요 여부를 확인하고, 상태 체크나 코멘트 등으로 PR에 표시합니다. 봇의 안내에 따라 절차를 진행해주시면 됩니다. CLA는 한 번만 제출하시면, 해당 CLA를 사용하는 모든 저장소에 적용됩니다.

이 프로젝트는 [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) 를 채택하고 있습니다. 자세한 내용은 행동 강령 FAQ를 참고하시거나, 추가적인 질문이나 의견이 있으실 경우 언제든 [opencode@microsoft.com](mailto:opencode@microsoft.com) 으로 연락해주시기 바랍니다.

## 상표권

이 프로젝트에는 프로젝트, 제품 또는 서비스와 관련된 상표나 로고가 포함되어 있을 수 있습니다.
Microsoft 상표 또는 로고의 사용은 반드시 [Microsoft 상표 및 브랜드 가이드라인](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general)을 준수해야 하며, 이에 따라야 합니다.
이 프로젝트의 수정된 버전에서 Microsoft 상표 또는 로고를 사용할 경우, 사용자에게 혼동을 주거나 Microsoft의 공식 후원 또는 지원을 암시해서는 안 됩니다.
제3자 상표 또는 로고의 사용은 해당 제3자의 정책을 따라야 합니다.
