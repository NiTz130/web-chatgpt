# 📝 Changelog

Tất cả thay đổi đáng chú ý của dự án sẽ được ghi lại tại file này.

Format dựa theo [Keep a Changelog](https://keepachangelog.com/vi/1.1.0/),
dự án tuân theo [Semantic Versioning](https://semver.org/lang/vi/).

## [0.1.0] - 2026-06-09

### Added
- Chat UI với cancel & edit controls, copy, regenerate.
- Server-side private user instructions (`server/user-instructions/`).
- Skills context handling — 10 skills (translator, proofreader, resume, email, v.v.).
- Chat layout refinement + default model.
- Demo preview mode (mock responses, không cần API key).
- Image generation với fallback `gpt-image-2` → `gpt-image-1.5`.
- Document export: PDF (pdfmake), DOCX (docx), ZIP (jszip).
- Voice input qua Web Speech API.
- File upload (PDF, DOCX, TXT) với context injection.
- Task templates trong `src/data/tasks.ts`.
- Deploy config cho Vercel (`vercel.json`) + Render (`render.yaml`).

### Stack
- React 19 + TypeScript 5.8 (strict)
- Vite 7
- OpenAI Responses API + Images API
- Node.js 18+ proxy (vanilla `http`)
