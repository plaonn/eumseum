# eumseum

<p align="center">
  <img src="assets/eumseum-logo.svg" alt="eumseum logo" width="160">
</p>

<details>
<summary>English</summary>

Portable response instructions for reducing LLM output tokens, centered on compact Korean direct conversation.

`eumseum` takes its name from Korean 음슴체, but does not force every sentence to end with `-ㅁ`, `-음`, `-임`, or `-함`. It selects the shortest clear expression among natural 음슴체 endings, noun phrases, fragments, status words, and short standard sentences.

## What It Does

- Removes greetings, filler, repeated framing, and context already clear from the conversation.
- Uses 음슴체 endings only when they are both concise and natural.
- Preserves questions, requests, commands, recommendations, uncertainty, conditions, causality, ownership, and order.
- Applies to direct conversation by default. Files, code blocks, documents, emails, reports, commit messages, PR descriptions, and other deliverables use style appropriate to their audience and purpose.
- Preserves code, API names, paths, URLs, CLI flags, symbols, and error strings exactly.
- Uses clear standard language whenever compression would create ambiguity or risk.

## File

- [instructions/user-custom-instructions.md](instructions/user-custom-instructions.md): compact instructions for persistent user or custom instruction settings.

## Use

Copy or reference the instruction file in the persistent instruction surface of the LLM or agent being used. A user's explicit request for another tone, format, or level of detail takes precedence.

## Design Goal

Reduce output tokens as much as practical while preserving meaning, accuracy, and necessary nuance. Token efficiency matters more than consistently imitating a fixed 음슴체 ending pattern.

## License

Released under the [MIT License](LICENSE).

</details>

한국어 직접 대화의 출력 토큰을 줄이기 위한 상시 적용 지침입니다.

`eumseum`은 음슴체에서 이름을 가져왔지만, 모든 문장을 `-ㅁ`, `-음`, `-임`, `-함`으로 끝내는 것이 목표는 아닙니다. 자연스러운 음슴체, 명사구, 단편문, 상태어, 짧은 일반 문장 중 의미가 유지되는 가장 짧은 표현을 선택합니다.

## 주요 기능

- 인사, 미사여구, 반복 설명, 문맥상 자명한 내용을 제거합니다.
- 짧고 자연스러울 때만 음슴체 종결형을 사용합니다.
- 질문, 요청, 명령, 권고, 부정, 불확실성, 조건, 인과관계, 작업 주체, 실행 순서를 보존합니다.
- 기본 적용 범위는 사용자와의 직접 대화입니다. 파일, 코드 블록, 문서, 이메일, 보고서, commit message, PR description 등 산출물은 목적과 독자에 맞는 문체를 사용합니다.
- code, API name, path, URL, CLI flag, symbol, error string은 정확히 보존합니다.
- 압축으로 의미가 모호해지거나 위험해지는 경우에는 분명한 일반 문장을 사용합니다.

## 파일

- [instructions/user-custom-instructions.md](instructions/user-custom-instructions.md): 사용자 맞춤형 지침 등에 상시 적용하기 위한 경량 원본입니다.

## 사용

지침 파일을 사용하는 LLM 또는 agent의 상시 사용자 지침에 복사하거나 참조합니다. 사용자가 특정 문체, 형식, 상세도를 요청하면 해당 요청을 우선합니다.

## 예시

| 일반 표현 | 종결형을 강제한 표현 | 권장 압축 |
| --- | --- | --- |
| 이 방법은 현재 적용할 수 없습니다. | 이 방법은 현재 적용할 수 없음. | 현재 적용 불가. |
| 어떤 방식을 원하세요? | 어떤 방식을 원함? | 어느 방식? |
| 먼저 로그를 확인해 주세요. | 먼저 로그 확인 필요함. | 먼저 로그 확인. |
| 가능성이 낮아 보이지만 확인은 필요합니다. | 가능성 낮음. 확인 필요함. | 가능성은 낮아 보임. 그래도 확인 필요. |

## 설계 목표

의미, 정확성, 필요한 뉘앙스를 보존하면서 출력 토큰을 최대한 줄이는 것이 목표입니다. 고정된 음슴체 종결형의 일관성보다 실제 토큰 효율을 우선합니다.

## 라이선스

[MIT License](LICENSE)를 따릅니다.
