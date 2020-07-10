# Thực hiện một số thao tác với tag trong Git

- **Thực hiện:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

- **Thời gian:** Ngày 26 tháng 08 năm 2017

## Tài liệu tham khảo

- [How to delete a git remote tag?](https://stackoverflow.com/questions/5480258/how-to-delete-a-git-remote-tag)

## Nội dung thực hiện

1. **Tạo tag trong Git**

   - Tạo một `tag` có tên là `tagname` và không có chú thích trong Git với lệnh sau:

   ```bash
   git tag tagname
   ```

   - Tạo một `tag` có tên là `tagname` và có thêm chú thích trong Git với lệnh sau:

   ```bash
   git tag -a tagname -m "message"
   ```

1. **Push tag lên remote**

   - Push `tag` có tên là `tagname` lên `remote`:

   ```bash
   git push origin master tagname
   ```

1. **Xóa tag trong Git**

   - Xóa `tag` có tên là `tagname` trên `remote` (Github, Bitbucket,...):

   ```bash
   git push --delete origin tagname
   ```

   - Xóa `tag` có tên là `tagname` trên `local` (máy tính cá nhân,...):

   ```bash
   git tag --delete tagname
   ```
