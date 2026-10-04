# mua proxy theo GB: cách tính dung lượng, so sánh toàn bộ gói GB của 9Proxy và mẹo không để phí traffic

“Mua proxy theo GB” nghe đơn giản: trả tiền cho dung lượng, dùng bao nhiêu tính bấy nhiêu, không cần cam kết tháng. Nhưng lúc mở trang thanh toán thì câu hỏi thật mới hiện ra. Nên bắt đầu ở 5 GB hay nhảy thẳng lên 100 GB? Chênh lệch giá trên mỗi GB giữa các gói lớn đến mức nào? Và nếu công việc không chạy đều, phần dung lượng mua dư có bị bốc hơi không?

Bài này trả lời theo thứ tự đó, dùng 9Proxy làm ví dụ cụ thể vì đây là nhà cung cấp có cả mô hình tính theo GB lẫn theo IP, nên có thể so sánh trực tiếp.

## Mua proxy theo GB khác gì mua theo IP

Hai mô hình này không phải bản nâng cấp của nhau, chúng giải hai bài toán khác nhau.

| Tiêu chí | Gói theo GB | Gói theo IP |
| --- | --- | --- |
| Cách tính tiền | Trả theo tổng dung lượng | Trả theo số lượng IP |
| Giới hạn traffic | Có, hết GB là dừng | Không giới hạn trong thời gian IP hoạt động |
| Số endpoint tạo được | Không giới hạn | 1 IP = 1 lượt dùng khi forward |
| Vòng đời IP | Xoay tự động theo request/session | Vài giờ tới 24 giờ, tùy IP |
| Cách chạy | Trực tiếp trên dashboard | Cần app desktop (local port forwarding) |
| Xác thực | Username/password hoặc IP whitelist | Qua app, có thể kèm xác thực proxy |

Điểm dễ hiểu sai nhất nằm ở cột “giới hạn traffic”. Gói theo IP nhìn qua có vẻ hào phóng vì băng thông không tính, nhưng bạn bị chặn bởi số IP — hết IP là hết việc. Gói theo GB thì ngược lại: bạn tạo bao nhiêu endpoint cũng được, miễn còn dung lượng trong tài khoản.

Nói cách khác, mua theo GB là mua **quyền xoay IP không giới hạn**, trả tiền bằng dữ liệu đi qua. Còn mua theo IP là mua **băng thông không giới hạn**, trả tiền bằng số điểm truy cập.

## Khi nào nên mua proxy theo GB, khi nào không

Mô hình GB hợp với công việc có hai đặc điểm: mỗi request truyền ít dữ liệu, và cần đổi IP liên tục.

Ví dụ cụ thể: kiểm tra giá hiển thị theo từng thành phố, kiểm tra quảng cáo có phân phối đúng khu vực không, thu thập dữ liệu từ các trang nhẹ, polling API, hoặc các tác vụ MMO cần nhiều danh tính mạng khác nhau nhưng không kéo về lượng dữ liệu lớn.

Ngược lại, nếu công việc của bạn là tải hàng trăm GB mỗi tháng qua một số ít phiên ổn định, gói theo IP thường rẻ hơn nhiều vì bạn không phải trả cho từng gigabyte. Cùng một khoản tiền, mô hình IP cho bạn băng thông không giới hạn miễn là IP còn sống.

Một cách tự kiểm tra nhanh: nếu bạn thấy khó ước lượng “tháng này dùng hết bao nhiêu GB”, phần lớn khả năng bạn đang ở nhóm phù hợp với gói theo GB — vì chính sự thất thường đó là lý do mô hình trả theo dữ liệu tồn tại.

> Gói theo GB không có nghĩa là “rẻ hơn”. Nó chỉ có nghĩa là “không trả cho phần mình không dùng”. Với workload chạy đều và nặng, hai điều này là hai chuyện khác nhau.

## Proxy theo GB của 9Proxy hoạt động thế nào

Theo tài liệu chính thức của 9Proxy, mô hình Residential Proxy by GB hoạt động như sau:

- Bạn mua một gói tính bằng GB (ví dụ 50 GB, 200 GB), dung lượng này là hạn mức duy nhất bị trừ dần.
- Trong phạm vi dung lượng còn lại, bạn tạo được **không giới hạn số endpoint**.
- Có hai chế độ session: **sticky** (giữ nguyên IP trong khoảng thời gian bạn cấu hình) và **rotating** (đổi IP theo request hoặc theo session).
- Xác thực bằng username/password hoặc IP whitelist — không cần mật khẩu nếu bạn whitelist IP thiết bị.
- Nhắm mục tiêu theo quốc gia, tiểu bang, thành phố, ZIP hoặc ISP.
- Toàn bộ thao tác nằm trong dashboard, không cần cài app.

