---
title: "Beginner's guide to torrents"
date: 2023-03-09T18:04:49+07:00
summary: "Sử dụng phương thức BitTorrent để tải dữ liệu"
description: "Sử dụng phương thức BitTorrent để tải dữ liệu"
draft: true
---
{{< lead >}}
Hướng dẫn sử dụng torrent để tải content trên internet
{{< /lead >}}

## Các khái niệm

{{< alert >}}
Đây chỉ là miêu tả các khái niệm của phương thức mạng ngang hàng (P2P) dành cho những bạn tò mò, nếu cảm thấy không cần thiết các bạn có thể skip tới phần hướng dẫn.
{{< /alert >}}

### Phương thức mạng

Phương thức mạng là "ngôn ngữ" của các máy tính để nói chuyện với nhau. Một phương thức mà có lẽ bất kì ai sử dụng internet đều đã thấy qua là HTTPS (HyperText Transfer Protocol Secure). Phương thức HTTPS thường bao gồm một máy chủ (server) và các người dùng (clients) giao tiếp với nhau. Tất cả người dùng sẽ giao tiếp với máy chủ để có thể trao đổi dữ liệu và thông tin, nhưng không thể giao tiếp trực tiếp với các người dùng khác.

{{< mermaid >}}
graph TD;
A[Server]-->B[Client 1];
A-->C[Client 2];
A-->D[Client 3];
linkStyle 0 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 1 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 2 stroke:#00FF00,stroke-width:4px,color:red;
{{< /mermaid >}}


Ngoài HTTPS, một số phương thức thông dụng khác bao gồm: SSH, FTP, BitTorrent, v.v.

### Phương thức P2P

Khác với phương thức HTTPS, các phương thức P2P (peer-to-peer) không có sự phân chia giữa máy chủ - người dùng. Thay vào đó, tất cả máy tính (peers) trong mạng lưới được coi như ngang hàng nhau. Khi đó, tất cả người dùng đều có thể giao tiếp với nhau mà không cần thông qua trung gian là máy chủ.

{{< mermaid >}}
graph LR;
A[Peer 1]-->B[Peer 2];
B-->C[Peer 3];
C-->D[Peer 4];
A-->C
A-->D
B-->D
linkStyle 0 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 1 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 2 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 3 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 4 stroke:#00FF00,stroke-width:4px,color:red;
linkStyle 5 stroke:#00FF00,stroke-width:4px,color:red;
{{< /mermaid >}}

Điểm mạnh của phương thức này là không cần có trung gian là máy chủ, người dùng có dữ liệu có thể chọn chia sẻ nó với các người dùng khác một cách tự do. Ngoài ra, một người dùng có thể tải từ nhiều peers cùng lúc để có thể đạt được tốc độ tải nhanh nhất.

#### BitTorrent

BitTorrent là phương thức P2P thông dụng nhất, thường được dùng để chia sẻ dữ liệu. Một mạng lưới BitTorrent sẽ bao gồm:
1. Uploader: là người dùng đầu tiên chia sẻ tập tin/dữ liệu đó
2. Seeder: là những người dùng đã tải xong tập tin/dữ liệu và sẵn sàng để chia sẻ tập tin/dữ liệu
3. Leecher: là những người dùng đang tải tập tin/dữ liệu

### File torrent

Để có thể tải tập tin bằng phương thức BitTorrent, chúng ta sẽ cần 2 thông tin:
1. Tập tin đó có ở mạng lưới nào
2. Trong mạng lưới đó, những người dùng cụ thể nào đang có tập tin chúng ta muốn tải

2 thông tin này sẽ được chứa trong các file có đuôi '.torrent' hoặc các 'magnet links'. Thông thường, khi một người muốn chia sẻ tập tin bằng phương thức BitTorrent, người đó sẽ tạo một file torrent có chứa các thông tin này rồi chia sẻ nó cho người khác.

### Tracker

Tracker là những trang web/forum để người dùng có thể chia sẻ các file torrent/magnet. Có 2 loại tracker:
1. Public trackers: những trang web chia sẻ torrent mà bất kì ai cũng có thể sử dụng
2. Private trackers: những trang web chia sẻ torrent cần được invited để tham gia

Điểm cộng của private trackers là những trang web này thường bắt buộc người dùng phải có khối lượng dữ liệu upload và download bằng nhau để tránh bị ban, do đó những file torrent trên những trackers này thường có nhiều seeders hơn, tốc độ tải cũng sẽ nhanh hơn. Tuy nhiên, để có thể sử dụng những trang web này, người dùng phải được thành viên của tracker mời, hoặc chờ tracker mở đăng kí cho thành viên mới.

Ở các nước châu Âu và Bắc Mỹ, việc sử dụng public trackers có thể khiến người dùng gặp rắc rối liên quan đến bản quyền. Để tải torrent từ public trackers, người dùng ở nước ngoài thường phải sử dụng VPN hoặc debrid.

Tuy nhiên, ở VN, tốc độ mạng thường không đủ cao để tận dụng các private trackers, và vấn đề bản quyền cũng không quan trọng mấy, nên việc sử dụng public trackers sẽ không mang lại nhiều bất lợi cho người dùng.

### Client

Để sử dụng phương thức BitTorrent, chúng ta cần một chương trình/ứng dụng có thể "giao tiếp" bằng phương thức này. Một số chương trình thường được dùng:
- QBitTorrent
- Deluge
- Transmission
- rTorrent/ruTorrent
- aria2c
- BiglyTorrent

Theo ý kiến cá nhân, QBitTorrent là chương trình vừa dễ sử dụng vừa có rất nhiều tính năng. Các chương trình torrent client có cách sử dụng căn bản tương đối giống nhau, các bạn có thể chọn bất kì chương trình nào các bạn thích.