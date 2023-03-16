---
title: Obsidian + Storj S3
description: Sử dụng Storj S3 để sao lưu và đồng bộ hóa các flashcards và notes của bạn trong Obsidian.
summary: Sử dụng Storj S3 để sao lưu và đồng bộ hóa các flashcards và notes của bạn trong Obsidian.
date: 2023-01-19
series: ["Obsidian"]
series_order: 2
cover:
    image: feature.jpeg
categories:
    - guides
    - obsidian
---
{{< lead >}}
Sử dụng Storj S3 để sao lưu và đồng bộ hóa các flashcards và notes của bạn trong Obsidian.
{{< /lead >}}
Trong các lựa chọn lưu trữ (Dropbox/OneDrive/Obsidian Sync/S3) thì mình chọn dùng Storj S3 vì:

- So với các lựa chọn khác thì S3 (Simple Storage Service) có giá rất mềm, thậm chí nhiều nhà cung cấp cho người dùng một khoản dung lượng lưu trữ miễn phí như Scaleway (75GB free) hay Backblaze B2 (10GB free).
- Storj S3 có các máy chủ (node) trên toàn thế giới, đặc biệt là ở châu Á - Thái Bình Dương (AP1), so với các lựa chọn miễn phí khác đa phần chỉ có ở EU/US.
- Storj S3 cho người dùng dung lượng lưu trữ miễn phí rất khủng: 150GB. Nếu người dùng sử dụng hơn 150GB thì giá cũng rất mềm ($4/TB)

Bài viết sẽ hướng dẫn các bạn setup Storj để đồng bộ dữ liệu cho Obsidian.

## Tạo tài khoản & Bucket

1. Đăng kí tài khoản Storj để nhận 150GB miễn phí: Storj - Sign Up - nhớ chọn "Region: `AP1`" như hình để có tốc độ tốt nhất cho châu Á, sau đó nhập thông tin tài khoản và bấm Sign Up.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-region.png"></p>

2. Vào email đã nhập ở bước 2 để xác minh email, sau đó chọn `Continue in Web`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-new-project.png"></p>

3. Chọn `New Bucket`. Sau đó nhập tên Bucket (`bucket` giống như một thư mục vậy, dùng để chứa các file khác). Ở bước Encryption các bạn chọn `Enter Passphrase` rồi `Continue`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-encryption.png"></p>

4. Nhập mật khẩu cho bucket. Khuyến nghị dùng mật khẩu an toàn. Nhớ lưu lại mật khẩu này vì nếu mất thì sẽ không truy cập được dữ liệu trong bucket nữa. Mật khẩu này sẽ được sử dụng ở bước 2.2. Tick vào ô `I understand, ...` rồi chọn `Continue` là xong, đã tạo được 1 bucket dành riêng cho Obsidian.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-passphrase.png"></p>

Lưu ý là Bucket các bạn vừa tạo chỉ được dùng để đồng bộ hóa Obsidian. Nếu cần lưu trữ dữ liệu khác các bạn phải tạo Bucket khác theo các bước như trên. Tổng dung lượng của các Bucket không được quá 150GB nếu các bạn không muốn phải trả tiền.

## Tạo Access Key cho Storj

1. Ở menu chính bên tay trái, chọn `Access`, sau đó chọn `Create S3 Credentials`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-access.png"></p>

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-create-credentials.png"></p>

2. Trong hộp thoại hiện ra, các bạn điền tên là `obsidian` ở phần `Name`, chọn `All` ở phần `Permissions`, rồi chọn tên bucket các bạn đã tạo ở bước 1.3 (vd của mình là `phuctran-obsidian`) ở phần `Buckets`, sau đó nhấn `Encrypt my access`. 

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-create-access.png"></p>

3. Chọn `Create my own passphrase` sau đó nhập password như ở bước 1.4, chọn `Download.txt`, sau đó tick vào ô `I understand ...` rồi chọn `Create my access`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-encryption-key.png"></p>

4. Các bạn sẽ thấy `Access Key` và `Secret Key` được tạo cùng với `Endpoint`. Chọn `Download as .txt` để tải về. <mark>Đây là lần duy nhất các bạn sẽ thấy được Access Key và Secret Key</mark>, nên phải giữ kỹ file `s3-credentials[...].txt` vừa tải về. Nếu làm mất các bạn sẽ phải tạo Access Key mới để sử dụng.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/storj-keys.png"></p>

## Cài plugin

1. Mở Obsidian lên, vào `Settings` (biểu tượng dưới cùng bên tay trái), chọn `Community plugins` > `Turn on community plugins` (nếu cần) > `Browse`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/obsidian-community.png"></p>

2. Tìm và chọn plugin `Remotely Save`, `Install` > đợi cài đặt xong > `Enable` > `Agree`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/obsidian-remotely-save.png"></p>

3. Quay lại `Settings` > `Remotely Save`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/remotely-save-settings.png"></p>

4. Điền theo hướng dẫn:
- `Choose a remote service`: chọn `S3 or compatible`
- `Endpoint`: https://gateway.storjshare.io
- `Region`: `us-east-1`
- `Access Key ID`: `Access Key` đã lưu ở bước 2.4
- `Secret Access Key`: `Secret Key` đã lưu ở bước 2.4
- `Bucket Name`: tên của Bucket ở bước 1.3
- `S3 URL Style`: đổi thành `Path-style`
- Bấm nút `Check` ở mục `Check connectivity`, nếu điền tất cả thông tin đúng sẽ hiện thông báo `Great! The bucket can be accessed.`

5. Về màn hình chính của Obsidian, mở Command Palette (`Ctrl+P` trên máy tính hoặc kéo xuống trên điện thoại/máy tính bảng khi đang ở đầu trang), gõ `Remotely Save` và chọn option `Remotely Save: Start Sync`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/remotely-save-command.png"></p>

6. Lặp lại các bước 3.1-3.5 trên tất cả thiết bị.
7. Xong!

Các bạn có thể sync thủ công như bước 3.5 mỗi lúc cần hoặc thiết lập tự động đồng bộ hóa trong `Settings` > `Remotely Save` > `Basic Settings` > `Schedule for Auto Run` và `Run Once on Startup Automatically`

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-storj/remotely-save-autorun.png"></p>
