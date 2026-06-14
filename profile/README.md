<div align="center">

# 🧪 GitAIOps

### 분리된 테스트 공간 · Isolated Sandbox

**`KO`** 원본 저장소를 직접 건드리지 않고 자유롭게 실험하기 위해 fork해 온 **샌드박스(분리된 테스트 공간)**입니다.
**`EN`** A **sandbox (isolated test space)** — forked so we can freely experiment **without touching the upstream repositories**.

> ⚠️ **공식 저장소가 아닙니다 / Not an official repository.**
> 정식 자료는 아래 원본을 참고하세요 · See the upstream sources below for canonical material.

</div>

---

## ℹ️ 이 조직은 무엇인가 · What is this

**`KO`**
- [`sysnet4admin`](https://github.com/sysnet4admin)의 자료를 fork해 온 **개인 실험·학습용 공간**입니다.
- 원본에서는 마음대로 테스트할 수 없어, **분리된 sandbox**로 옮겨와 안전하게 실험합니다.
- Kubernetes 인프라 구성·배포와 Claude Code 기반 워크플로(AIOps)를 직접 굴려봅니다.

**`EN`**
- A **personal playground for experiments & learning**, forked from [`sysnet4admin`](https://github.com/sysnet4admin).
- Since the upstream can't be freely modified, work happens here in an **isolated sandbox**.
- Used to exercise Kubernetes infra/deployment and Claude Code–driven (AIOps) workflows hands-on.

## 🙏 출처 · Upstream / Credits

**`KO`** 이 조직의 코드는 아래 원본에서 fork했으며, 모든 크레딧은 원작자에게 있습니다.
**`EN`** All code here is forked from the following upstream. Full credit goes to the original author.

- 👤 원작자 · Author: **Hoon Jo** ([`sysnet4admin`](https://github.com/sysnet4admin)) — CNCF Ambassador · AI & Cloud Native Engineer
- 📦 원본 · Upstream:
  - [`sysnet4admin/notiflex-platform`](https://github.com/sysnet4admin/notiflex-platform) — Claude Code 가드레일로 AI 에이전트가 GKE 위에 구축한 B2B 알림 SaaS / A B2B notification SaaS built by an AI agent on GKE under Claude Code guardrails
  - [`sysnet4admin/_Book_GitAIOps`](https://github.com/sysnet4admin/_Book_GitAIOps) — 도서 「AI 시대에 개발자가 알아야 할 인프라 구성·배포 with 클로드 코드」 / Companion book
- 📘 관련 도서 · Related book: *「AI 시대에 개발자가 알아야 할 인프라 구성·배포 with 클로드 코드」*

#### 🔗 원작자 채널 · Author's channels

[![KubernetesLab](https://img.shields.io/badge/KubernetesLab-kuberneteslab.dev-1f6feb?logo=kubernetes&logoColor=white)](https://kuberneteslab.dev/ko)
[![GitHub](https://img.shields.io/badge/GitHub-sysnet4admin-181717?logo=github&logoColor=white)](https://github.com/sysnet4admin)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-hoonjo-0A66C2?logo=linkedin&logoColor=white)](https://linkedin.com/in/hoonjo)
[![YouTube](https://img.shields.io/badge/YouTube-@KubernetesLab-FF0000?logo=youtube&logoColor=white)](https://youtube.com/@KubernetesLab)

## 📂 저장소 · Repositories

| 저장소 · Repo | 내용 · Description |
| --- | --- |
| [**notiflex-platform**](https://github.com/gitaiops/notiflex-platform) | 핵심 실습 프로젝트 fork (ch2~ch8.2, Go · GKE · GitOps · Claude Code) / Main practice project fork |
| [**_Book_GitAIOps**](https://github.com/gitaiops/_Book_GitAIOps) | 책 관련 자료 fork / Book companion fork |

## 🧰 여기서 실험하는 것 · What we test here

`KO` / `EN`
- ☸️ Kubernetes / GKE 인프라 구성 · infra setup
- 🚀 GitOps · ArgoCD · Argo Rollouts · CI/CD 배포 자동화 · deployment automation
- 📊 Prometheus · Grafana · Loki 관측성 · observability
- 🤖 Claude Code 기반 AIOps 워크플로 · AIOps workflows (자연어 → 매니페스트 → 배포)

## 🗺️ 사용법 · How to use

```bash
# 실습 프로젝트 클론 · clone the practice project
git clone https://github.com/gitaiops/notiflex-platform.git
```

**`KO`** 챕터(ch2~ch8.2) 흐름을 따라가며 Claude Code로 인프라 구성·배포를 실습합니다.
**`EN`** Follow the chapter flow (ch2~ch8.2) and practice infra build/deploy with Claude Code.

> **`KO`** 챕터는 별도 브랜치/태그가 아니라 **`main` 브랜치에 누적**됩니다 — 각 챕터가 이전 결과 위에 쌓입니다. 진행 현황은 [`JOURNEY.md`](https://github.com/gitaiops/notiflex-platform/blob/main/JOURNEY.md)에 기록됩니다.
> **`EN`** Chapters are **cumulative on `main`** (not separate branches/tags) — each builds on the previous. Progress is tracked in [`JOURNEY.md`](https://github.com/gitaiops/notiflex-platform/blob/main/JOURNEY.md).

## 🧭 챕터 여정 · Chapter journey

| 챕터 · Ch | 구성한 것 · What's built | 핵심 기술 · Key tech |
| --- | --- | --- |
| **ch2** | GKE 클러스터 + 첫 서비스 배포 · Cluster & first deploy | GKE (Spot, Gateway API), Go `api:v0.1.0` |
| **ch3** | GitOps + CI/CD (커밋 → 자동 배포) · commit → auto-deploy | ArgoCD v3.4.3, GitHub Actions + WIF (keyless) |
| **ch4** | 관측성 · Observability | Prometheus · Grafana · Loki + Fluent Bit · Alerting |
| **ch5** | 트래픽 관리 + 무중단 배포 · Traffic & zero-downtime | Gateway API · HTTPRoute · Argo Rollouts (Blue/Green) |
| **ch6** | 캐시 · 시크릿 · 점진 배포 · Cache/secret/progressive | Valkey · Secret Manager CSI (WI) · Canary (20/50/80%) |
| **ch7** | 엔터프라이즈 규모 · Enterprise scale | 멀티 노드풀 · App of Apps · 멀티테넌시 · multi-nodepool/tenancy |
| **ch8.1** | 메시징 · Messaging | Strimzi Kafka (KRaft) + notifications topic |
| **ch8.2** | 분산 트레이싱 · Distributed tracing | Tempo + OpenTelemetry (OTLP) |
| _ch8.3~ch9_ | CronJob 헬스체크 · 회고 · 온보딩 문서 _(예정 · upcoming)_ | CronJob · repo analysis · runbook |

---

<div align="center">
<sub>🧪 GitAIOps — isolated sandbox · forked from <a href="https://github.com/sysnet4admin">sysnet4admin</a> · not an official repository</sub>
</div>
