# QA review · B3-mid

Mã khóa: CB95-EEB9

| frame              | object_ref | rule_id | nhận xét                                                                                                                                                             |
| ------------------ | ---------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| adasind_230910.jpg | pedestrian | R06     | Vùng được gán nhãn Pedestrian thực tế là phần ego body của xe/camera, không phải người đi bộ; cần chuyển thành ignore_region với reason=ego_body. |

Ghi finding r2_qa: cell=L_13, rule_R06 có giá trị, why =Vùng ego body bị nhận diện nhầm thành Pedestrian nên cần loại khỏi các object detection và đánh dấu ignore_region với reason=ego_body.
