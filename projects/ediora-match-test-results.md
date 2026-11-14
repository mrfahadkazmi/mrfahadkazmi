# EDIORA Match — local testing evidence

**Review date:** 14 November 2026  
**Source reviewed:** EDIORA Match source archive, version 1.6.10  
**Environment:** Linux x86-64; Python 3.13.5; Node.js 22.16.0; installed Go 1.23.2.  
**Scope:** Source-level tests, not a native Windows production test.

## Verified commands and outcomes

| Command / check | Result | Scope |
| --- | --- | --- |
| `python3 -m unittest discover -s tests -p 'test_oracle_transfer_progress.py' -v` | **PASS: 3 tests** | Simulated progress event parsing and download/upload status |
| `python3 -m unittest discover -s tests -p 'test_automatic_credentials.py' -v` | **PASS: 3 tests** | Credential/environment handling tests |
| `python3 -m unittest discover -s tests -p 'test_duration_choices.py' -v` | **PASS: 5 tests** | Content boundaries and duration choices |
| `test_cloud_transport.py`, three separately selected tests | **PASS: 3 tests** | Resume after partial transfer, manifest validation, secret export isolation |
| `node tools/check_ui_refresh.cjs` | **PASS: 1 regression script** | UI polling/state-refresh behavior |
| `gofmt -l desktop/*.go` | **PASS: zero unformatted files** | Formatting only, not compilation |
| `python3 -m compileall -q` on 5 selected processing modules | **PASS** | Syntax compilation only |
| `node tools/check_ui_modes.cjs` | **FAILED** | Test environment lacks a mocked `document.addEventListener`; UI correctness not established by this run |
| `node tools/test_monitor_history_retry.cjs` | **FAILED** | Test harness called `require` with undefined module ID; behavior unverified |
| Full `test_cloud_transport.py` suite | **INCOMPLETE** | Timed out while running the full suite; no suite-wide PASS claim |
| `go test ./...` | **NOT RUN** | Local Go 1.23.2 is older than the source's Go 1.26.0 requirement |
| Native Windows/cloud end-to-end test | **NOT RUN** | Requires a live Windows run and configured services |

**Total independently completed Python test cases above:** 14 passing. These tests run against local mocks and source logic; they do **not** prove successful live Google Drive, SSH, Kaggle, YouTube, or full video export behavior.

## How to reproduce selected tests

From the extracted source project directory:

```bash
python3 -m unittest discover -s tests -p 'test_oracle_transfer_progress.py' -v
python3 -m unittest discover -s tests -p 'test_automatic_credentials.py' -v
python3 -m unittest discover -s tests -p 'test_duration_choices.py' -v
python3 -m unittest discover -s tests -p 'test_cloud_transport.py' -k test_resume_does_not_redownload_completed_upload -v
python3 -m unittest discover -s tests -p 'test_cloud_transport.py' -k test_manifest_rejects_path_traversal_wrong_clip_and_duplicates -v
python3 -m unittest discover -s tests -p 'test_cloud_transport.py' -k test_secret_export_excludes_other_drive_connections -v
node tools/check_ui_refresh.cjs
```

The source is currently **not published in this portfolio repository**, so third parties cannot independently reproduce these commands from this page alone. This is a transparent local review record, not public CI evidence.

## Next steps

1. Repair the two failing JavaScript test harnesses and rerun.
2. Run the Go test suite with the required Go toolchain.
3. Add genuine Windows and live-cloud test logs with secrets redacted.
4. Publish a safe, reproducible sample project or sanitized source subset when ready.

[Back to EDIORA Match](ediora-match.md)
