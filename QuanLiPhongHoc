import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

class QuanLyPhongHoc {
    private final List<PhongHoc> danhSachPhongHoc;

    public QuanLyPhongHoc() {
        danhSachPhongHoc = new ArrayList<>();
    }

    public void themPhongHoc(PhongHoc phongHoc) {
        if (!danhSachPhongHoc.contains(phongHoc)) {
            danhSachPhongHoc.add(phongHoc);
            System.out.println("Thêm phòng học thành công!");
        } else {
            System.out.println("Phòng học đã tồn tại trong danh sách!");
        }
    }

    public PhongHoc timPhongHoc(String maPhong) {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            if (phongHoc.getMaPhong().equals(maPhong)) {
                return phongHoc;
            }
        }
        return null;
    }

    public void inDanhSachPhongHoc() {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            System.out.println(phongHoc);
        }
    }

    public void inDanhSachPhongHocDatChuan() {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            if (phongHoc instanceof PhongHocLyThuyet lyThuyet) {
                if (lyThuyet.isCoMayChieu()) {
                    System.out.println(phongHoc);
                }
            } else if (phongHoc instanceof PhongHocMayTinh mayTinh) {
                if (mayTinh.getSoLuongMayTinh() >= 1.5) {
                    System.out.println(phongHoc);
                }
            } else if (phongHoc instanceof PhongHocThiNghiem thiNghiem) {
                if (thiNghiem.isCoBonRua()) {
                    System.out.println(phongHoc);
                }
            }
        }
    }

    public void sapXepTangDanTheoDayNha() {
        danhSachPhongHoc.sort(Comparator.comparing(PhongHoc::getDayNha));
    }

    public void sapXepGiamDanTheoDienTich() {
        danhSachPhongHoc.sort((ph1, ph2) -> Double.compare(ph2.getDienTich(), ph1.getDienTich()));
    }

    public void sapXepTangDanTheoSoLuongBongDen() {
        danhSachPhongHoc.sort(Comparator.comparingInt(PhongHoc::getSoLuongBongDen));
    }

    public void capNhatSoMayTinh(String maPhong, int soLuongMayTinh) {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            if (phongHoc instanceof PhongHocMayTinh mayTinh && phongHoc.getMaPhong().equals(maPhong)) {
                mayTinh.setSoLuongMayTinh(soLuongMayTinh);
                System.out.println("Cập nhật số máy tính thành công!");
                return;
            }
        }
        System.out.println("Không tìm thấy phòng máy tính có mã phòng: " + maPhong);
    }

    public void xoaPhongHoc(String maPhong) {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            if (phongHoc.getMaPhong().equals(maPhong)) {
                danhSachPhongHoc.remove(phongHoc);
                System.out.println("Xóa phòng học thành công!");
                return;
            }
        }
        System.out.println("Không tìm thấy phòng học có mã phòng: " + maPhong);
    }

    public void inTongSoPhongHoc() {
        System.out.println("Tổng số phòng học: " + danhSachPhongHoc.size());
    }

    public void inDanhSachPhongMay60May() {
        for (PhongHoc phongHoc : danhSachPhongHoc) {
            if (phongHoc instanceof PhongHocMayTinh mayTinh) {
                if (mayTinh.getSoLuongMayTinh() == 60) {
                    System.out.println(phongHoc);
                }
            }
        }
    }

    public static void main(String[] args) {
        QuanLyPhongHoc quanLyPhongHoc = new QuanLyPhongHoc();

        PhongHocLyThuyet lyThuyet1 = new PhongHocLyThuyet("LT1", "Day Nha A", 100.0, 10, true);
        PhongHocLyThuyet lyThuyet2 = new PhongHocLyThuyet("LT2", "Day Nha B", 80.0, 8, false);
        PhongHocMayTinh mayTinh1 = new PhongHocMayTinh("MT1", "Day Nha C", 120.0, 12, 30);
        PhongHocMayTinh mayTinh2 = new PhongHocMayTinh("MT2", "Day Nha D", 150.0, 15, 60);
        PhongHocThiNghiem thiNghiem1 = new PhongHocThiNghiem("TN1", "Day Nha E", 200.0, 20, "Hoa Hoc", 40, true);
        PhongHocThiNghiem thiNghiem2 = new PhongHocThiNghiem("TN2", "Day Nha F", 180.0, 18, "Vat Ly", 36, false);

        quanLyPhongHoc.themPhongHoc(lyThuyet1);
        quanLyPhongHoc.themPhongHoc(lyThuyet2);
        quanLyPhongHoc.themPhongHoc(mayTinh1);
        quanLyPhongHoc.themPhongHoc(mayTinh2);
        quanLyPhongHoc.themPhongHoc(thiNghiem1);
        quanLyPhongHoc.themPhongHoc(thiNghiem2);

        quanLyPhongHoc.inDanhSachPhongHoc();

        System.out.println("Tìm phòng học có mã 'MT1': " + quanLyPhongHoc.timPhongHoc("MT1"));

        System.out.println("Danh sách các phòng học đạt chuẩn:");
        quanLyPhongHoc.inDanhSachPhongHocDatChuan();

        System.out.println("Sắp xếp danh sách phòng học tăng dần theo dãy nhà:");
        quanLyPhongHoc.sapXepTangDanTheoDayNha();
        quanLyPhongHoc.inDanhSachPhongHoc();

        System.out.println("Sắp xếp danh sách phòng học giảm dần theo diện tích:");
        quanLyPhongHoc.sapXepGiamDanTheoDienTich();
        quanLyPhongHoc.inDanhSachPhongHoc();

        System.out.println("Sắp xếp danh sách phòng học tăng dần theo số lượng bóng đèn:");
        quanLyPhongHoc.sapXepTangDanTheoSoLuongBongDen();
        quanLyPhongHoc.inDanhSachPhongHoc();

        quanLyPhongHoc.capNhatSoMayTinh("MT1", 35);
        quanLyPhongHoc.inDanhSachPhongHoc();

        quanLyPhongHoc.xoaPhongHoc("TN2");
        quanLyPhongHoc.inDanhSachPhongHoc();

        quanLyPhongHoc.inTongSoPhongHoc();

        System.out.println("Danh sách các phòng máy có 60 máy tính:");
        quanLyPhongHoc.inDanhSachPhongMay60May();
    }
}
