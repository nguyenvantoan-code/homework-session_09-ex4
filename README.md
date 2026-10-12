# Bài 4: Lưu trữ dữ liệu đơn giản với Docker Volume

## 1. Tạo Volume

Lệnh thực hiện:

```bash
docker volume create easy-volume
```

Kết quả: Đã tạo Volume có tên `easy-volume`.

## 2. Ghi dữ liệu vào Volume

Lệnh thực hiện:

```bash
docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
```

Kết quả: Đã ghi dữ liệu vào tệp `/data/test.txt` trong Volume.

## 3. Đọc dữ liệu từ container thứ hai

Lệnh thực hiện:

```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

Kết quả mong đợi:

```text
Luu tru du lieu Docker
```

## 4. Kết luận

Đã tạo và sử dụng Docker Named Volume để lưu trữ dữ liệu. Dữ liệu vẫn tồn tại sau khi container ghi dữ liệu bị xóa, và container khác có thể đọc lại dữ liệu từ cùng Volume.