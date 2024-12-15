### Hướng dẫn chạy notebook sử dung docker
----------------------------------------------------------
Trước khi thưc hiện các bước sau hãy đảm bảo máy bạn đã được cài đặt docker.

1. Mở Terminal và di chuyển vào thư mục chứa Dockerfile.
   
2. Chạy lệnh sau để build docker image, quá trình build image sẽ có thể mất khoảng 2 - 3 phút.
```
docker build -t notebook .
```

3. Kiểm tra xem đã có image chưa sử dụng lệnh sau và tìm image có tên là "notebook".
```
docker images
```

4. Nếu đã có image thì sử dụng lệnh sau để build container.
```
docker run --name my-notebook -p 8888:8888 notebook
```

5. Khi chạy xong lệnh container sẽ được khởi chạy ngay lập tức và chỉ cần copy địa chỉ localhost dán vào web browser để truy cập. Thông thường địa chỉ sẽ nằm sau dòng "Or copy and paste one of these URLs:" và thường có dạng là "http://127.0.0.1:8888/tree?...".
   
6. Sau khi build thành công để kiểm tra xem có đang khởi chạy container đó không sử dụng lệnh.
```
docker ps
```

7. Để dừng chạy container có thể làm theo các bước sau.
   - Sử dụng lệnh sau và tìm "CONTAINER ID" của container có tên là "my-notebook" và copy lại.
    ```
    docker ps -a
    ```

   - Sau khi đã có "CONTAINER ID" ta sử dụng lệnh sau để dừng container, thay container-id thành id vừa copy và chạy lệng.
    ```
    docker stop container-id
    ```
    