# 🔒 Security Policy

## Reporting a Vulnerability

**KHÔNG tạo public issue** cho lỗ hổng bảo mật. Gửi qua GitHub profile của maintainer.

Bao gồm:
- Mô tả lỗ hổng
- Các bước tái hiện
- Mức độ ảnh hưởng
- Đề xuất fix (nếu có)

## ⚠️ QUAN TRỌNG — Secrets

**KHÔNG BAO GIỜ** commit:

- `OPENAI_API_KEY` thật
- File `.env` (đã gitignore, nhưng check trước khi push)
- Token, password, hoặc bất kỳ secret nào

### Quy tắc Vite env

- **`VITE_*` prefix → expose ra browser bundle** (client-side)
- **Không prefix → chỉ server-side** (Node proxy)

→ `OPENAI_API_KEY` **KHÔNG ĐƯỢC** có prefix `VITE_`. Chỉ dùng prefix này cho URL public (proxy URL).

Nếu đã commit nhầm:
1. **Rotate** key ngay tại [platform.openai.com](https://platform.openai.com/api-keys)
2. Dùng `git filter-repo` hoặc BFG Repo-Cleaner để xóa khỏi history
3. Force-push và thông báo co-author

## Best Practices

- Validate mọi user input server-side (proxy `server/proxy.mjs`)
- Giới hạn upload size qua `MAX_REQUEST_BODY_BYTES` (mặc định 25MB)
- Set `Content-Security-Policy` header khi deploy production
- Bật HTTPS cho mọi deploy
