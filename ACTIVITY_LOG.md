# Automation Activity Log

This log records meaningful development changes made by the GitHub development automation across the repositories owned by `omjoshi-2307`.

Entries use India Standard Time (Asia/Kolkata) and link to the source commit and pull request. Validation is reported exactly as performed; a source change is not considered tested merely because a PR was opened.

---

## 2026-11-19

### Dev — Reject injected provider model mismatches

- **Time (Asia/Kolkata):** 23:42:39 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `feature/stage-2-chat-orchestrator`
- **Commit:** [`9f784af8b4cca198b5404c47c27b22fc635c89d9`](https://github.com/omjoshi-2307/Dev/commit/9f784af8b4cca198b5404c47c27b22fc635c89d9)
- **Pull request:** [#5 — DEV Stage 2 Task 3: Implement Chat Orchestrator](https://github.com/omjoshi-2307/Dev/pull/5) (existing PR updated)
- **Change:** Verify that injected built-in Ollama and OpenAI adapters are configured for the same model selected by deterministic routing. Reject mismatches before provider execution and add parameterized regression coverage for both adapters.
- **Validation:** Tests added but not executed in this run; no local checkout/runtime is available. Static source inspection only; CI status for the new head remains to be checked.


### CivicLoop — Add backend health-route regression coverage

- **Time (Asia/Kolkata):** 19/11/2026, 23:45:56 IST
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `test/backend-health-route`
- **Commit:** [`20135c55c38eb567f1636feccf5690657971dacc`](https://github.com/omjoshi-2307/CivicLoop/commit/20135c55c38eb567f1636feccf5690657971dacc)
- **Pull request:** [#4 — health route regression coverage](https://github.com/omjoshi-2307/CivicLoop/pull/4) (draft; awaiting test execution and project-lead review).
- **Change:** Add a Node.js test-runner script and a Fastify `inject()` regression test for `GET /health`; document the command and current coverage. No new dependency or database requirement.
- **Validation:** Test added but not executed; no local checkout/runtime is available in this automation environment.


### JalSanchaeeNavachar — Add local startup documentation

- **Time (Asia/Kolkata):** 19/11/2026, 23:47:01 IST
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`5ff14469c150c0a141d44d5c83cfd60e084187a6`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/5ff14469c150c0a141d44d5c83cfd60e084187a6)
- **Pull request:** [#2 — local startup and backend script](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2).
- **Change:** Add the missing `npm run server` script for the existing Express backend and replace the one-line README with accurate local setup, frontend/backend startup, health/API endpoints, quality-check commands, and Firebase security guidance.
- **Validation:** Diff inspected; lint/build not executed in this automation environment because no local checkout/runtime is available.



## 2026-11-20

### JalSanchaeeNavachar — Remove missing server dependencies and normalize irrigation inputs

- **Time (Asia/Kolkata):** 20/11/2026, 23:41:51 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`2c2dd5524aa15b082a010f50120daab814a3ac89`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/2c2dd5524aa15b082a010f50120daab814a3ac89)
- **Pull request:** [#2 — local startup and backend script](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Replace Express/CORS/dotenv imports with Node's built-in HTTP server so the documented server command no longer requires missing packages. Extract schedule calculations, normalize crop/season/soil inputs, support acre/hectare/square-foot conversion, validate request bodies, and add HTTP/calculation regression tests.
- **Validation:** 11 Node tests passed in an isolated local harness; syntax checks passed. Full install/build and Firebase integration were not run because the environment could not reach GitHub for a checkout.


### JalSanchaeeNavachar — Preserve environment-file startup and tighten area validation

- **Time (Asia/Kolkata):** 20/11/2026, 23:44:12 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`6ff566338729ea0bac1458a3bd7ec98832702472`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/6ff566338729ea0bac1458a3bd7ec98832702472)
- **Pull request:** [#2 — backend startup and irrigation validation](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Preserve root `.env` loading with Node's `--env-file-if-exists` option and document the Node version. Reject boolean/object area values in the calculator and cover them with regression cases.
- **Validation:** `npm test` passed 11 tests; backend syntax checks passed. Full install/build and Firebase integration remain unverified due unavailable network checkout.


### JalSanchaeeNavachar — Correct token normalization for unit and soil values

- **Time (Asia/Kolkata):** 20/11/2026, 23:45:06 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`f90172f60f36ac8984ea3c53d8fbd3791fba7426`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/f90172f60f36ac8984ea3c53d8fbd3791fba7426)
- **Pull request:** [#2 — backend startup and irrigation validation](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Corrected a regex escaping error in token normalization. The faulty expression removed the letter `s` rather than whitespace, causing `Sq Ft` and `Sandy` values to fail validation.
- **Validation:** Reproduced the regression locally (7 passed, 4 failed), corrected the expression, then reran `npm test` with 11/11 tests passing and syntax checks passing.


## 2026-11-20

### Jal-Sanchaee-Navachar — Normalize irrigation inputs and validate area

- **Time (Asia/Kolkata):** 20/11/2026, 23:48:47 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/irrigation-input-validation-2026-11-20`
- **Commit:** [`2ee4272532426e846182b37c35e5cbd43b819d9d`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/2ee4272532426e846182b37c35e5cbd43b819d9d)
- **Pull request:** [#2 — validate irrigation planner inputs](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/2)
- **Change:** Normalize capitalized season/soil selections, convert hectares and square feet to acres, reject non-positive/non-numeric areas and unsupported selections, return input validation errors as HTTP 400, and add a Node test command with regression coverage.
- **Validation:** 5 Node tests passed in an isolated harness; calculator and controller syntax checks passed. Full backend integration was not run because no checkout/dependencies were available.


## 2026-11-21

### Portfolio — Make email copying reliable and testable

- **Time (Asia/Kolkata):** 21/11/2026, 23:58:27 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/om-joshi-portfolio--OLD-](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-)
- **Branch:** `fix/copy-email-clipboard-fallback-20261121`
- **Commit:** [`ec9a07d2710274c286b2175b64679457bbef431a`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/ec9a07d2710274c286b2175b64679457bbef431a)
- **Pull request:** [#1 — clipboard copy reliability](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/pull/1).
- **Change:** Extract clipboard copying into a browser helper; fall back when the secure Clipboard API rejects; treat `execCommand('copy')` returning false as failure; ensure temporary textarea cleanup with `finally`; add four focused Node tests; include them in the existing test command; and clear/reuse the copied-state timer to prevent premature feedback reset and timer leaks.
- **Validation:** Four isolated Node 22.16.0 tests passed. Full portfolio test suite, lint, and production build were not run because dependencies and checkout are unavailable.


## 2026-11-22

### JalSanchaeeNavachar — Keep irrigation schedule dates in the local calendar

- **Time (Asia/Kolkata):** 22/11/2026, 00:00:35 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`45eeeabc3d2e33f896325d448eb2a29ac40eee72`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/45eeeabc3d2e33f896325d448eb2a29ac40eee72)
- **Pull request:** [#2 — backend startup and irrigation validation](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Avoid UTC date conversion shifting a local schedule date backward near midnight. Format dates from local year/month/day values and add a regression test for the UTC boundary at 00:15 IST.
- **Validation:** 6/6 irrigation-calculator tests passed under `TZ=Asia/Kolkata` in an isolated Node 22.16.0 harness. Full integration remains unverified.


## 2026-11-22

### WALL-E — Align obstacle threshold and scan-angle documentation

- **Time (Asia/Kolkata):** 22/11/2026, 00:01:40 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot)
- **Branch:** `docs/align-walle-obstacle-scan-20261122`
- **Commit:** [`5ce749f4faf2e4d5ea9af049da6f84eda4c0a01f`](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot/commit/5ce749f4faf2e4d5ea9af049da6f84eda4c0a01f)
- **Pull request:** Pending creation after diff review.
- **Change:** Correct the README's 20 cm threshold to the actual `distance <= 15` code condition and document the real servo scan positions (50° right, 170° left, 115° center) and reverse/scan behavior.
- **Validation:** Documentation cross-checked against `Software/code.cpp`; hardware behavior and Arduino compilation not tested in this environment.


### WALL-E — Correct motor-shield documentation and restore contributor link

- **Time (Asia/Kolkata):** 22/11/2026, 00:02:19 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot)
- **Branch:** `docs/align-walle-obstacle-scan-20261122`
- **Commit:** [`ac101c52302603ccae26f4312c1b7dafcd368187`](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot/commit/ac101c52302603ccae26f4312c1b7dafcd368187)
- **Pull request:** [#4 — align WALL-E README with Arduino behavior](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot/pull/4).
- **Change:** Correct the motor-driver component row to match the AFMotor library used by `Software/code.cpp` and restore the Sarthak Ghogare LinkedIn URL spelling that was accidentally altered in the first README commit.
- **Validation:** Cross-checked against the Arduino source and original README. Hardware/Arduino compilation not performed.

## 2026-11-22

### JalSanchaeeNavachar — Harden irrigation validation and request URL handling

- **Time (Asia/Kolkata):** 22/11/2026, 23:10:44 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [`e65ec1c1873cfd92171286a739a5a10db057209a`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/e65ec1c1873cfd92171286a739a5a10db057209a)
- **Pull request:** [#2 — backend startup and irrigation validation](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Add own-property checks to calculator selection maps, reject non-finite area/water calculations, and return a 400 for malformed request targets instead of allowing URL parsing to throw from the request handler. Add regression coverage for inherited keys, numeric overflow, and malformed HTTP request targets.
- **Validation:** A local mirrored Node harness passed 15/15 tests after the raw HTTP test was corrected in follow-up commit [e1ccb8c](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/e1ccb8c37690f31be9f66561af521b3b61783219). The corrected test file was inspected on the PR branch; full Firebase integration was not run.



### JalSanchaeeNavachar — Correct malformed request-target test escaping

- **Time (Asia/Kolkata):** 22/11/2026, 23:12:31 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `docs/add-local-development-guide`
- **Commit:** [e1ccb8c37690f31be9f66561af521b3b61783219](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/e1ccb8c37690f31be9f66561af521b3b61783219)
- **Pull request:** [#2 — backend startup and irrigation validation](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/2) (existing PR updated)
- **Change:** Correct the raw HTTP test's escape sequences so the malformed request is transmitted with actual CRLF delimiters and the 400 response assertion is a valid regex.
- **Validation:** The corrected request-target test passed in the local Node harness; all 15 calculator/HTTP tests passed. Exact Firebase integration remains unverified.


## 2026-11-22

### Jal-Sanchaee-Navachar — Fix irrigation-service syntax and reject inherited keys/overflow

- **Time (Asia/Kolkata):** 22/11/2026, 23:13:53 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/irrigation-input-validation-2026-11-20`
- **Commit:** [3500888fc1ea3089f1f835e41b22a8ffa69363f4](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/3500888fc1ea3089f1f835e41b22a8ffa69363f4)
- **Pull request:** [#2 — validate irrigation planner inputs](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/2) (existing PR updated)
- **Change:** Fix escaped template literal that prevented the irrigation service from parsing, validate unit and season lookup keys as own properties, reject area conversion and water-total overflow, and add regression tests.
- **Validation:** 7/7 Node tests passed in an isolated harness. Firebase/controller integration was not run.


## 2026-11-23

### Dev — Reject custom transport subclasses for local-only Ollama traffic

- **Time (Asia/Kolkata):** 23/11/2026, 23:59:36 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `feature/stage-2-chat-orchestrator`
- **Commit:** [`428cf6f3c6906c36483ec83b43ddb42c86f1a413`](https://github.com/omjoshi-2307/Dev/commit/428cf6f3c6906c36483ec83b43ddb42c86f1a413)
- **Pull request:** [#5 — DEV Stage 2 Task 3: Implement Chat Orchestrator](https://github.com/omjoshi-2307/Dev/pull/5) (existing PR updated)
- **Change:** Require exact trusted HTTPX transport classes for local Ollama requests and the exact direct httpcore connection-pool class. Reject subclasses that can override transport execution or routing. Add regression tests for subclassed AsyncHTTPTransport and MockTransport.
- **Validation:** Focused isolated validator harness using HTTPX 0.28.1 passed 7/7 checks (exact direct and Mock transports accepted; custom transport subclasses, explicit proxy transport, and request/response event hooks rejected). The committed pytest file and full repository suite were not executed in this environment.


### Jal-Sanchaee-Navachar — Validate farmer demand and allocate whole-minute irrigation slots

- **Time (Asia/Kolkata):** 24/11/2026, 00:02:11 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/validate-daily-irrigation-schedule`
- **Commit:** [`27a64d338c496060d00364c74594514eb2de4319`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/27a64d338c496060d00364c74594514eb2de4319)
- **Pull request:** [#3 — validate farmer demand and prevent zero-minute slots](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/3).
- **PR opened (Asia/Kolkata):** 24/11/2026, 00:04:22 IST.
- **Change:** Validate the farmer list, Firestore document IDs, and positive finite `litres_day` values before scheduling. Allocate at least one whole minute for each positive request and round up to avoid under-allocating pump time. Add Node built-in regression tests and replace the placeholder backend test script.
- **Validation:** 5/5 focused Node.js 22.16.0 tests passed. Full backend/Firebase integration and frontend build were not run.


- **Follow-up commit (24/11/2026, 00:03:02 IST):** [`ab0a993db1f15605cd8acd4aa24cf3baad03a1a9`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/ab0a993db1f15605cd8acd4aa24cf3baad03a1a9) — corrected the FIFO capacity regression fixture after its first local execution showed that the original 11,000 L case exactly fit the remaining 60-minute window. The fixture now uses 11,500 L so the following 1,000 L farmer correctly remains unscheduled. Validation completed: 5/5 focused Node.js 22.16.0 tests passed.


- **Follow-up commit (24/11/2026, 00:03:42 IST):** [`0cd63e8421443fa1adb71cc3db5b75d391692557`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/0cd63e8421443fa1adb71cc3db5b75d391692557) — reused the existing `minutesToTimeString` helper from `backend/utils/dateUtils.js` instead of introducing a duplicate formatter. Validation rerun completed on the merged `main` scheduler sources: 5/5 focused Node.js 22.16.0 tests passed.


- **Follow-up commit (24/11/2026, 00:07:08 IST):** [`ccf8d932d71b14e8558a621c2bb6000bab1b9320`](https://github.com/omjoshi-2307/Dev/commit/ccf8d932d71b14e8558a621c2bb6000bab1b9320) — reject non-empty or unverifiable HTTPX request/response event-hook lists on injected local Ollama clients, and add parameterized regression tests. This addresses a further Codex P1 finding that hooks could forward local-only request or response content.


## 2026-11-24

### Jal-Sanchaee-Navachar — Reject sparse farmer arrays with a typed validation error

- **Time (Asia/Kolkata):** 24/11/2026, 23:17:04 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/reject-sparse-farmer-schedule-inputs-20261124`
- **Commit:** [`8499e8de4f45177108d3a52f49c9b32c968a58c2`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/8499e8de4f45177108d3a52f49c9b32c968a58c2)
- **Pull request:** [#4 — reject sparse farmer input arrays](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/4).
- **PR opened (Asia/Kolkata):** 24/11/2026, 23:18:36 IST.
- **Change:** Replace `Array#forEach` validation with indexed iteration so sparse array slots are checked instead of skipped. A sparse farmer list previously passed validation and then threw an untyped `TypeError` during schedule generation; it now raises `ScheduleInputError` with the invalid index. Add a regression test.
- **Validation:** The sparse-array failure was reproduced against the pre-change implementation. 6/6 focused Node.js 22.16.0 tests passed after the fix; `node --check` passed for the scheduler and test file.
