# eumseum

한국어와 영어를 대상으로 하는 LLM 출력 압축 skill.

`eumseum`은 한국어 음슴체와 짧은 영어 기술 문체를 사용해 LLM 응답의 출력
토큰을 줄이는 것을 목표로 함.

## 하는 일

- 한국어: 음슴체 사용. 문장 끝을 `-ㅁ`, `-음`, `-임`, `-함` 중심으로 압축함.
- 영어: 관사, filler, hedging 제거. 의미가 명확하면 fragment 사용함.
- 기술 내용: code, API name, error message, path, symbol은 그대로 유지함.
- 안전 예외: 보안 경고나 삭제 작업은 일반적이고 명확한 문장 사용함.

## 파일

- [skills/eumseum/SKILL.md](skills/eumseum/SKILL.md): agent skill 시스템용 본체.
- [instructions/user-custom-instructions.md](instructions/user-custom-instructions.md): 사용자 맞춤형 지침에 붙여 넣기 좋은 경량 버전.

특정 LLM/agent 전용 파일은 포함하지 않음. 필요한 도구에 직접 복사하거나 참조해서
사용하면 됨.

## 사용

skill은 `$eumseum`, `/eumseum`, 또는 아래 표현으로 호출함.

- `음슴체로 답변`
- `토큰 절약 모드`
- `use eumseum`
- `be terse in Korean and English`

해제는 아래 표현 사용함.

- `normal mode`
- `polite language`
- `일반 모드`
- `존댓말로`

## 설계 목표

목표는 실사용 가능한 토큰 절약임.

코딩, 분석, 리뷰, 디버깅, 기술 설명에서 정확도는 유지하고 출력 토큰만 줄이는 것을
목표로 함.

<details>
<summary>English</summary>

# eumseum

LLM output compression skill for Korean and English.

`eumseum` reduces LLM output tokens with Korean 음슴체 and terse English
technical prose.

## What It Does

- Korean: uses 음슴체. Ends sentences with `-ㅁ`, `-음`, `-임`, `-함` where possible.
- English: drops articles, filler, and hedging. Uses fragments when clear.
- Technical content: preserves code, API names, error messages, paths, and symbols.
- Safety: uses normal clear language for security warnings or destructive actions.

## Files

- [skills/eumseum/SKILL.md](skills/eumseum/SKILL.md): main skill for agent skill systems.
- [instructions/user-custom-instructions.md](instructions/user-custom-instructions.md): lightweight default instructions for custom user preferences.

No LLM/agent-specific glue files included. Copy or reference these files directly in your tool of choice.

## Use

Invoke skill with `$eumseum`, `/eumseum`, or phrases like:

- `음슴체로 답변`
- `토큰 절약 모드`
- `use eumseum`
- `be terse in Korean and English`

Disable with:

- `normal mode`
- `polite language`
- `일반 모드`
- `존댓말로`

## Design Goal

Goal is practical token reduction.

Keep accuracy. Reduce output tokens for coding, analysis, review, debugging, and
technical explanation across Korean and English.

</details>
