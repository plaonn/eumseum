# eumseum

<p align="center">
  <img src="assets/eumseum-logo.svg" alt="eumseum logo" width="160">
</p>

한국어와 영어를 대상으로 하는 LLM 출력 압축 skill입니다.

`eumseum`은 한국어 음슴체와 짧은 영어 기술 문체를 사용해 LLM 응답의 출력
토큰을 줄이는 것을 목표로 합니다.

## 주요 기능

- 한국어 직접 대화에서는 별도 문체 요청이 없을 때 음슴체를 사용합니다. 문장 끝은 `-ㅁ`, `-음`, `-임`, `-함` 중심으로 압축합니다.
- 영어 직접 대화에서는 별도 문체 요청이 없을 때 관사, filler, hedging을 줄입니다. 의미가 명확하면 fragment를 사용합니다.
- 산출물에는 음슴체를 적용하지 않습니다. 파일, 코드 블럭, 문서, 이메일, 보고서, commit message, PR description 등은 맥락에 맞는 일반 문체를 사용합니다.
- 기술 내용은 보존합니다. code, API name, error message, path, symbol은 그대로 유지합니다.
- 보안 경고나 삭제 작업처럼 명확성이 중요한 경우에는 일반적이고 분명한 문장을 사용합니다.

## 파일

- [skills/eumseum/SKILL.md](skills/eumseum/SKILL.md): agent skill 시스템용 본체입니다.
- [instructions/user-custom-instructions.md](instructions/user-custom-instructions.md): 사용자 맞춤형 지침에 붙여 넣기 좋은 경량 버전입니다.

특정 LLM/agent 전용 파일은 포함하지 않습니다. 필요한 도구에 직접 복사하거나
참조해서 사용하면 됩니다.

## 사용

skill은 `$eumseum`, `/eumseum`, 또는 아래 표현으로 호출할 수 있습니다.

- `음슴체로 답변`
- `토큰 절약 모드`
- `use eumseum`
- `be terse in Korean and English`

해제는 아래 표현을 사용합니다.

- `normal mode`
- `polite language`
- `일반 모드`
- `존댓말로`

사용자가 다른 문체를 요청하면 그 문체를 우선합니다. 음슴체는 사용자와의 직접
대화에만 적용하고, 산출물에는 적용하지 않습니다.

## 설계 목표

목표는 실사용 가능한 토큰 절약입니다.

코딩, 분석, 리뷰, 디버깅, 기술 설명에서 정확도는 유지하고 출력 토큰만 줄이는 것을
목표로 합니다.

## 라이선스

[MIT License](LICENSE)를 따릅니다.

<details>
<summary>English</summary>

# eumseum

LLM output compression skill for Korean and English.

`eumseum` reduces LLM output tokens with Korean 음슴체 and terse English
technical prose.

## What It Does

- Direct Korean conversation: uses 음슴체 when user has not requested another style.
- Direct English conversation: drops articles, filler, and hedging when user has not requested another style.
- Deliverables: files, code blocks, docs, emails, reports, commit messages, and PR descriptions use normal style appropriate to context.
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

If user requests another tone/style, that style wins. Eumseum applies only to
direct conversation, not deliverables.

## Design Goal

Goal is practical token reduction.

Keep accuracy. Reduce output tokens for coding, analysis, review, debugging, and
technical explanation across Korean and English.

## License

Released under the [MIT License](LICENSE).

</details>
