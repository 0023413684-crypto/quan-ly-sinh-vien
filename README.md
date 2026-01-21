```mermaid
  erDiagram
    KHOA {
        string maKhoa PK
        string tenKhoa
    }

    BO_MON {
        string maBoMon PK
        string tenBoMon
        string maKhoa FK
    }

    MON_HOC {
        string maMon PK
        string tenMon
        int soTinChi
        string maBoMon FK
    }

    LOP_KH {
        string maLopKH PK
        string tenLopKH
        string nienKhoa
        string maKhoa FK
    }

    SINH_VIEN {
        string maSV PK
        string hoTen
        date ngaySinh
        string gioiTinh
        string soDienThoai
        string diaChi
        string maLopKH FK
    }

    GIANG_VIEN {
        string maGV PK
        string hoTen
        date ngaySinh
        string hocVi
        string chucDanh
        string maBoMon FK
    }

    LOP_MH {
        string maLopMH PK
        int hocKy
        string namHoc
        int siSoToiDa
        string maMon FK
        string maGV FK
    }

    DANGKY_MH {
        string maSV PK, FK
        string maLopMH PK, FK
        date ngayDangKy
    }

    KET_QUA {
        string maSV PK, FK
        string maLopMH PK, FK
        float diemQT
        float diemThi
        float diemTongKet
        string ketQua
    }

    %% Quan hệ
    KHOA ||--o{ BO_MON : quan_ly
    KHOA ||--o{ LOP_KH : quan_ly
    BO_MON ||--o{ MON_HOC : phu_trach
    BO_MON ||--o{ GIANG_VIEN : quan_ly
    MON_HOC ||--o{ LOP_MH : mo
    GIANG_VIEN ||--o{ LOP_MH : giang_day
    LOP_KH ||--o{ SINH_VIEN : chua
    SINH_VIEN ||--o{ DANGKY_MH : dang_ky
    LOP_MH ||--o{ DANGKY_MH : duoc_dang_ky
    SINH_VIEN ||--o{ KET_QUA : co
    LOP_MH ||--o{ KET_QUA : co
```
