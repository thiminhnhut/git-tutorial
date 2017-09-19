# Giải quyết Conflict trong Git

* **Thực hiện:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

* **Thời gian:** Ngày 26 tháng 08 năm 2017

## Tài liệu tham khảo

## Nội dung thực hiện

* Conflict trong Git: Khi nhiều người cùng thay đổi một nội dung, người push lên remote server đầu tiên sẽ không có vấn đề gì, nhưng những người push lên remote server ở lần sau sẽ gặp vấn đề conflict - xung đột trong Git.

* Ví dụ về tình huống tạo Conflict:

	+ Người thứ nhất tạo file `test-conflict.md` có nội dung như sau và push lên remote server:

	```markdown
		# Tạo tình huống Conflict trong Git

		* Nội dung 1

		* Nội dung 2

		* Nội dung 3
	```

	+ Thự hiện đưa `test-conflict.md` lên remote server:

	```bash
	$ git add test-conflict.md
	$ git commit -m "Kiem tra Conflict trong Git"
	$ git push origin master
	```

	+ Người thứ 2, pull thay đổi từ remote server về local server và thay đổi nội dung của file `test-conflict.md` như sau và người thứ 2 cũng thực hiện push lên remote server.

	```markdown
		# Tạo tình huống Conflict trong Git

		* Nội dung 1

		* Thay đổi dòng này

		* Nội dung 3
	```

	+ Người thứ nhất lại thay đội nội dung của file `test-conflict.md` như sau:

	```markdown
		# Tạo tình huống Conflict trong Git

		* Nội dung 1

		* Nội dung 2: không cần phải update.

		* Nội dung 3
	```

	+ Người thứ nhất, tiến hành commit lại thay đổi trên file `test-conflict.md`:

	```bash
	$ git add test-conflict.md
	$ git commit -m "Noi dung khong can thay doi"
	$ git push origin master
	To https://github.com/thiminhnhut/git-tutorial.git
	 ! [rejected]        master -> master (fetch first)
	error: failed to push some refs to 'https://github.com/thiminhnhut/git-tutorial.git'
	hint: Updates were rejected because the remote contains work that you do
	hint: not have locally. This is usually caused by another repository pushing
	hint: to the same ref. You may want to first integrate the remote changes
	hint: (e.g., 'git pull ...') before pushing again.
	hint: See the 'Note about fast-forwards' in 'git push --help' for details.
	```

	+ Người thứ nhất không push lên được remote server, do nội dung trên remote server đã được thay đổi: cách giải quyết như sau: Lấy nội dung mới trên remote server về và gộp vào nội dung dưới local server rồi push nội dung lên remote server để được nội dung mới nhất.

	```bash
	$ git fetch
	$ git merge origin/master
	Auto-merging tutorials/test-conflict/test-conflict.md
	CONFLICT (content): Merge conflict in tutorials/test-conflict/test-conflict.md
	Automatic merge failed; fix conflicts and then commit the result.
	```
	+ Xuất hiện thông báo xảy ra conflict ở file `tutorials/test-conflict/test-conflict.md`. Cần giải quyết conflict rồi push lên remote server.

	+ Giải quyết conflict:

		- Nội dung của file `tutorials/test-conflict/test-conflict.md` như sau:

		```markdown
			# Tạo tình huống Conflict trong Git

			* Nội dung 1

			<<<<<<< HEAD
			* Nội dung 2: không cần phải update.
			=======
			* Thay đổi dòng này
			>>>>>>> origin/master

			* Nội dung 3
		```

		- Nội dung nằm giữa `<<<<<<<` và `>>>>>>>` là phần xung đột. Giữ lại nội dung thay đổi phù hợp nhất (trao đổi, liên lạc,...). Sau khi xóa nội dung gây conflict, được nội dung như sau:

		```markdown
			# Tạo tình huống Conflict trong Git

			* Nội dung 1

			* Nội dung 2: không cần phải update.

			* Nội dung 3
		```

		- Người thứ nhất, tiến hành commit lại thay đổi trên file `test-conflict.md` và có thể push lên được remote server:

		```bash
		$ git add test-conflict.md
		$ git commit -m "Giai quyet conflict"
		$ git fetch
		$ git merge origin/master
		$ git push origin master
		```

* Giải quyết vấn đề như sau:

	+ Thực hiện các lệnh bên dưới trước:

	```bash
	$ git fetch
	$ git merge origin/master
	```
	+ Nếu xảy ra conflict thì giải quyết như ví dụ (tìm xóa nội dung cho phù hợp), rồi push lên remote server.

	+ Nếu không xảy ra conflict thì push lên remote server.
