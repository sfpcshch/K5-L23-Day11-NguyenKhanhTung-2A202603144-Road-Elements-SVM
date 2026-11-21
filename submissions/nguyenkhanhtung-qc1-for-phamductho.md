# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Phạm Đức Thọ (`2A202603182`, `phamductho`)        Người kiểm (học viên): Nguyễn Khánh Tùng (`2A202603144`)  
Ngày: 2026-11-21                                            Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `phamductho-front.zip`, `phamductho-fisheye.zip` (`revision 1`; SHA256 khớp manifest, `contains_images = false`)  
Số ảnh kiểm: 6 (`A01`, `A07`, `A09`, `A12`, `B01`, `B05`; ảnh không lỗi: `B01`) (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 60  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 7 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 11 | 3 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 11 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 11 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 11 | 2 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 19 | 5 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 3 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 6 | 3 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 3 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 8 | 0 | chính |
| QC1-12 file | lỗi file | 60 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-06 | A01 | `lane#5@(1274,704)` | chính | Vạch liền mép phải (`R2`) ngoài ảnh màu vàng nhưng gán sai `color = white` (đúng là `yellow`) |
| 2 | QC1-06 | A01 | `lane#2@(1,602)` | chính | Vạch mép trái (`L2`) gồm 2 nét trắng song song liền nhau nhưng gán sai `kind = single` (đúng là `double`) |
| 3 | QC1-09 | A01 | `traffic_sign#6@(552,409)` | chính | Biển chỉ dẫn hướng đi nền xanh bên phải bị gán sai `group = mandatory` (đúng là `information`) |
| 4 | QC1-03 | A07 | `lane#1@(1198,451)` | nặng | Vạch trắng bên phải (ngăn dải đỗ xe với làn xe tải) bị gán nhầm `position = L1` (đúng là `R2`; bên trái barrier không có vạch sơn) |
| 5 | QC1-07 | A07 | `drivable#3@(799,560)` | chính | Vùng `drivable` (`alternative`) vẽ trùm qua toàn bộ dải đỗ xe có vạch chữ T sát bên phải `R1` (dải đỗ xe không thuộc vùng lái) |
| 6 | QC1-03 | A09 | `lane#3@(444,649)` | nặng | Vạch trắng đôi sát bên trái làn xe đang đi bị gán nhầm `position = L2` (đúng là `L1`) |
| 7 | QC1-03 | A09 | `lane#4@(540,640)` | nặng | Vạch trắng đứt bên phải làn xe đang đi bị gán nhầm `position = L1` (đúng là `R1`; cũng là nguyên nhân `lint` báo thiếu `R1` trên `A09`) |
| 8 | QC1-07 | A09 | `drivable#0@(1274,694)` | chính | Vùng `drivable` ở làn bên phải bị gán nhầm `area_type = direct` (đúng là `alternative`) |
| 9 | QC1-07 | A09 | `drivable#1@(491,658)` | chính | Vùng `drivable` ở làn xe mình đang đi bị gán nhầm `area_type = alternative` (đúng là `direct`) |
| 10 | QC1-09 | A12 | `traffic_sign#9@(942,256)` | chính | Biển hiệu lệnh `ONE WAY` trên cột phải bị gán sai `group = prohibitory` (đúng là `mandatory`) |
| 11 | QC1-09 | A12 | `traffic_sign#10@(970,230)` | chính | Biển tên đường nền xanh (`Greene`) trên cột phải bị gán sai `group = prohibitory` (đúng là `information`) |
| 12 | QC1-07 | A12 | `drivable#2@(3,641)` | chính | Vùng `drivable` (`direct`) trước vạch ngựa vạn vẽ tràn hết sang làn bên phải và dải đỗ xe hai bên thay vì chỉ ôm làn đang đi |
| 13 | QC1-07 | B05 | `drivable#1@(922,259)` | chính | Lòng đường chính sát thân xe bị gán sai `area_type = alternative` thay vì `direct` và thiếu phần mặt đường phía trái sát vạch ngựa vạn |

*(Ảnh ghi "không lỗi" trong 6 ảnh kiểm: **`B01`** — đủ 4 tag đúng, `crosswalk`, `drivable direct`, 2 `road_curb` vẽ gần→xa mượt và `traffic_light#0@(349,178)` sát vỏ, đúng `edge_zone = false`.)*

*(Ghi chú thêm ngoài 6 ảnh kiểm để bạn tham khảo khi sửa toàn lô: ở `A05` không có vạch sơn nên miễn `QC1-02`; ở `A06` thiếu `R1` do cột thép không sơn vạch; ở `B07`, `B08` còn vài `lane` camera hai bên có `p0.y < p1.y`; và `A10` có 2 box `< 8 px` không bắt buộc.)*

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| — | Không có ca mơ hồ ảnh hưởng quyết định (`A09` có vẽ vạch `R1` nhưng gán nhầm `position = L1`, nên tính là 1 lỗi `QC1-03` thay vì đếm trùng `QC1-02`; `A05` không có vạch sơn đã miễn theo CHECKPOINTS) | — |

## Quyết định
Lỗi nặng: 3   Lỗi chính: 10 / 60 nhãn = 16.7 %   Lỗi nhẹ: 0   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Rework  
Lý do (theo luật của phiếu): Có 3 lỗi nặng (`≥ 1` lỗi nặng → Rework) và tỉ lệ lỗi chính `10 / 60 = 16.7 % > 5 %` → **Rework**.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
