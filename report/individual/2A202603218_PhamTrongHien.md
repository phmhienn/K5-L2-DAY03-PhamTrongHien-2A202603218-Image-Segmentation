# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên [LMS](https://aithucchien.vinuni.edu.vn). Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](../../reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202603218
- Ngày / CVAT local: 12/11/2026
- Công cụ đã dùng: CVAT, SAM3

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh [LMS](https://aithucchien.vinuni.edu.vn) đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task            | File ZIP đúng tên   | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --------------- | ------------------- | -----------------: | ---------------------------: |
| easy_semantic   | easy_semantic.zip   |              3 / 3 |                           20 |
| medium_instance | medium_instance.zip |              3 / 3 |                           32 |
| hard_panoptic   | hard_panoptic.zip   |              2 / 2 |                           30 |
| cp1_holes       | chưa hoàn thành     |              1 / 1 |                            3 |
| cp2_slice       | chưa hoàn thành     |              0 / 1 |                            3 |
| cp5_occlusion   | chưa hoàn thành     |              0 / 1 |                            3 |
| cp3_thin        | chưa hoàn thành     |              0 / 1 |                            3 |
| cp4_curb        | chưa hoàn thành     |              0 / 1 |                            3 |
| cp6_coverage    | chưa hoàn thành     |              0 / 1 |                            3 |
| **Tổng tối đa** |                     |                    |                      **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: ảnh:000000181542.jpg, vị trí: giữa ảnh dưới bức tượng, object person 10
- Class và quy tắc tôi dùng để chọn biên: class: person, quy tắc dùng là: brush/mask
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: không dùng, thấy đối tượng phù hợp với class person dựa vào các đặc điểm
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng:hard_panoptic/ảnh:000000350023.jpg/vùng xe ô tô phía trên lệch trái
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: bị gộp 2 object car với nhau
- Bằng chứng tôi nhìn thấy:Nhìn thấy rõ khe hở và đường tiếp giáp giữa 2 thân xe, nhưng trong danh sách Objects chỉ có duy nhất 1 shape car bao trùm cả 2 xe
- Quy tắc và hành động sửa: không để 2 đối tượng chung 1 object nên là đã tách nó ra làm 2 object riêng biệt
- Sau sửa đã Save và export lại chưa? đã save và export lại

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể  | Quy tắc/chứng cứ                                                       | Quyết định hoặc câu hỏi cho coach            |
| ---------- | --------------------- | ---------------------------------------------------------------------- | -------------------------------------------- |
| 1          | 81ae7cbb-6bc63a4a.jpg | 1 cục đen đen cạnh biển quảng cáo chưa chắc là bụi cây                 | không annotation vì chưa xác định được class |
| 2          | 7ee6d192-89e2408b.jpg | chưa xác định rõ được road có đến chỗ bờ tường không                   | không annotation                             |
| 3          | 817bca71-00000000.jpg | 1 phần đen ở bên trái chưa xác định được là vegetation hay là building | không annotation                             |
