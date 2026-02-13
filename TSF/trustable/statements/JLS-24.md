---
level: 1.1
normative: true
references:
  - type: project_website
    url: "https://json.nlohmann.me/features/parsing/parse_exceptions/"
    description: "Documents that invalid JSON input triggers a parse_error exception (with examples and recommended try/catch)."
  - type: project_website
    url: "https://json.nlohmann.me/home/exceptions/"
    description: "Overview of exception types including parse errors thrown during deserialization."
evidence:
        type: https_response_time
        configuration:
                target_seconds: 2
                urls:
                    - "https://json.nlohmann.me/features/parsing/parse_exceptions/"
                    - "https://json.nlohmann.me/home/exceptions/"
---

The nlohmann/json library recognizes malformed JSON and returns an exception or a discarded value.