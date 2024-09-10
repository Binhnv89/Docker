# Docker
Là nền tảng cho developers và sysadmin để phát triển, triển khai và chạy ứng dụng với vùng chứa. Nó cho phép tạo môi trường độc lập và tách biệt để khởi chạy và phát triển ứng dụng và môi trường này gọi là container.
Khi cần triển khia bất kỳ máy chủ nào chỉ cần chạy container của Docker thì ứng dụng sẽ được khởi chạy ngay lập tức.
# Kiến trúc của Docker
Kiến trúc của Docker dựa trên mô hình client-server, giúp phát triển, triển khai, và quản lý các container ứng dụng 1 cách hiệu quả và dễ dàng.
## Các thành phần chính trong kiến trúc của Docker là:
- Docker Client : Là giao diện người dùng sử dụng để tương tác với Docker.
    + Các lệnh của Docker Client: docker build, docker run, docker pull sẽ được chuyển đến Docker Daemon xử lý.
    + Docker Client có thể giao tiếp với nhiểu Docker Daemon
      
- Docker daemon : Là thành phần chính chịu trách nhiệm quản lý Docker containers, images, networks, và volumes.Daemon lắng nghe các yêu cầu từ Docker Client và thực hiện các yêu cầu đó.
-  Nhiệm vụ:
  + Tạo, khởi động và dừng các container
  + Tải và quản lý các Docker images
  + Quản lý việc mạng (network) và volumes giữa các container

- Docker Image: Là bản mô tả không thay đổi của 1 ứng dụng và các thành phần cần thiết của nó. Mỗi image chứa nhiều lớp được sắp xếp theo thứ tự, và Docker sử dụng lớp này để tạo container.

- Docker Container: Là 1 phiên bản đang chạy của 1 Docker Image. Nó bao gồm tất cả những gì cần thiết để ứng dụng có thể chạy độc lập. Container chia sẻ kernel của hệ điều hành nhưng được cách ly với các container khác, đảm bảo tính nhất quán và bảo mật.

- Docker Registry: Là nơi lưu trữ Docker Images.
  + Docker Hub là 1 Docker Registry công cộng phổ biến nhất, nơi người dùng có thể tải lên hoặc tải về các images.
  + Khi bạn sử dụng lệnh docker pull hoặc docker push, Docker Client sẽ tương tác với Docker Registry.

- Docker Compose: là công cụ giúp định nghĩa và chạy các ứng dụng Docker multi-container. Thay vì chạy từng file 1 thì chúng ta có thể gộp 1 file docker-composer.yml và chạy 1 lệnh để khởi chạy toàn bộ hệ thống.

- Docker Network và Volumes:
  + Docker Network: Docker cung cấp cơ chế để kết nối các container với nhau hoặc với thế giới bên ngoài thông qua mạng. Mỗi container có thể được đặt vào một hoặc nhiều mạng tùy vào cấu hình của bạn.
  + Docker Volumes: Volumes cho phép lưu trữ dữ liệu ngoài container. Điều này giúp giữ lại dữ liệu ngay cả khi container bị xóa hoặc tắt.
