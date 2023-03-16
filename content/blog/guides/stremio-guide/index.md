---
title: "Stremio guide"
description: Sử dụng Stremio để xem phim.
summary: Sử dụng Stremio để xem phim.
categories:
    - guides
date: 2023-02-22T10:25:40+07:00
draft: false
---
{{< lead >}}
Sử dụng ứng dụng Stremio để xem phim.
{{< /lead >}}
## Stremio

[Stremio](https://www.stremio.com) là một ứng dụng đa nền tảng để stream những file [torrent](https://vi.wikipedia.org/wiki/BitTorrent) có sẵn trên internet. Stremio tương thích với các thiết bị:
- Windows
- Android
- Android TV (lưu ý là phiên bản TV cần có một điện thoại Android hoặc máy tính Windows để setup)
- MacOS
- Linux

{{< alert cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" >}}
Stremio hiện chưa có trên hệ điều hành iOS/iPadOS.
{{< /alert >}}

Điểm mạnh của torrent là khi có bất kì file phim chất lượng cao trên internet (Netflix, HBO, Hulu, v.v.) hoặc đĩa (DVD, BluRay) nào đó, chỉ chừng nửa ngày sau sẽ có file torrent chất lượng cao **hoàn toàn miễn phí**. Tuy nhiên, một số phim như phim Hoa ngữ, Nhật ngữ, hay thậm chí Việt ngữ ít người upload hơn nên số lượng phim cũng ít hơn. Nhưng để xem phim tiếng Anh thì nguồn phim là vô tận nhé.

Stremio còn có một số addons như Trakt, OpenSubtitles, Subscene, v.v. để sử dụng khi xem phim. Nhưng bài viết này không nói về những addons đó, mà chỉ tập trung vào cách cài đặt Stremio để xem phim.

## Debrid

{{< alert icon="circle-info" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" >}}
Việc đăng kí mua debrid là **không cần thiết** để xem phim, nó chỉ cải thiện trải nghiệm của bạn. Stremio **hoàn toàn** có thể được sử dụng mà không có debrid.
{{< /alert >}}

Khi bạn tải torrent, đặc biệt là ở nước ngoài, bạn sẽ vi phạm một số *luật bảo vệ bản quyền* (<mark>ở VN không làm gắt chuyện này</mark>). Ngoài ra, vì torrent là phương thức *"tải ngang hàng"* (peer-to-peer/P2P), không có một máy chủ cố định, tốc độ tải torrent sẽ **phụ thuộc vào khoảng cách** giữa bạn và các người dùng khác có cùng file torrent đó (seeders).

Để tiện hơn và nhanh hơn, bạn có thể sử dụng *<mark>"debrid"</mark>*. Debrid là dịch vụ trung gian giữa người dùng và torrent/file hosters (Mediafire, MEGA, v.v.), với 2 chức năng chính:
1. **Unlock premium**: ở một số dịch vụ chia sẻ tập tin như MediaFire, MEGA, Fshare, v.v. bạn có lựa chọn trả tiền để nâng cấp tài khoản, tăng tốc độ tải dữ liệu. Thông qua debrid, bạn chỉ cần trả tiền 1 lần cho dịch vụ debrid để có tốc độ tải bằng với tài khoản premium ở một số trang. Lưu ý là không phải trang web nào cũng có thể unlock premium theo cách này.
2. **Torrent cache**: để người dùng không phải tải thẳng torrent về máy, debrid sẽ đứng ra làm trung gian và tải file torrent đó về máy chủ **gần người dùng nhất**, sau đó cung cấp cho người dùng một link HTTPS để nhận dữ liệu từ máy chủ. Cách này khiến người khác không thấy bạn nội dung bạn tải là gì, vì khác với phương thức P2P, **HTTPS có áp dụng mã hóa, không ai có thể thấy dữ liệu giữa máy chủ và người dùng**. Ngoài ra, một chức năng rất hữu dụng của debrid là nếu có torrent nhiều người tải, debrid sẽ tự lưu file đó về máy chủ mà không cần người dùng yêu cầu. Nghĩa là những phim nào hot đa phần đều sẽ **có sẵn** ở máy chủ gần bạn nhất, giúp tốc độ tải phim nhanh hơn.

Có 2 dịch vụ debrid giá rẻ và thông dụng nhất là [AllDebrid](https://alldebrid.com) và [Real-Debrid](https://real-debrid.com). Giá thành 2 dịch vụ này ngang ngửa nhau khi mua nhiều tháng cùng lúc nhưng AllDebrid sẽ rẻ hơn nếu đăng kí từng tháng. Cả hai đều có giá khoảng **<mark>80k/tháng</mark>**, rất hợp lí vì rẻ hơn đăng kí streaming nhiều và khác với các dịch vụ streaming như Netflix, torrent **không bị giới hạn số lượng phim** vì lí do bản quyền.

Tốc độ tải từ máy chủ gần nhất (Hong Kong hoặc Singapore) là tương đương, nhưng Real-Debrid có nhiều máy chủ hơn. Về chất lượng dịch vụ, mình đã xài qua cả 2 dịch vụ này và đều cảm thấy rất ổn, tốc độ đường truyền từ nhà mình (max 100Mbps) tới các máy chủ tại: 
- Hong Kong: `80Mbps`
- Singapore: `90Mbps`
- Cloudflare: `80Mbps`

Tốc độ này là đủ để xem phim Full HD không bị giật lag.

Ngoài 2 lựa chọn trên, một lựa chọn cũng rất tốt là [Premiumize](https://www.premiumize.me/), có bao gồm 1TB lưu trữ trên mây và hỗ trợ nhiều file hosters hơn, nhưng giá thành cũng sẽ cao hơn (gấp đôi nếu mua gói một năm).

Nếu có điều kiện tài chính và muốn xem phim mượt hơn, ổn định hơn, hoặc muốn tải torrent an toàn hơn, hãy cân nhắc mua một trong các gói debrid.

{{< alert icon="circle-info" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" >}}
Việc đăng kí mua debrid là **không cần thiết** để xem phim, nó chỉ cải thiện trải nghiệm của bạn. Stremio **hoàn toàn** có thể được sử dụng mà không có debrid.
{{< /alert >}}

## Cài đặt

Để xem phim miễn phí, chỉ cần cài đặt addon Torrentio. Trong ứng dụng Stremio đã có sẵn OpenSubtitles để cung cấp phụ đề. Nếu muốn các bạn có thể tự khám phá các addons khác.

1. Truy cập [Stremio](https://www.stremio.com/downloads) và tải phiên bản mà bạn muốn, hoặc cài đặt bằng Play Store nếu sử dụng Android/Android TV*
2. Đăng nhập/đăng kí tài khoản để bắt đầu sử dụng.
3. Cài đặt Torrentio [ở link này](https://torrentio.strem.fun/configure).
![install Torrentio](torrentio-install.jpeg#center)
  - Providers: Các nguồn torrent (mặc định: tất cả, không cần đổi)
  - Sorting: Cách sắp xếp kết quả (không cần đổi)
  - Priority foreign language: Ngoại ngữ ưa thích (không cần đổi)
  - Exclude qualities/resolutions: Các định dạng muốn bỏ qua (có thể chọn 4K, BluRay, HDR, Dolby Vision để loại những kết quả này vì dung lượng file khá lớn, tốn băng thông và tốc độ tải không nhanh)
  - Debrid provider: Nếu có mua gói debrid (xem phần Debrid trong bài viết này), click chọn tên dịch vụ và điền API Key (sau khi chọn dịch vụ cụ sẽ có hướng dẫn)
4. Bấm chọn Install

{{< alert "circle-info" >}}
*Android TV không tự cài addons được mà phải thông qua 1 thiết bị khác. Bạn đăng nhập Stremio trên điện thoại hoặc máy tính (tài khoản Stremio trên TV và thiết bị còn lại phải giống nhau), sau đó cài đặt Torrentio và các addons bạn muốn, rồi vào phần Add-Ons để đồng bộ hóa cài đặt.
{{< /alert >}}

## Sử dụng

1. Trong Stremio, chọn phim mà bạn muốn xem. Stremio sẽ tự tìm và cho bạn một danh sách các file torrent.
![stremio choose source](stremio-choose-stream.webp#center)
2. Chọn file mà bạn muốn sử dụng. Nên chọn những file 1080p (chất lượng Full HD) và có nguồn là `RARBG` hoặc `YTS` nếu có để dễ khớp phụ đề hơn.
3. Bật phụ đề: Chọn biểu tượng phụ đề, chọn English để bật. Nếu phụ đề không khớp (nhanh hơn/chậm hơn phim), chọn phụ đề khác hoặc chỉnh phần `Adjust timing` - `+` để phụ đề chậm hơn và `-` để phụ đề nhanh hơn.
![stremio subtitles](stremio-subtitles.webp#center)
4. Xem phim.