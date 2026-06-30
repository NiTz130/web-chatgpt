# 🤝 Đóng góp cho Web ChatGPT

## Quy trình

1. **Fork** repo và tạo branch: `git checkout -b feat/ten-tinh-nang`
2. **Cài** dependencies: `npm install`
3. **Dev**:
   ```bash
   npm run dev      # UI tại localhost:5173
   npm run api      # Proxy tại localhost:3001
   ```
4. **Build check**: `npm run build` (gồm `tsc --noEmit`)
5. **Commit** với [Conventional Commits](https://www.conventionalcommits.org/)
6. **Push** + mở PR vào `main`

## Quy tắc

- **Không commit** `OPENAI_API_KEY` thật — chỉ dùng `.env` (đã gitignore)
- **TypeScript strict** — không dùng `any` khi có thể tránh
- **Skills** mới → tạo folder `server/skills/<id>/SKILL.md` mô tả rõ use case
- **Không commit** `node_modules/`, `dist/`, `.env`, `.env.local`

## Commit Convention

```
<type>(<scope>): <description>

Types: feat, fix, docs, style, refactor, test, chore
```

**Ví dụ**:
```
feat(skills): add code-review skill
fix(proxy): handle image API timeout gracefully
docs(readme): add architecture diagram
```

## Báo lỗi

Mở issue với:
- Mô tả ngắn gọn
- Các bước tái hiện
- Screenshot (nếu UI)
- Browser + OS
- Log từ proxy (terminal chạy `npm run api`)
