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


### CivicLoop — Load backend environment files in development and production scripts

- **Time (Asia/Kolkata):** 24/11/2026, 23:21:36 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `fix/load-backend-env-file-20261124`
- **Commit:** [`05aadb7428b82edea01ec9896d5ba6e4158be411`](https://github.com/omjoshi-2307/CivicLoop/commit/05aadb7428b82edea01ec9896d5ba6e4158be411)
- **Pull request:** [#5 — load local env files in backend scripts](https://github.com/omjoshi-2307/CivicLoop/pull/5).
- **PR opened (Asia/Kolkata):** 24/11/2026, 23:23:43 IST.
- **Change:** The backend README instructed contributors to copy `.env.example` to `.env`, but the development and production scripts did not load that file. Use Node's built-in `--env-file-if-exists` option for both scripts, preserve shell-provided environment variable precedence, and document the behavior without adding a dependency.
- **Validation:** Confirmed with Node.js 22.16.0 that `.env` values are absent without the flag and loaded with `--env-file-if-exists`. Updated `package.json` parsed successfully; both scripts contain the env-file flag. Node.js 22.16.0 confirmed env-file loading and shell-variable precedence. Full typecheck/build/tests not run because dependencies are not installed.


### Dev — Fall back safely for non-finite OpenAI Retry-After headers

- **Time (Asia/Kolkata):** 24/11/2026, 23:28:53 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `fix/non-finite-retry-after-20261124`
- **Commit:** [`26767644fac72277569f5ecc9773162b2fb84df7`](https://github.com/omjoshi-2307/Dev/commit/26767644fac72277569f5ecc9773162b2fb84df7)
- **Pull request:** [#6 — ignore non-finite Retry-After values](https://github.com/omjoshi-2307/Dev/pull/6).
- **PR opened (Asia/Kolkata):** 24/11/2026, 23:30:19 IST.
- **Change:** Reject non-finite numeric `Retry-After` values before clamping. A header such as `NaN` previously produced a NaN sleep duration, causing `asyncio.sleep` to raise `ValueError` instead of using the bounded exponential backoff. Add parameterized regression coverage for `NaN`, `Infinity`, and `-Infinity`.
- **Validation:** Reproduced that `asyncio.sleep(float("nan"))` raises `ValueError`. 3/3 isolated retry-delay checks passed for non-finite values, valid numeric clamping, and malformed-header fallback. Full `tests/test_providers.py` suite not run because a complete repository checkout is unavailable.


### Dev — Exercise non-finite Retry-After values through the provider retry loop

- **Time (Asia/Kolkata):** 24/11/2026, 23:43:35 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `fix/non-finite-retry-after-20261124`
- **Commit:** [`9e6340a22770ce68bfc5daa9eff68cfb598f6bd1`](https://github.com/omjoshi-2307/Dev/commit/9e6340a22770ce68bfc5daa9eff68cfb598f6bd1)
- **Pull request:** [#6 — ignore non-finite Retry-After values](https://github.com/omjoshi-2307/Dev/pull/6) (existing PR updated).
- **Change:** Add end-to-end provider retry regression cases for `NaN`, `Infinity`, and `-Infinity` Retry-After headers. Each case verifies that the provider retries successfully and sleeps using the finite configured exponential-backoff delay rather than passing a non-finite duration to asyncio.
- **Validation:** 3/3 isolated HTTPX 0.28.1 retry-flow harness cases passed. The committed pytest tests were source-inspected; the full repository pytest suite was not run because a complete checkout is unavailable.


### Jal-Sanchaee-Navachar — Preserve local calendar dates in weekly irrigation schedules

- **Time (Asia/Kolkata):** 24/11/2026, 23:45:33 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/local-calendar-schedule-dates-20261124`
- **Commit:** [`512ced1f22af3a085857ea9baa279000f5fc6a83`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/512ced1f22af3a085857ea9baa279000f5fc6a83)
- **Pull request:** [#5 — preserve local calendar dates in weekly irrigation schedules](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/5).
- **PR opened (Asia/Kolkata):** 24/11/2026, 23:46:21 IST.
- **Change:** Replace UTC ISO-date slicing with local year/month/day formatting after advancing each weekly schedule date. This prevents a schedule generated shortly after local midnight in India from displaying the previous UTC calendar day. Add a timezone-specific regression test for 00:15 IST.
- **Validation:** 8/8 isolated Node.js 22.16.0 tests passed under a UTC process, including a regression case that switches to Asia/Kolkata and verifies all four weekly dates. Full Firebase integration was not run.


### Jal-Sanchaee-Navachar — Validate crop coefficients and water calculations

- **Time (Asia/Kolkata):** 24/11/2026, 23:49:15 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/water-calculation-input-validation-20261124`
- **Commit:** [`33b0aa67d1a64255c2f16d1f0e3566ed1a3a5a57`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/33b0aa67d1a64255c2f16d1f0e3566ed1a3a5a57)
- **Pull request:** [#6 — validate crop coefficient and water calculations](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/6).
- **PR opened (Asia/Kolkata):** 24/11/2026, 23:49:49 IST.
- **Change:** Use own-property checks for crop/stage coefficient lookups, preserve the mid-stage fallback for unknown stages, and reject negative, non-numeric, non-finite, or overflowing evapotranspiration and water-volume calculations. Add a dedicated Node test file for the exported water-calculation helpers.
- **Validation:** 7/7 isolated Node.js 22.16.0 tests passed, covering normal coefficients, inherited keys, invalid inputs, and numeric overflow. Full Firebase integration was not run.


### CivicLoop — Test backend env-file loading and shell precedence

- **Time (Asia/Kolkata):** 24/11/2026, 23:51:05 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `fix/load-backend-env-file-20261124`
- **Commit:** [`7424015ddb2fd812f3cc6c70b08e596edd2ab3a7`](https://github.com/omjoshi-2307/CivicLoop/commit/7424015ddb2fd812f3cc6c70b08e596edd2ab3a7)
- **Pull request:** [#5 — load local env files in backend scripts](https://github.com/omjoshi-2307/CivicLoop/pull/5) (existing PR updated).
- **Change:** Add regression tests that assert both backend start scripts load `.env` before running the server and verify Node's env-file loader preserves shell-provided variable precedence. Temporary test files are cleaned up after each test.
- **Validation:** 2/2 isolated Node.js 22.16.0 tests passed. Full `tsx --test` suite and backend build/typecheck were not run because repository dependencies are not installed locally.


- **Follow-up commit (Asia/Kolkata):** 24/11/2026, 23:52:00 IST — [`4e766af3bb180edf26cc49ebc54d49d65827728b`](https://github.com/omjoshi-2307/CivicLoop/commit/4e766af3bb180edf26cc49ebc54d49d65827728b) corrected regex and newline escaping in the env-file regression test so it matches the actual script flag and writes a valid temporary `.env` file. Validation rerun after correction: 2/2 isolated Node.js 22.16.0 tests passed against the corrected test source.


- **Follow-up commit (Asia/Kolkata):** 24/11/2026, 23:57:04 IST — [`7d43a580ad2f746fdb0b9a854c8d544b4966e1c5`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/7d43a580ad2f746fdb0b9a854c8d544b4966e1c5) addresses Codex P2 review feedback on PR #5: the browser now sends its IANA time zone, the backend validates it and computes weekly calendar dates in that zone without relying on the server's local time zone, and tests cover Asia/Kolkata versus UTC plus invalid zones. Validation: 9/9 isolated Node.js 22.16.0 irrigation-service tests passed. Full Firebase integration was not run.

## 2026-11-25

### CivicLoop — Validate backend server environment configuration

- **Time (Asia/Kolkata):** 25/11/2026, 00:10:40 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `fix/validate-backend-server-config-20261125`
- **Commit:** [`1246b80fd74967d7246ddfc5d486e5d38bbaf948`](https://github.com/omjoshi-2307/CivicLoop/commit/1246b80fd74967d7246ddfc5d486e5d38bbaf948)
- **Pull request:** [#6 — validate backend server environment configuration](https://github.com/omjoshi-2307/CivicLoop/pull/6).
- **PR opened (Asia/Kolkata):** 25/11/2026, 00:11:17 IST.
- **Change:** Extract backend port, host, and Fastify log-level parsing into a pure configuration helper. Reject malformed, fractional, non-finite, and out-of-range ports rather than silently falling back to port 3000; validate supported log levels and preserve the existing defaults. Add focused regression tests and wire the validated configuration into server startup.
- **Validation:** 4/4 isolated Node.js 22.16.0 tests passed using Node's experimental TypeScript type stripping. Full `tsx --test`, TypeScript build/typecheck, and backend integration were not run because project dependencies are not installed in this execution environment.

### JalSanchaeeNavachar — Match the request media type exactly before parsing JSON

- **Time (Asia/Kolkata):** 25/11/2026, 00:13:03 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `fix/strict-json-content-type-20261125`
- **Commit:** [`4334e2f66f926af51bdce68781983670f737cd60`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/4334e2f66f926af51bdce68781983670f737cd60)
- **Pull request:** [#3 — require exact JSON request media type](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/3).
- **PR opened (Asia/Kolkata):** 25/11/2026, 00:13:26 IST.
- **Change:** Replace the prefix-based `application/json` check with an exact media-type comparison that still accepts optional parameters such as `charset=utf-8`. This prevents unsupported types such as `application/jsonp` and `application/json-invalid` from being parsed and persisted as JSON. Add an HTTP regression test verifying accepted parameters, rejected lookalike types, and that rejected requests never call the persistence callback.
- **Validation:** 8/8 HTTP server tests passed on Node.js 22.16.0 using an isolated copy of the current backend server and calculator sources. Firebase integration was not run.

### WALL-E — Let the servo settle after returning to center

- **Time (Asia/Kolkata):** 25/11/2026, 00:15:30 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot)
- **Branch:** `fix/servo-center-settle-20261125`
- **Commit:** [`30b8381ff4f1de2c6641d09d53638d9a7026850c`](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot/commit/30b8381ff4f1de2c6641d09d53638d9a7026850c)
- **Pull request:** [#5 — wait for servo to settle after obstacle scans](https://github.com/omjoshi-2307/WALL-E-Autonomous-Obstacle-Avoiding-Robot/pull/5).
- **PR opened (Asia/Kolkata):** 25/11/2026, 00:15:50 IST.
- **Change:** Move the unreachable 100 ms delay in `lookLeft()` before its return and add the same post-center settling delay to `lookRight()`. Both scan helpers now allow the servo to begin returning to its 115-degree center position before the next movement or scan command.
- **Validation:** 2/2 host-side C++ stub timing assertions passed with g++ 14.2.0 and warnings-as-errors using a minimal harness that mirrors the two scan helpers. This did not compile the repository sketch against the Arduino libraries or verify physical servo motion.

- **Follow-up commit (Asia/Kolkata):** 25/11/2026, 00:16:34 IST — [`8bd224f0701fab4486c7708f6812ba7a09d4eb39`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/8bd224f0701fab4486c7708f6812ba7a09d4eb39) adds an HTTP regression test for the existing 100 KiB request-body limit. It verifies oversized JSON requests receive HTTP 413 and never reach the persistence callback. Validation rerun: 9/9 HTTP server tests passed on Node.js 22.16.0 in the isolated backend harness.


## 2026-11-25

### JalSanchaeeNavachar — Validate backend port configuration

- **Time (Asia/Kolkata):** 25/11/2026, 23:55:54 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `fix/validate-server-port-20261125-run8`
- **Commit:** [`2df1396850aeb38d0657ddbf157a0fbdcc86abb7`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/2df1396850aeb38d0657ddbf157a0fbdcc86abb7)
- **Change:** Replace permissive `Number(PORT) || 5000` startup parsing with a pure helper that accepts blank/default or integer ports 1–65535 and rejects malformed, fractional, zero, and out-of-range values. Add four Node built-in regression tests.
- **Validation:** 4/4 local Node.js tests passed for the isolated helper. Repository dependencies and Firebase integration were not installed/run.
- **Pull request:** [#4 — validate backend port configuration](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/4). **PR opened (Asia/Kolkata):** 25/11/2026, 23:56:18 IST.


### Portfolio OLD — Announce lazy case-study loading accessibly

- **Time (Asia/Kolkata):** 25/11/2026, 23:56:38 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/om-joshi-portfolio--OLD-](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-)
- **Branch:** `fix/a11y-case-study-loading-20261125-run8`
- **Commit:** [`010c2e7bd45826bb902cd26eaa603ef8b57935c`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/010c2e7bd45826bb902cd26eaa603ef8b57935c)
- **Change:** Add a polite live status to the case-study loading fallback so assistive technology announces the state; hide the decorative spinner from screen readers and disable its motion under reduced-motion preferences.
- **Validation:** Source diff inspected. Automated frontend tests/build not run; dependencies and checkout unavailable.
- **Pull request:** [#2 — announce case-study loading state](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/pull/2). **PR opened (Asia/Kolkata):** 25/11/2026, 23:56:52 IST.


### Jal-Sanchaee-Navachar — Reject duplicate farmer IDs in daily schedules

- **Time (Asia/Kolkata):** 25/11/2026, 23:57:49 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Jal-Sanchaee-Navachar](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar)
- **Branch:** `fix/reject-sparse-farmer-schedule-inputs-20261124`
- **Commit:** [`de4501be89cdb28be55160dc1114e297780aab99`](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/commit/de4501be89cdb28be55160dc1114e297780aab99)
- **Change:** Extend the scheduler's existing indexed validation to reject duplicate farmer IDs (including duplicates after trimming surrounding whitespace) before any time slots are allocated, preventing multiple entries from being scheduled against the same farmer identifier. Add two regression tests.
- **Validation:** 8/8 focused Node.js tests passed locally, including existing empty/FIFO/12-hour-window/sparse-input tests and the two duplicate-ID cases. Tests were run against an isolated copy of the PR branch sources; no Firebase integration.
- **PR:** existing [#4 — reject sparse farmer input arrays](https://github.com/omjoshi-2307/Jal-Sanchaee-Navachar/pull/4) updated.


### CivicLoop — Add backend test and type-check CI

- **Time (Asia/Kolkata):** 25/11/2026, 23:58:39 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `ci/backend-tests-20261125-run8`
- **Commit:** [`7ef1fe3c3ae862c3e0a347ba65e5de52345908b4`](https://github.com/omjoshi-2307/CivicLoop/commit/7ef1fe3c3ae862c3e0a347ba65e5de52345908b4)
- **Change:** Add a GitHub Actions backend CI workflow that installs the backend lockfile with Node.js 22, runs the existing backend tests, and type-checks the backend on relevant PRs and main pushes. The repository had no workflow directory.
- **Validation:** Workflow source inspected; execution awaits GitHub Actions after PR creation. No local dependencies/build were run.
- **Pull request:** [#7 — run backend tests and typecheck](https://github.com/omjoshi-2307/CivicLoop/pull/7). **PR opened (Asia/Kolkata):** 25/11/2026, 23:58:53 IST.


## 2026-11-26

### CivicLoop — Run backend CI on the documented Node.js 26 baseline

- **Time (Asia/Kolkata):** 26/11/2026, 23:57:33 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `ci/backend-tests-20261125-run8`
- **Commit:** [`3b036d6abd4dfc78231f2b9dad094c8f7fdd0200`](https://github.com/omjoshi-2307/CivicLoop/commit/3b036d6abd4dfc78231f2b9dad094c8f7fdd0200)
- **Pull request:** [#7 — run backend tests and typecheck](https://github.com/omjoshi-2307/CivicLoop/pull/7) (existing PR updated)
- **Change:** Address Codex P2 feedback by changing the backend CI runtime from Node.js 22 to Node.js 26, matching the repository's documented Node.js 26 LTS baseline. Test, typecheck, lockfile caching, and read-only workflow permissions are unchanged.
- **Validation:** Workflow source inspected. GitHub Actions must rerun on the new PR head; no local dependency install or backend test/typecheck was run in this environment.


### Portfolio OLD — Remove aria-busy from transient loading status

- **Time (Asia/Kolkata):** 26/11/2026, 23:58:20 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/om-joshi-portfolio--OLD-](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-)
- **Branch:** `fix/a11y-case-study-loading-20261125-run8`
- **Commit:** [`5da9d6aae399829b3eb6c44f9532e03bb984c790`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/5da9d6aae399829b3eb6c44f9532e03bb984c790)
- **Pull request:** [#2 — announce case-study loading state](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/pull/2) (existing PR updated)
- **Change:** Address Codex P2 feedback by removing `aria-busy="true"` from the transient `role="status"` fallback. The polite status can now be announced immediately instead of being held while marked busy and then unmounted when the lazy route resolves. Decorative spinner and reduced-motion handling remain unchanged.
- **Validation:** Inspected the one-attribute diff. Frontend tests and production build were not run because no checkout/dependencies are available in this execution environment; fresh Codex review requested after the update.


## 2026-11-27

### Dev — Add Python 3.11 test automation

- **Time (Asia/Kolkata):** 27/11/2026, 00:00:06 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `ci/python-tests-20261126`
- **Commit:** [`5ed83115feccbe5b03771c547f6c85cd44676b41`](https://github.com/omjoshi-2307/Dev/commit/5ed83115feccbe5b03771c547f6c85cd44676b41)
- **Change:** Add a least-privilege GitHub Actions workflow for pull requests and pushes to `main` affecting backend code, tests, dependencies, or the workflow. It installs the existing `requirements.txt` under the README's Python 3.11+ baseline and runs the documented `python -m pytest -q` command.
- **Validation:** Workflow source inspected against the README test command and dependency manifest. CI has not yet run; no local dependency installation or full pytest suite was available in this run.
- **Pull request:** [#7 — Python 3.11 pytest CI](https://github.com/omjoshi-2307/Dev/pull/7). **PR opened (Asia/Kolkata):** 27/11/2026, 00:00:30 IST.


### JalSanchaeeNavachar — Add Node.js quality-check workflow

- **Time (Asia/Kolkata):** 27/11/2026, 00:01:00 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `ci/node-checks-20261126`
- **Commit:** [`ce74760d265c0bda1eb0ac08be6a87021640ca6d`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/ce74760d265c0bda1eb0ac08be6a87021640ca6d)
- **Change:** Add a least-privilege GitHub Actions workflow for pull requests and pushes to `main`. It uses Node.js 22, installs the committed lockfile with `npm ci`, and runs the repository's documented `npm test`, `npm run lint`, and `npm run build` checks. Path filters cover backend, frontend, package manifests, Vite/ESLint configuration, and the workflow itself.
- **Validation:** Workflow source inspected against the README's Node.js 22.12+ prerequisite and existing npm scripts. GitHub Actions has not yet run; no local install/lint/build was available in this environment.
- **Pull request:** [#5 — Node.js tests, lint, and build CI](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/5). **PR opened (Asia/Kolkata):** 27/11/2026, 00:01:20 IST.


- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 00:02:06 IST — [`91fb63042b4dd5097629c1ce39c08f50b839b658`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/91fb63042b4dd5097629c1ce39c08f50b839b658) updates the shared lazy-loading fallback to accept a label, using “LOADING CASE STUDY...” for case-study routes and “LOADING PAGE...” for not-found routes. This addresses the new Codex P3 finding that unknown routes were incorrectly announced as case studies. Validation: focused source diff inspected; frontend build/tests remain unavailable without checkout/dependencies. A fresh Codex review was requested after the prior follow-up.


- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 00:04:05 IST — [`f5ebf4ade6f1378837582c349b586e75562febea`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/f5ebf4ade6f1378837582c349b586e75562febea) adds an ESLint 9 flat configuration after the first new CI run exposed that the documented `npm run lint` script had no `eslint.config.*` file and failed before linting. The configuration enables core recommended checks, React Hooks rules, React Refresh component-export warnings, and browser/Node globals while ignoring generated dependencies/build output. The workflow's lint step will rerun on this commit. Validation: config and package dependency imports source-inspected; full lint is pending GitHub Actions.


- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 00:05:05 IST — [`0eeb8d2ebffa1d613ef61de398031a06b79c2663`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/0eeb8d2ebffa1d613ef61de398031a06b79c2663) adjusts the new ESLint baseline after the first lint run reported 164 pre-existing unused declarations across the legacy UI. These remain visible as warnings instead of blocking the workflow; React Hooks violations remain errors, and the unused declarations can be cleaned incrementally in focused UI changes. Validation: the failed CI log was inspected; a fresh run is pending.


- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 00:07:52 IST — [`2dcdcd743c8899d5f675c63231b094cb07d86753`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/2dcdcd743c8899d5f675c63231b094cb07d86753) fixes the two existing JavaScript errors uncovered by the new lint job: remove the duplicate/default Clock import and repeated Droplets import in `HistoryDashboard.jsx`, and scope the humidity `switch` case in `src/pages/Dashboard/Dashboard.jsx` so its `const` declaration is legal. These are narrow syntax/import fixes; existing unused declarations remain warnings. Validation: exact CI-reported locations inspected and source changes checked; fresh workflow run pending.


### Run 9 validation follow-up — 27 November 2026

- **CivicLoop PR #7:** Updated head `3b036d6abd4dfc78231f2b9dad094c8f7fdd0200`; GitHub Actions `backend` check completed successfully. The Node.js 26 baseline finding was fixed and its outdated review thread was resolved. A fresh Codex review was requested.
- **Portfolio OLD PR #2:** Updated head `91fb63042b4dd5097629c1ce39c08f50b839b658`; Vercel preview check completed successfully. The P2 live-region and P3 route-copy findings were fixed and both outdated threads were resolved. A fresh Codex review was requested. Frontend build/test execution remains unverified; Vercel's check reports preview feedback only.
- **Dev PR #7:** Updated head `5ed83115feccbe5b03771c547f6c85cd44676b41`; GitHub Actions `tests` check completed successfully. The workflow installs the README-declared dependencies and runs the documented pytest suite.
- **JalSanchaeeNavachar PR #5:** Updated head `2dcdcd743c8899d5f675c63231b094cb07d86753`; GitHub Actions backend tests passed **15/15**, ESLint completed with **174 existing warnings and 0 errors**, but the Vite build failed because `react-router-dom` is imported by `src/main.jsx` and `src/routes/index.jsx` but is absent from both `package.json` and `package-lock.json`. No dependency/lockfile edit was made because a reproducible lockfile could not be generated in this environment. PR remains open with this concrete blocker.
- **Merge decisions:** No PR merged. Branch-protection/required-review settings could not be independently verified through the available GitHub integration, and CivicLoop's contribution guide explicitly requires project-lead approval before merge.


### JalSanchaeeNavachar PR #5 — Copilot dependency follow-up (external co-authored commit)

- **Time (Asia/Kolkata):** 27/11/2026, 00:09:43 IST (GitHub commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `ci/node-checks-20261126`
- **Commit:** [`33cc540becd21a4df305030b3e4227f43a2e3442`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/33cc540becd21a4df305030b3e4227f43a2e3442)
- **Pull request:** [#5](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/5)
- **Authorship note:** GitHub reports `omjoshi-2307` as commit author, `web-flow` as committer, and `copilot-swe-agent[bot]` as co-author. This is recorded separately from the assistant-authored commit count.
- **Change:** Added the missing app/build dependencies (including `react-router-dom` and `lucide-react`) and regenerated `package-lock.json` to address the Vite unresolved-import finding. The commit modifies only `package.json` and `package-lock.json`.
- **Validation:** No check runs were present for this commit at inspection time; build/install validation is pending.


- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 00:14:32 IST — [`9ead62d843be44a3fa45e98f016d324c594c22a7`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/9ead62d843be44a3fa45e98f016d324c594c22a7) adds `postcss.config.*` and `tailwind.config.*` to both pull-request and main-push path filters, addressing the Codex P2 finding that CSS build-configuration-only changes could skip CI. Validation: inspected both path lists and the focused diff; a new workflow run is pending.


### Final CI and review results — 27 November 2026

- **Observed at:** 27/11/2026, 00:15:04 IST.
- **CivicLoop PR #7:** Node.js 26 backend workflow passed on `3b036d6abd4dfc78231f2b9dad094c8f7fdd0200`; backend test step and TypeScript type-check succeeded. The Codex Node-version finding is resolved. A fresh Codex review was requested. Merge remains blocked by the repository's required project-lead approval and unavailable branch-protection verification.
- **Portfolio OLD PR #2:** Latest Vercel Preview Comments check passed on `91fb63042b4dd5097629c1ce39c08f50b839b658`; both Codex accessibility threads are resolved. No frontend build or test run is claimed.
- **Dev PR #7:** Python 3.11 GitHub Actions job passed on `5ed83115feccbe5b03771c547f6c85cd44676b41`: **186 passed, 1 warning**.
- **JalSanchaeeNavachar PR #5:** Latest GitHub Actions `quality` job passed on `9ead62d843be44a3fa45e98f016d324c594c22a7`. `npm ci` installed 379 packages; backend tests **15 passed, 0 failed**; ESLint **0 errors, 174 warnings** (legacy unused declarations remain visible); Vite production build succeeded in 6.09 seconds. Vite emitted a bundle-size warning for the 1.32 MB JavaScript bundle (407.48 kB gzip). All three Codex findings (ESLint config, frontend dependencies/lockfile, PostCSS/Tailwind path filters) were resolved after the successful run. The package/lockfile update commit `33cc540becd21a4df305030b3e4227f43a2e3442` was co-authored by `copilot-swe-agent[bot]` and remains separately identified from assistant-authored commits.
- **Merge decisions:** No PR merged. Dev #7 and JalSanchaeeNavachar #5 were opened in this run and remain inside the 12-hour waiting window. Older PRs remain open because required human approval and branch-protection requirements could not be fully verified; CivicLoop also explicitly requires project-lead approval.

### Dev — Disable persisted checkout credentials after review finding

- **Time (Asia/Kolkata):** 27/11/2026, 27/11/2026, 00:24:41 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/Dev](https://github.com/omjoshi-2307/Dev)
- **Branch:** `ci/python-tests-20261126`
- **Commit:** [`ce419e883f1551b482ea9089286b6d751a148e35`](https://github.com/omjoshi-2307/Dev/commit/ce419e883f1551b482ea9089286b6d751a148e35)
- **Pull request:** [#7 — Python 3.11 pytest CI](https://github.com/omjoshi-2307/Dev/pull/7) (existing PR updated)
- **Change:** Address the Codex P2 finding by setting `persist-credentials: false` on `actions/checkout@v4`. No later workflow step requires authenticated Git, so the read-only checkout token is no longer persisted in Git configuration while dependency installation and tests execute.
- **Validation:** Inspected the updated workflow and confirmed the setting is scoped to the checkout step. GitHub Actions must rerun on the new PR head; no local workflow execution was possible.

### CivicLoop — Disable persisted checkout credentials in backend CI

- **Time (Asia/Kolkata):** 27/11/2026, 27/11/2026, 00:26:02 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/CivicLoop](https://github.com/omjoshi-2307/CivicLoop)
- **Branch:** `ci/backend-tests-20261125-run8`
- **Commit:** [`4059ca004de0b4d3dadb3fb86f4f7564c99e3b6d`](https://github.com/omjoshi-2307/CivicLoop/commit/4059ca004de0b4d3dadb3fb86f4f7564c99e3b6d)
- **Pull request:** [#7 — run backend tests and typecheck](https://github.com/omjoshi-2307/CivicLoop/pull/7) (existing PR updated)
- **Change:** Set `persist-credentials: false` for `actions/checkout@v4` so the read-only checkout token is not left in Git configuration while backend dependencies and tests execute. No later step needs authenticated Git.
- **Validation:** Inspected the workflow diff and confirmed the option is attached to the checkout step. Updated GitHub Actions run is pending; no local workflow execution was available.

### JalSanchaeeNavachar — Disable persisted checkout credentials in Node.js CI

- **Time (Asia/Kolkata):** 27/11/2026, 27/11/2026, 00:26:18 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/JalSanchaeeNavachar](https://github.com/omjoshi-2307/JalSanchaeeNavachar)
- **Branch:** `ci/node-checks-20261126`
- **Commit:** [`36d34402b0e8e848c5e416cd32174b875f8f001a`](https://github.com/omjoshi-2307/JalSanchaeeNavachar/commit/36d34402b0e8e848c5e416cd32174b875f8f001a)
- **Pull request:** [#5 — run Node.js tests, lint, and build](https://github.com/omjoshi-2307/JalSanchaeeNavachar/pull/5) (existing PR updated)
- **Change:** Set `persist-credentials: false` on `actions/checkout@v4` so the read-only checkout token is not retained while npm dependencies, tests, lint, and build scripts execute. No subsequent workflow step needs authenticated Git.
- **Validation:** Inspected the workflow diff and confirmed the option is scoped to the checkout step. Updated quality workflow run is pending; no local workflow execution was available.

### Portfolio OLD — Add regression coverage for accessible lazy-route loading

- **Time (Asia/Kolkata):** 27/11/2026, 27/11/2026, 00:27:57 IST (source commit timestamp)
- **Repository:** [omjoshi-2307/om-joshi-portfolio--OLD-](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-)
- **Branch:** `fix/a11y-case-study-loading-20261125-run8`
- **Commit:** [`48d76b7ecda8909a81cb915815018afcd1fc1132`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/48d76b7ecda8909a81cb915815018afcd1fc1132)
- **Pull request:** [#2 — announce case-study loading state](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/pull/2) (existing PR updated)
- **Change:** Add a Node.js regression test for the lazy-route fallback's polite status semantics, decorative spinner accessibility, reduced-motion class, route-specific labels, and absence of the transient `aria-busy` attribute.
- **Validation:** Test source and assertions inspected. The test is wired into the existing `npm test` command through `project-validation.test.mjs`; execution is pending because no local repository checkout/dependencies are attached.

- **Follow-up commit (Asia/Kolkata):** 27/11/2026, 27/11/2026, 00:28:28 IST — [`3433d5652ce8f0bb2c39797295f620336945f087`](https://github.com/omjoshi-2307/om-joshi-portfolio--OLD-/commit/3433d5652ce8f0bb2c39797295f620336945f087) corrects escaping in the new lazy-loading accessibility regression assertions so the regular expressions match whitespace and literal periods as intended. Validation: inspected the resulting test source; execution remains pending without a checkout/runtime.
