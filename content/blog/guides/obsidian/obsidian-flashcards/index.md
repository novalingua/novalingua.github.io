---
title: Obsidian flashcards
description: Sử dụng ObsidianMD để tạo flash cards.
summary: Sử dụng ObsidianMD để tạo flash cards.
date: 2023-01-19
series: ["Obsidian"]
series_order: 1
cover:
    image: feature.jpeg
categories:
    - guides
    - obsidian
---
{{< lead >}}
Sử dụng ObsidianMD để tạo flash cards.
{{< /lead >}}
Có nhiều các ứng dụng khác chuyên dùng cho phương pháp lặp lại ngắt quãng như Anki, Mochi, v.v. Tuy nhiên mình chọn Obsidian vì 4 lí do:

1. Obsidian có app cho **tất cả hệ điều hành thông dụng**: Windows, MacOS, iOS, Android, thậm chí cả Linux. Tất cả phiên bản này đều **free**.
2. Obsidian sử dụng **thuật toán** spaced repetition tương tự thuật toán của Anki - một ứng dụng học flashcards rất hiệu quả và thông dụng.
3. Có thể dễ dàng **đồng bộ hóa** các flashcards (và các ghi chú khác) giữa các thiết bị **hoàn toàn miễn phí** thông qua Obsidian + plugin + Dropbox/OneDrive/S3. Do đó người học có thể tạo flashcards trên máy tính và học trên điện thoại ở khắp mọi nơi.
4. Ngoài chức năng flashcards, Obsidian có chức năng chính là một ứng dụng để ghi chép notes. Do vậy nó có rất nhiều chức năng khác và người học có thể sử dụng Obsidian như một **hệ thống quản lý kiến thức cá nhân** (Personal Knowledge Management System) để phục vụ cho học tập hay công việc của mình (tương tự như Notion, Keep, OneNote, v.v.).

Obsidian là app miễn phí nhưng có lựa chọn sử dụng dịch vụ "Obsidian Sync" để đồng bộ hóa dữ liệu - nhưng theo mình nên dùng plugin để đỡ tốn chi phí (miễn phí vs $10/tháng cho Obsidian Sync). Nếu các bạn dùng plugin Remotely Save (miễn phí) cùng với OneDrive (miễn phí 15GB) sẽ lưu trữ & đồng bộ được ~ 3 triệu notes (trung bình 1 note = 1000 từ), Backblaze B2 (miễn phí 10GB) được ~2 triệu notes, Storj (miễn phí 150GB) được ~30 triệu(!) notes. Guide

Cách tạo flashcards trong Obsidian:

## Cài đặt plugin Spaced Repetition

1. Mở Obsidian lên, vào `Settings` (biểu tượng dưới cùng bên tay trái), chọn `Community plugins` > `Turn on community plugins` (nếu cần) > `Browse`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/obsidian-community.png"></p>

2. Tìm `Spaced Repetition`, chọn `Install` sau đó `Enable`.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/spaced-repetition.png"></p>

## Tạo flashcards

1. Tag 1 note chứa flashcard bằng #flashcards/tên-note.
2. Mỗi cặp từ vựng + định nghĩa các bạn gõ lại thành `từ vựng:::định nghĩa`. Khi sử dụng 2 dấu hai chấm (`::`) thì app sẽ chỉ hỏi bạn từ vựng, bạn trả lời định nghĩa. Sử dụng 3 dấu hai chấm (`:::`) thì app sẽ hỏi bạn từ vựng hoặc định nghĩa và bạn trả lời cái còn lại.
3. Nên tạo note theo tuần. (VD: mỗi ngày học 20 từ thì tạo luôn 1 note 140 từ của tuần đó)

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/obsidian-flashcards.png"></p>

## Sử dụng flashcards để ôn từ vựng

1. Chọn `Review flashcards` bên tay trái
- Trên điện thoại Android/iOS mở plugin bằng cách:
	1. Chọn biểu tượng 3 gạch ngang ở góc dưới cùng bên tay phải
	2. Chọn `Review flashcards`

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/review-flashcards.png"></p>

2. Chọn `flashcards` để ôn lại từ vựng trong tất cả note hoặc bấm mũi tên và chọn `tên-note` để ôn lại từ vựng trong note đó.

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/flashcards-decks.png"></p>

3. Ở mỗi từ vựng/định nghĩa, các bạn cố gắng nhớ từ/định nghĩa tương ứng là gì, sau đó nhấn Show Answer (hoặc spacebar trên bàn phím).

<p align=center><img src="https://neolingo.b-cdn.net/obsidian-flashcards/flashcard-question.png"></p>

4. Chọn theo mức độ khó của từ: 
	- Đỏ - Hard: khó nhớ hoặc không nhớ. Từ/định nghĩa sẽ được hỏi lại sau 1 ngày.
	- Bình thường - Good: tạm thời nhớ. Từ/định nghĩa sẽ được hỏi lại sau 2.5 ngày.
	- Dễ - Easy: Nhớ dễ, nhanh. Từ/định nghĩa sẽ được hỏi lại sau 3.5 ngày.

5. Khoảng 2-3 ngày nên mở lên ôn lại một lần, tới cuối tuần mở lên lần cuối để chắc chắn mình đã thuộc.
