# GAME SHOW TƯ TƯỞNG HỒ CHÍ MINH

## 📁 CẤU TRÚC DỰ ÁN

### File chính (SỬ DỤNG):
- **index_new.html** - Màn hình chọn vai trò (BẮT ĐẦU TẠI ĐÂY)
- **host.html** - Trang điều khiển cho HOST
- **team.html** - Trang dùng chung cho Team A và Team B

### File cũ (KHÔNG DÙNG):
- ~~index.html~~ - File cũ đã lỗi thời

---

## 🎮 HƯỚNG DẪN SỬ DỤNG

### Bước 1: Khởi động
1. Mở file **index_new.html** trên trình duyệt

### Bước 2: Chọn vai trò
- **HOST**: Nhập mật khẩu `T@ohan123`
- **Team A**: Click "Join as TEAM A"
- **Team B**: Click "Join as TEAM B"

### Bước 3: Chơi game

#### Trên màn hình TEAM (A/B):
1. Chọn ô câu hỏi (1-9)
2. Chờ Host phê duyệt
3. Khi được duyệt → Câu hỏi tự động hiện ra
4. Timer 30 giây đếm ngược
5. Thảo luận và trả lời miệng cho Host nghe

#### Trên màn hình HOST:
1. Nhận thông báo team chọn ô (góc phải màn hình)
2. Click **"PHÊ DUYỆT"** hoặc **"TỪ CHỐI"**
3. Khi phê duyệt → Câu hỏi hiện ra với timer
4. Nghe team trả lời
5. Click **"✓ ĐÚNG"** hoặc **"✗ SAI"**
   - Nếu SAI: Có thể cho team kia cướp ô
   - Nếu cả 2 sai: Ô chết (màu xám)
6. Tự động check BINGO (3 ô liên tiếp = +50 điểm)

---

## 🎯 LUẬT CHƠI

### VÒNG 1: BINGO (9 câu hỏi trắc nghiệm)

1. **Chọn ô**: Team chọn 1 trong 9 ô
2. **Trả lời đúng**: 
   - Ô sáng màu đội (🔴 Đỏ = Team A, 🟡 Vàng = Team B)
   - +10 điểm
3. **Trả lời sai**: 
   - Đội kia có quyền cướp ô
   - Nếu cả 2 sai → Ô chết (màu xám)
4. **BINGO**: 3 ô liên tiếp (ngang/dọc/chéo) → +50 điểm thưởng

### VÒNG 2: CÂU HỎI MỞ

1. Host click **"🎯 VÒNG 2"**
2. Hiện câu hỏi phân tích mở
3. Cả 2 team trả lời miệng
4. Host quyết định team nào thuyết phục hơn
5. Click nút **"TEAM A +50 điểm"** hoặc **"TEAM B +50 điểm"**

### KẾT QUẢ CHUNG CUỘC

- Host click **"🏆 Kết quả chung cuộc"**
- Hiển thị điểm số cuối cùng
- Xác định đội CHIẾN THẮNG 👑

---

## 🛠️ TÍNH NĂNG KỸ THUẬT

### ✅ Đã sửa các lỗi:
1. ✅ Team A/B giờ HIỆN FORM CÂU HỎI khi được duyệt
2. ✅ Bỏ bảng 9 ô ở trang Host
3. ✅ Vòng 2 cộng 50 điểm (không phải 30)
4. ✅ Tách hoàn toàn 3 trang riêng biệt
5. ✅ Clean code, loại bỏ code trùng lặp

### Đồng bộ Real-time:
- Firebase Realtime Database
- Tự động cập nhật điểm số
- Đồng bộ màu ô giữa các màn hình
- Timer đếm ngược 30s

### Phân quyền:
- Host: Chấm điểm, phê duyệt, reset game
- Team: Chỉ chọn ô và xem câu hỏi

---

## 📊 CÂU HỎI TRONG GAME

### Chương 6: Văn hóa, Đạo đức, Con người
1. Quan niệm văn hóa của HCM (1943)
2. Mối quan hệ văn hóa - kinh tế - chính trị
3. Văn hóa nghệ thuật là một mặt trận
4. Đạo đức cách mạng như gốc và nguồn
5. Trung với nước, hiếu với dân
6. Cần, kiệm, liêm, chính
7. Một tấm gương sống
8. Trồng người
9. Con người - mục tiêu và động lực

### Câu hỏi Vòng 2:
Phân tích mối quan hệ biện chứng giữa Văn hóa với Kinh tế và Chính trị theo tư tưởng Hồ Chí Minh.

---

## 🎨 MÀU SẮC

- 🔴 **Đỏ**: Team A
- 🟡 **Vàng**: Team B
- ⚫ **Xám**: Ô chết (cả 2 sai)
- 🟨 **Vàng nhạt**: Ô chưa chọn

---

## 💾 DỮ LIỆU FIREBASE

### Database Structure:
```
/gameState
  - currentRound: 1
  - scores: { A: 0, B: 0 }

/cells
  - 1-9: { owner: null/'A'/'B'/'dead', answered: true/false }

/cellSelection
  - teamRequesting: "Team A"/"Team B"
  - cellNumber: 1-9
  - status: "pending"/"approved"/"rejected"
  - answeringTeam: "Team A"/"Team B"
```

---

## 🔐 BẢO MẬT

- Mật khẩu Host: **T@ohan123**
- Chỉ Host mới có quyền:
  - Phê duyệt câu hỏi
  - Chấm điểm đúng/sai
  - Reset game
  - Xem kết quả cuối cùng

---

## 📱 RESPONSIVE

- Desktop: Full layout
- Tablet: Tối ưu grid
- Mobile: Hỗ trợ touch

---

## 🚀 KHỞI CHẠY

```bash
# Cách 1: Double-click file
index_new.html

# Cách 2: Live Server (VS Code)
Right-click > Open with Live Server

# Cách 3: HTTP Server
python -m http.server 8000
# Truy cập: http://localhost:8000/index_new.html
```

---

## 📞 HỖ TRỢ

Nếu có lỗi:
1. Kiểm tra kết nối Internet (cần Firebase)
2. Dùng trình duyệt Chrome/Edge mới nhất
3. Xóa cache và refresh (Ctrl + Shift + R)
4. Đảm bảo 3 file cùng folder: index_new.html, host.html, team.html

---

## 🎓 MỤC ĐÍCH SỬ DỤNG

Game show tương tác cho lớp học môn **Tư tưởng Hồ Chí Minh**, giúp:
- Ôn tập kiến thức Chương 6
- Tăng tính tương tác và cạnh tranh
- Phát triển tư duy chiến thuật (Bingo)
- Rèn kỹ năng phân tích (Vòng 2)

---

**Version**: 2.0 (Clean Code)  
**Last Updated**: January 2026  
**Developer**: AI Assistant
