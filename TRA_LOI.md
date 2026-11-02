❓ **Câu 1.** Lúc mới nhận repo, nhánh `main` có bao nhiêu commit? Kể tên 4 nhánh còn lại.
Nhánh main có 7 commit
1.feature/giao-dien-moi
2.feature/tieu-de
3.feature/xuat-csv
4.hotfix/sua-loi-cong
❓ **Câu 2.** Bạn Lan có bao nhiêu commit trong toàn bộ repo (gợi ý: thêm `--all`)?
- 7 commit 
❓ **Câu 3.** Dòng có chữ `reduce` trong `js/tinh-toan.js` do ai viết, ở commit nào?
Lê Hùng - commit mã df17ab7d
❓ **Câu 4.** `git diff` và `git diff --staged` khác nhau thế nào? Vì sao file `.env` không bao giờ nên đưa lên Git?
- git diff: Xem những thay đổi chưa được đưa vào Staging.
- git diff --staged: Xem những thay đổi đã được đưa vào Staging, đang chờ commit.
- Vì file .env thường chứa thông tin bí mật như mật khẩu, API key, thông tin kết nối database. Nếu đưa lên GitHub, người khác có thể xem và sử dụng những thông tin đó.
❓ **Câu 5.** Vì sao 3.1 là fast-forward còn 3.2 lại tạo merge commit?
- 3.1 là fast-forward vì nhánh feature/gioi-thieu được tạo từ main và chưa có commit riêng trên main trong lúc đó. Git chỉ cần di chuyển con trỏ main lên commit mới.
- 3.2 tạo merge commit vì hai nhánh đã có lịch sử phát triển riêng, cần một commit để ghi nhận việc gộp.
❓ **Câu 6.** Vì sao gộp `feature/giao-dien-moi` không xung đột, còn `feature/tieu-de` thì có?
- Gộp feature/giao-dien-moi không xung đột vì hai nhánh sửa những phần khác nhau của file. Gộp feature/tieu-de bị xung đột vì cả hai cùng sửa một dòng tiêu đề h1 trong index.html.
❓ **Câu 7.** Vì sao dùng `git revert` chứ không dùng `git reset` để gỡ commit đã có trên nhánh chung?
- Dùng git revert vì lệnh này tạo commit mới để đảo ngược thay đổi của commit cũ, không xóa lịch sử. git reset có thể làm thay đổi lịch sử nhánh, gây ảnh hưởng đến những người khác.
❓ **Câu 8.** `reset --soft`, `reset --mixed` (mặc định) và `reset --hard` khác nhau thế nào?
reset --soft: Xóa commit nhưng giữ thay đổi trong staging.
reset --mixed: Xóa commit, đưa thay đổi về working directory, không còn trong staging.
reset --hard: Xóa commit và bỏ cả thay đổi trong working directory lẫn staging.
❓ **Câu 9.** Commit gây lỗi là commit nào (mã, thông điệp, tác giả)? Dùng `git show <mã>` và giải thích ngắn gọn vì sao code đó gây lỗi.
❓ **Câu 10.** Nếu dùng `git merge hotfix/sua-loi-cong` thay cho `cherry-pick` thì chuyện gì xảy ra?
- Nếu merge hotfix/sua-loi-cong thì Git sẽ gộp tất cả commit trên nhánh hotfix, bao gồm cả commit sửa lỗi và commit thử font Comic Sans chưa được duyệt.
❓ **Câu 11.** Sau rebase, mã commit "Thêm hàm xuất CSV" có giống mã cũ không? Vì sao không nên rebase một nhánh mà bạn khác đã kéo về máy?
- Sau rebase, mã commit có thể khác mã cũ vì Git tạo commit mới trên nền main mới. Không nên rebase nhánh mà người khác đã kéo về máy vì sẽ làm thay đổi lịch sử commit và gây khó khăn khi đồng bộ.
❓ **Câu 12.** `git fetch` và `git pull` khác nhau thế nào?
- git fetch tải thông tin và commit mới từ remote về nhưng không tự gộp vào nhánh hiện tại. git pull vừa fetch vừa tích hợp thay đổi vào nhánh hiện tại.