Hạ tầng mà 9Proxy công bố là hơn 20 triệu IP dân cư trải trên hơn 90 quốc gia. Thời hạn sử dụng của gói GB là **180 ngày** theo tài liệu, riêng chương trình Enterprise thì không giới hạn thời hạn.

Chi tiết đáng chú ý cho người làm nhóm: Enterprise có chế độ team 1 owner + tối đa 5 member, chia sẻ dung lượng trong nội bộ không bị tính hạn 180 ngày, có log hoạt động và giới hạn traffic theo từng thành viên.

## Bảng giá toàn bộ gói GB của 9Proxy

Đây là bảng giá niêm yết cho các gói theo dung lượng. Cột “tổng” là số tiền bạn trả một lần, không phải phí định kỳ.

| Gói | Giá mỗi GB | Tổng | Hiệu lực | Mua |
| --- | --- | --- | --- | --- |
| 5 GB | $3,00 | $15 | 180 ngày | [ Mua gói 5 GB để test trước](https://bit.ly/9-Proxy) |
| 50 GB + tặng 5 GB | $2,10 | $105 | 180 ngày | [ Mua gói 50 GB kèm 5 GB tặng](https://bit.ly/9-Proxy) |
| 100 GB | $1,50 | $150 | 180 ngày | [ Mua gói 100 GB](https://bit.ly/9-Proxy) |
| 200 GB | $1,00 | $200 | 180 ngày | [ Mua gói 200 GB](https://bit.ly/9-Proxy) |
| 1.000 GB | $0,80 | $800 | 180 ngày | [ Mua gói 1.000 GB](https://bit.ly/9-Proxy) |
| 2.000 GB | $0,75 | $1.500 | 180 ngày | [ Mua gói 2.000 GB](https://bit.ly/9-Proxy) |
| 10.000 GB | $0,68 | — | 180 ngày | [ Xem giá gói 10.000 GB tại trang thanh toán](https://bit.ly/9-Proxy) |

Vài điểm cần đọc đúng ở bảng trên:

**Đơn giá giảm rất nhanh ở những bậc đầu.** Từ 5 GB xuống 100 GB, giá mỗi GB giảm một nửa ($3,00 → $1,50). Nhưng từ 200 GB trở lên, mức giảm bắt đầu thoải — 200 GB và 2.000 GB chỉ chênh nhau 25% đơn giá, dù tổng tiền chênh gấp 7,5 lần.

**Gói 50 GB là gói duy nhất có bonus.** Bạn trả cho 50 GB nhưng nhận 55 GB, đẩy đơn giá thực tế xuống mức tương đương $1,91/GB. Đây là lý do gói này thường được xếp vào nhóm “phổ biến nhất”.

**Gói 5 GB là gói test, không phải gói làm việc.** Ở mức $3,00/GB, bạn đang trả giá cao nhất trong cả bảng để đổi lấy việc không phải cam kết gì.

**Mức $0,68/GB là giá sàn được 9Proxy quảng bá** cho các gói dung lượng lớn. Con số này chỉ đạt được khi bạn mua ở bậc cao nhất, không áp dụng cho gói nhỏ.

Giá có thể thay đổi theo từng đợt điều chỉnh, nên bước cuối cùng trước khi trả tiền vẫn là xem con số trên trang thanh toán.

## Gói theo IP và gói kết hợp IP + GB

Nếu sau khi tính toán bạn thấy mô hình GB không khớp, 9Proxy còn hai dòng sản phẩm khác. Gói theo IP cho băng thông không giới hạn:

| Gói theo IP | Chi phí |
| --- | --- |
| 100 IP | $24 |
| 500 IP | $72 |
| 1.000 IP kèm 500 IP tặng | $126 |
| 100.000 IP | $2.300 |
| 500.000 IP | $8.625 |

Và dòng bundle, dành cho ai cần cả IP ổn định lẫn dung lượng linh hoạt trong một gói:

| Bundle | Nội dung | Giá | Hiệu lực traffic |
| --- | --- | --- | --- |
| Starter | 100 IP + 5 GB | $30 | 180 ngày |
| Popular | 1.500 IP + 50 GB | $180 | 180 ngày |
| Pro | 5.000 IP + 500 GB | $720 | 180 ngày |

Câu hỏi hợp lý ở đây là: bundle có đáng không? Nhìn vào bundle Starter — 100 IP lẻ giá $24, 5 GB lẻ giá $15, cộng lại $39 nhưng mua bundle chỉ $30. Bundle Pro cũng rẻ hơn mua tách ($600 cho 5.000 IP cộng $400 cho 500 GB, so với $720). Nếu bạn thật sự cần cả hai loại tài nguyên, bundle tiết kiệm hơn mua rời.

Nhưng nếu chỉ cần một trong hai, phần dư ra trong bundle là tiền chết.

## Ước tính số GB bạn thật sự cần

Đây là phần quyết định số tiền bạn bỏ ra, và cũng là phần bị bỏ qua nhiều nhất. Không có công thức chung, nhưng có vài mốc tham chiếu.

Kích thước một request phụ thuộc vào loại trang:

- Trang HTML nhẹ, ít script: khoảng 50–150 KB mỗi lần tải.
- Trang nặng JavaScript, có nhiều ảnh và API call: 2–5 MB mỗi lần tải.

Từ đó, vài phép chia nhanh:

- Gói **5 GB** tương đương khoảng 50.000 lượt tải trang nhẹ, hoặc chỉ khoảng 1.000–2.500 lượt nếu bạn tải trang nặng.
- Gói **100 GB** đủ cho khoảng một triệu lượt tải trang nhẹ, hoặc khoảng 20.000–50.000 lượt trang nặng.
- Gói **200 GB** gấp đôi con số trên, đủ cho các job giám sát chạy đều vài tháng.

Cách làm thực tế: mua gói nhỏ nhất có thể chạy được một chu kỳ công việc hoàn chỉnh, đo lượng GB tiêu thụ, rồi nhân lên theo số chu kỳ bạn dự kiến chạy trong 180 ngày. Đừng mua 1.000 GB ngay từ đầu chỉ vì đơn giá rẻ hơn — nếu dự án đổi hướng sau sáu tuần, phần chênh lệch đó lớn hơn khoản tiết kiệm.

Một lưu ý nữa: nếu bạn kiểm soát được việc render, chặn ảnh và các tài nguyên không cần thiết, lượng GB tiêu thụ có thể giảm đáng kể so với con số ở trên. Với mô hình trả theo dung lượng, tối ưu phía client là cách tiết kiệm tiền trực tiếp.

Nếu bạn muốn tự đo trước khi cam kết, [👉 tạo tài khoản 9Proxy và chọn gói GB nhỏ để chạy thử](https://bit.ly/9-Proxy) là cách ít rủi ro nhất.

## Quy trình mua và thiết lập

Thứ tự các bước khá ngắn:

1. Tạo tài khoản và chọn gói GB theo dung lượng bạn đã ước tính.
2. Vào dashboard, mở mục **Residential Proxies → GB → Proxy Generator**.
3. Chọn phương thức xác thực: tạo sub-user với username/password, hoặc whitelist IP thiết bị để kết nối không cần mật khẩu.
4. Chọn khu vực: quốc gia, tiểu bang, thành phố, ZIP hoặc ISP.
5. Chọn chế độ session: sticky nếu bạn cần giữ phiên đăng nhập, rotating nếu bạn cần IP mới liên tục.
6. Xuất danh sách endpoint dạng `.txt` hoặc `.csv`, hoặc lấy code mẫu có sẵn để nhúng vào script.

Hai điểm đáng lưu ý về vận hành. Thứ nhất, gói theo GB không cần app desktop — khác với gói theo IP vốn yêu cầu app để forward port tại máy. Điều này quan trọng nếu bạn chạy trên VPS hoặc môi trường cloud. Thứ hai, xác thực bằng IP whitelist hữu ích khi bạn chạy script trên server có IP tĩnh, còn username/password phù hợp hơn khi làm việc trên nhiều máy hoặc chia sẻ cho sub-user.

9Proxy hỗ trợ qua Telegram, email và hệ thống ticket, hoạt động 24/7 theo thông tin trên trang chủ.

## Những hạn chế cần biết trước khi trả tiền

Gói GB không phải lựa chọn miễn phí rủi ro. Có bốn điểm nên nắm rõ:

**Thời hạn 180 ngày là thật.** Dung lượng mua không tồn tại vĩnh viễn. Nếu công việc của bạn rải rác quanh năm với cường độ thấp, hãy mua lượng vừa đủ dùng trong khoảng thời gian đó thay vì mua dư để lấy giá rẻ.

**Không có IP cố định dài hạn.** IP trong mô hình GB xoay theo request hoặc theo session bạn cấu hình. Nếu công việc bắt buộc phải giữ nguyên một IP trong nhiều ngày, đây không phải sản phẩm dành cho bạn.

**Không có băng thông không giới hạn.** Hết GB là dừng. Ngược lại với gói theo IP, bạn không thể “chạy thêm một chút”.

**Chất lượng không đồng đều ở mọi mục tiêu.** Đây là đặc điểm chung của phân khúc giá thấp, không riêng 9Proxy. Một bảng so sánh độc lập của traffic-creator xếp nhóm nhà cung cấp ngân sách (trong đó có 9Proxy) đạt tỷ lệ thành công 90–95% ở nhóm mục tiêu Tier 2, thấp hơn mức 96–99% của nhóm trung cấp. Với Tier 1, khoảng cách gần như không còn. Nghĩa là nếu bạn nhắm vào các site chống bot gắt, gói rẻ hơn có thể tốn thêm thời gian retry.

## Người khác đánh giá 9Proxy thế nào

Không cần tin hoàn toàn vào trang chủ. Một vài điểm tham chiếu từ bên thứ ba:

- ProxyLook chấm 9Proxy **3,9/5** và mô tả đây là nhà cung cấp proxy dân cư phân khúc ngân sách, mạnh về mô hình trả theo IP với băng thông không giới hạn, kho IP hơn 20 triệu tại hơn 90 quốc gia.
- Geekflare có bài đánh giá riêng về 9Proxy, xác nhận mô hình GB bắt đầu từ $3,00/GB cho gói nhỏ và giảm xuống $0,68/GB ở bậc dung lượng lớn nhất.
- Traffic-creator xếp 9Proxy vào nhóm ngân sách $0,70–$2/GB, đứng ngay trên DataImpulse về giá, và ghi nhận một số người dùng đạt tỷ lệ thành công tốt hơn trên một số mục tiêu cụ thể ở mức giá này.
- Proxybros có bài case study chạy thử khối lượng lớn qua 9Proxy và ghi nhận tỷ lệ thành công khoảng 99,5% cùng thời gian phản hồi trung bình khoảng 0,6 giây trong điều kiện test của họ.

Đọc các con số này cần giữ một chút tỉnh táo: tỷ lệ thành công phụ thuộc vào mục tiêu bạn nhắm tới, không phải thuộc tính cố định của nhà cung cấp. Con số của người khác là điểm khởi đầu, không phải kết luận.

## Câu hỏi thường gặp

**Mua proxy theo GB có rẻ hơn mua theo IP không?**
Không có câu trả lời chung. Nếu mỗi request của bạn nhẹ và bạn cần xoay IP liên tục, GB rẻ hơn vì bạn không trả cho IP. Nếu bạn tải dữ liệu nặng qua ít phiên, gói theo IP rẻ hơn vì băng thông không bị tính.

**Gói 5 GB dùng được bao lâu?**
Tùy loại trang. Khoảng 50.000 lượt tải trang nhẹ, hoặc chỉ khoảng 1.000–2.500 lượt nếu là trang nặng JavaScript.

**Dung lượng còn thừa sau 180 ngày thì sao?**
Tài liệu của 9Proxy ghi hiệu lực của gói GB là 180 ngày. Đây là lý do nên chọn dung lượng khớp với kế hoạch trong khoảng đó, trừ khi bạn dùng chương trình Enterprise vốn không giới hạn thời hạn.

**Có cần cài app không?**
Không. Gói theo GB chạy thẳng trên dashboard. Cần app là mô hình tính theo IP.

**Có phải trả phí hàng tháng không?**
Mô hình GB là mua một lần theo gói. Bạn không bị ràng buộc subscription, nhưng cũng không có băng thông tự động gia hạn.

**Có dùng được cả HTTP/HTTPS và SOCKS5 không?**
Có. 9Proxy hỗ trợ cả hai giao thức, kèm khả năng nhắm mục tiêu tới cấp thành phố và tiểu bang.

Nếu sau khi đọc đến đây bạn vẫn chưa chắc nên bắt đầu ở đâu, cách ít tốn kém nhất là chạy một job thật trên gói nhỏ, ghi lại lượng GB tiêu thụ, rồi mới quyết định bậc dung lượng. [👉 Bắt đầu với gói GB nhỏ nhất của 9Proxy](https://bit.ly/9-Proxy) rồi nâng lên sau khi đã có số liệu thực tế của chính bạn — an toàn hơn nhiều so với việc đoán trước rồi mua 1.000 GB.
