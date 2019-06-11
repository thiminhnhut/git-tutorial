# Git ignore file change mode

* **Thực hiện:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

* **Thời gian:** Ngày 11 tháng 06 năm 2018

## Tài liệu tham khảo

1. [How do I make Git ignore file mode (chmod) changes?](https://stackoverflow.com/questions/1580596/how-do-i-make-git-ignore-file-mode-chmod-changes)

## Nội dung thực hiện

### Git ignore file change mode

* Sử dụng lệnh:

    ``` bash
    $ git config core.fileMode false
    ```

    hoặc:

    ``` bash
    $ git config --global core.fileMode false
    ```