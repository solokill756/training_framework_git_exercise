# 🧪 Git Training

Chào mừng bạn đến với khoá thực hành Git! Mục tiêu giúp bạn làm chủ các thao tác Git quan trọng trong teamwork.

## 🚀 Bài tập

### 1. Fork & clone repo bằng SSH
- Fork repo này về GitHub cá nhân
- Cài SSH key, test bằng: `ssh -T git@github.com`
- Clone repo về máy qua SSH

```bash
git clone git@github.com:<github-username>/training_framework_git_exercise.git
```

### 2. Tạo commit theo yêu cầu
- Tạo nhánh mới từ master
```
git checkout -b feature/demo
```

- Mở file src/app.js và sửa đổi nội dung
```bash
console.log('Welcome to Git!')
```
Thêm commit:
🟢 Commit 1 với messages, 'Commit 1'

- Mở file src/app.js và sửa đổi nội dung
```
console.log('Welcome to Git edited!')
```
Chỉnh sửa commit: Sửa lại message commit đầu tiên (dùng --amend) với messages 'Commit 1 edit'

- Thực hiện push nhánh feature/demo lên github và tạo pull request vào repo fork

### 3. Tạo file .gitignore
```
node_modules/
.env
temp/
```
Sau đó tạo file .env, rồi chạy git status để xem trang thái

### 4. Tạo pull request có conflict
- checkout về master
- Tạo nhánh mới từ master
```
git checkout -b feature/conflict-demo
```

- Sửa nội dung dòng đầu trong src/app.js
```
console.log("Xin chào thế giới! Edit feature");
```

- commit
```
git commit -am "Tạo conflict trong app.js"
git push origin feature/conflict-demo
```

- checkout về master
- Sửa nội dung dòng đầu trong src/app.js
```
console.log("Xin chào thế giới! Edit master");
```

- commit
```
git commit -am "Tạo thay đổi mới trong master"
git push origin master
```


- Thực hiện tạo pull request từ nhánh feature/conflict-demo sang master ở repo fork
- Lúc này sẽ xuất hiện conflic ở pull request, dùng rebase để fix conflic và push lên lại nhánh feature/conflict-demo

### 5. Tạo pull request sang repo gốc:
- Sau khi hoàn thành bài tập 2
- Thực hiện tạo pull request từ nhánh feature/demo ở repo fork vào nhánh master ở repo gốc


### 6. Cập nhật Pull Request Template
- Thêm 1 dòng trong file: .github/PULL_REQUEST_TEMPLATE.md
```
You are welcome!!
```

### 7. Thực hành các lệnh Git nâng cao
- Tương tự các bài tập trên
- Từ master checkout 1 nhánh mới là feature/demo
- Thêm 1 dòng mới trong file app.js để tạo thay đổi
- Thực hiện commit với messages "git advance"
- Thực hiện merge tại local
```
git checkout master
git merge feature/demo
```


- Tiếp theo tạo 3 commit mới, lần lượt là 'git advance 1', 'git advance 2', 'git advance 3'
- Thực hiện reset để quan sát sự thay đổi

```
git reset --soft HEAD~1    # Gỡ commit, giữ code + staging
git status
git log --oneline
```

```
git reset --mixed HEAD~1   # Gỡ staging, giữ code
git status
git log --oneline
```

```
git reset --hard HEAD~1    # Gỡ sạch cả staging + code
git status
git log --oneline
```

- Thực hiện tạo sự thay đổi trong code
- Sau đó đưa code đang dang dở vào stash, và xem sự thay đổi
```
git stash -u        # Cất tạm thay đổi
git stash list      # Xem stash
git stash pop       # Lấy lại stash mới nhất
```