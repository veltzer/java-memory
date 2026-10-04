# TOFIX

Findings from a code scan on 2026-10-04.

## High

- Repo contents - "Investigate java memory flags" (`README.md:2`), but the repo has never contained any code: every tracked file is fleet boilerplate (`.editorconfig`, `.gitignore`, `LICENSE`, `README.md`, `config/project.lua`) and no `*.java`/script/Makefile appears anywhere in git history. Add the actual investigation (Java programs exercising `-Xmx`/`-Xss`/`-XX:MaxMetaspaceSize` etc. and the observed results) or retire the repo.

## Medium

- No build/CI at all - there is no `rsconstruct.toml` and no `.github/workflows/build.yml`, so not even `README.md` is linted; once there is content, add the fleet `rsconstruct.toml` (rumdl, taplo, actionlint, plus checkstyle for the Java sources) and the shared `build.yml`.

## Low

- `README.md:1-2` - hand-written two-line README rather than the fleet's generated one from the shared `tera.templates/README.md.tera`.
