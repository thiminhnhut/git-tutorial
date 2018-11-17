# Git commit

* **Thực hiện:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

* **Thời gian:** Ngày 17 tháng 11 năm 2018

## Tài liệu tham khảo

1. [How do I remove a single file from the staging area of Git but not remove it from the index or undo the changes to the file itself?](https://stackoverflow.com/questions/1505948/how-do-i-remove-a-single-file-from-the-staging-area-of-git-but-not-remove-it-fro)

## Nội dung thực hiện

### Đưa file từ Staging Area sang Unstaged trong Git

* Đặt vấn đề: Một file đã được commit (ở trạng thái staging area), nếu muốn xóa file ra khỏi staging area nhưng không xóa file ra khỏi project và đưa file về trạng thái unstaged (không sử dụng lệnh `git rm file`).

* Sử dụng lệnh:

    $ git rm --cached FILE
