# Seedance 2.0 통합 프롬프팅

씨댄스 2.0 프롬프트 작성용 스킬입니다. 기존 5블록 구조·멀티모달 소재 바인딩·타임라인·연장 지침에 seedance-clean의 연기·동선·카메라·조명 연출을 통합했습니다.

## 포함 내용

- `skills/seedance-2-prompting`: 통합 스킬. 요청 언어에 맞는 독립 프롬프트를 작성합니다.
- `skills/seedance-clean`: 통합 스킬을 불러오는 호환 진입점. 두 폴더를 함께 설치하세요.
- 원테이크, 순차 컷, 시간 지정 멀티샷, 지원되는 서비스의 연장 작업.
- 사용자의 NO BGM, 대사, 태그와 컷 구성 보존.

이 저장소는 프롬프트 작성 지침입니다. 영상 생성 API나 모델을 포함하지 않습니다. ByteDance 공식 배포물이 아니며 서비스별 제한과 기능은 현재 제공 환경에서 확인해야 합니다.

## Claude Code 설치

macOS / Linux:

```sh
git clone https://github.com/babicat4242-svg/seedance-2-prompting.git
mkdir -p ~/.claude/skills
cp -R seedance-2-prompting/skills/seedance-2-prompting ~/.claude/skills/
cp -R seedance-2-prompting/skills/seedance-clean ~/.claude/skills/
```

Windows PowerShell:

```powershell
git clone https://github.com/babicat4242-svg/seedance-2-prompting.git
New-Item -ItemType Directory -Path "$env:USERPROFILE\.claude\skills" -Force | Out-Null
Copy-Item -Path '.\seedance-2-prompting\skills\*' -Destination "$env:USERPROFILE\.claude\skills" -Recurse -Force
```

## Codex 설치

동일한 두 스킬 폴더를 `~/.codex/skills/`에 복사합니다. Windows에서는 `%USERPROFILE%\.codex\skills`에 해당합니다. 설치 후 새 대화에서 확인하세요.

## 사용 예

> 씨댄스 2.0 스킬로 10초 원테이크 프롬프트를 만들어줘. 이미지 1장은 인물 참조고, 비 오는 골목에서 편지를 읽는 장면이야. BGM 없이 한국어로 써줘.

> 씨댄스 클린으로 이 장면의 카메라와 조명, 인물 동선을 구체화해줘.

## 통합 시 정리한 규칙

영문 전용, 강제 3초 분할, 강제 FOV, 충돌하는 카메라 블록 위치 규칙을 통일했습니다. 장면에 필요한 제어 수준을 선택하며, 검증되지 않은 생성 사양이나 특정 수치의 효과를 보장하지 않습니다.
