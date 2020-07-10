# Cách lấy lại file đã xóa trong commit trước đó

- Nguồn tham khảo: [Find and restore a deleted file in a Git repository](https://stackoverflow.com/questions/953481/find-and-restore-a-deleted-file-in-a-git-repository)

- Cách thực hiện:

```bash
$ git rev-list -n 1 HEAD -- <file_path>
5a5bf28dcd7944991944cc5076c7525439830122 <delete_commit>

$ git checkout <deleting_commit>^ -- <file_path>
```
