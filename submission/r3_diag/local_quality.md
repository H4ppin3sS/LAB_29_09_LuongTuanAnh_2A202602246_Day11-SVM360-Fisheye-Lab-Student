# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `cb95eeb931a7ce083c25727eb54e262cd78909d320f95f06c3ea56f9608f3831`; slice `B3-mid`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_128310.jpg, adasind_140160.jpg, adasind_230910.jpg. Frame thiếu trong export: không.
TP=15; FP=4; FN=5; số lần đối chiếu=22; mean IoU của TP=0.804.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.682 | 0.918 | 0.818 |
| precision | 0.789 | 0.843 | 0.667 |
| recall | 0.750 | 0.750 | 0.500 |
| jaccard | 0.625 | 0.660 | 0.400 |
| dice | 0.769 | 0.775 | 0.571 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 2 | 0 | 0 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| Car | 2 | 1 | 2 | 0.864 | 0.667 | 0.500 | 0.400 | 0.571 |
| Pedestrian | 6 | 2 | 2 | 0.818 | 0.750 | 0.750 | 0.600 | 0.750 |
| ThreeWheeler | 1 | 0 | 1 | 0.955 | 1.000 | 0.500 | 0.500 | 0.667 |
| Truck | 4 | 1 | 0 | 0.955 | 0.800 | 1.000 | 0.800 | 0.889 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_128310.jpg | 4 | 0 | 1 | 0.800 | 1.000 | 0.800 |
| adasind_140160.jpg | 3 | 0 | 0 | 1.000 | 1.000 | 1.000 |
| adasind_230910.jpg | 8 | 4 | 4 | 0.571 | 0.667 | 0.667 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Car | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|---:|
| Bike | 2 | 0 | 0 | 0 | 0 | 0 |
| Car | 0 | 2 | 0 | 0 | 1 | 1 |
| Pedestrian | 0 | 0 | 6 | 0 | 0 | 2 |
| ThreeWheeler | 0 | 1 | 0 | 1 | 0 | 0 |
| Truck | 0 | 0 | 0 | 0 | 4 | 0 |
| <extra> | 0 | 0 | 2 | 0 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
