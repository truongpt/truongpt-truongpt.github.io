## Biên dịch Linux OS từ mã nguồn

Bắt đầu đi làm vào giữa 2009, tôi bắt đầu được tiếp xúc với Linux, nhưng trải qua gần 9 năm từ đó đến nay, hiểu biết về Linux rất ổn định như tham nhũng, không có gì thay đổi. Lý do thứ nhất là vì các dự án làm với Linux chỉ là sử dụng môi trường Linux để phát triển, nên cơ bản chỉ biết cái Makefile là xong, chẳng lúc nào cần mó tay một cách chỉnh chu thấu đáo vào các thứ như device driver, hay memory management …, để biết cái gì đủ hay ho mà kể chuyện. Thật ra là có một chút nhưng không ăn thua, mấy thứ cơ bản như system call, char driver, block driver … thì nó phổ cập cmnr, với lại khoảng cách giữa biết tên và biết để kể chuyện được nó cũng quá xa. Lý do thứ 2 là lười & nhác tìm hiểu.

Đang ôn tập lại chút kiến thức để chuẩn bị do dự án làm driver trên Linux, thì bắt gặp trang dưới (ko hiểu sao giờ mới biết, chắc lại do nhác & lười).
http://linuxfromscratch.org/lfs

Trước giờ hay có sở thích, là thử distribution (Linux OS) của Linux, hết Ubuntu đến Backtrack, với mục đích rất đáng sợ là để học sâu thêm về Linux nhưng cài xong  chiêm ngưỡng cái desktop xong  rồi thì sau đó là chỉ để duyệt web ~.~

Việc hay thử Linux OS, nó cũng bắt nguồn từ hồi mới ra trường, được bố mẹ bán hết lúa gạo lợn gà cho mua con hp pavilion, không nhớ chính xác tên nhưng giá là 12 hay 17 chai gì đấy. Đen đủi thế nào lúc ra lúc bắt đầu đi làm 1 năm thì bị trộm nó thó mất, lương thấp ăn chưa đủ nói gì đến mua lại máy. May thay ông anh trong dự án có con T40 thinkpad hỏng main đang đắp chiếu, bảo cầm về sửa mà dùng. Sau thay main cũ hết 1 triệu, cài luôn ubuntu, có hơi rùa bò tí những nó vẫn dùng để kết nối tốt với internet. Vì rùa bò nên nghĩ ra việc dùng các bản Linux OS cho máy cấu hình thấp, nhưng rồi cũng thấy chẳng ăn thua lắm nên mới sinh ra trò thử cài Ubuntu xong gỡ hết gói màu mè về giao diện ra thì tốc độ có thấy cải thiện kha khá. Từ đó có thêm trò ngược đời là cài xong Linux OS thì gỡ bớt gói không cần thiết ra, đôi khi không biết nên gỡ quá tay làm nó chẳng start up luôn được cả giao diện =]]. Dùng được hơn 1 năm thì T40 cũng đi vì cái màn hình hỏng.

Đến 2011, đi công tác ở Nhật, nhịn ăn nên cũng mua được con [CF-W5MW8AJR](https://panasonic.jp/pc/p-db/CF-W5MW8AJR_spec.html) Panasonic đồ cũ cùi bắp, mua xong cài luôn Ubuntu đè lên con Win Vista bản quyền luôn.
Riêng con này từ lúc mua ngoài làm mất thứ vớ vẩn thì cũng kiếm đc chút từ việc
[data hiding](https://www.freelancer.com/projects/C-Programming/Data-hiding-compressed-video-12726827/), do muốn mua con len Nikon 50mm f/1.8G, nhưng lương chỉ đủ nuôi con nên đành kiếm tí việc đánh thêm, đỡ phạm đến phần tiền mua sữa cho con 😦

Nói dài dòng, nhưng tóm lại giờ có con CF5 cùi bắp, tính  cho mấy thằng em ở quê, nhưng chắc là nó không thèm lấy, mà công nhận đồ của Panasonic rất chất, nhẹ, pin trâu vẫn duy trì hơn tầm 1.5h, phím bấm cực đã không bị rung, ai dùng dòng Let’s Note của Panasonic rồi thì biết, chỉ có điều giá trên trời. Như  đề cập ở trên, tự dưng biết 1 dự án rất có tâm, hướng dẫn biên dịch hẳn [Linux OS từ source code](https://linuxfromscratch.org/lfs/) (có khi google đủ các kiểu + bỏ thời gian ra chắc cũng tự build được), tóm lại từ Linux kernel, đến các gói mã nguồn GNU & non-GNU …

Dù là việc biên dịch chỉ là việc chân tay, nhưng trải nghiệm 1 lần biên dịch ra OS từ mã nguồn nó cũng hay hay, dù sao cũng tạo hứng thú vượt qua lười & nhác để có thể bắt đầu tìm hiểu thêm chút về Linux. Thêm vào đó hi vọng do tự điều chỉnh được các gói cần thiết nên sẽ có được con OS nhỏ gọn để chạy với cái đồ cùi bắp như CF-W5MW8AJR.

Có 1 điểm chú ý khi bắt đầu biên dịch là nên chuẩn bị 1 con USB stick hoặc CD live có thể chạy live Linux OS nào đó (ex: ubuntu), để phòng trường hợp lỗi khi chia ổ cứng này nọ thì còn có cách mà xử lý.
Về phần dữ liệu quan trọng trong máy thì theo tôi không cần phải backup, vì nếu bị lỗi thì có cơ hội học cách cứu dữ liệu, nếu cứu không được thì coi như cái giá phải trả để nhớ bài học hơn :-).

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/80x15.png" />