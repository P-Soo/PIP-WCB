# PIP Welcome Board

Ung dung tao bang chao mung khach/doan cho Phil Inter Pharma. App chay truc tiep tu mot file `index.html`, khong can backend, khong can buoc build, phu hop de mo tren trinh duyet hoac deploy GitHub Pages.

## Muc dich ung dung

- Tao welcome board kich thuoc 1920x1080 de chieu len TV/man hinh.
- Nhap danh sach cong ty/doan va thanh vien truc tiep tren trinh duyet.
- Ho tro nhap Excel `.xlsx`/`.xls`, tu gom nhom theo cong ty va loc theo ngay.
- Xem truoc va tai PNG dung kich thuoc 1920x1080.
- Tu luu du lieu vao `localStorage` cua trinh duyet.

## Cac che do hien thi

Ung dung hien co 3 tab layout trong panel chinh sua:

- `Cu`: layout mac dinh hien tai. Khung xanh, logo PHIL/INTER PHARMA, chu WELCOME, ten cong ty/doan o giua va danh sach thanh vien dang ten - vai tro. Neu chi co ten cong ty ma khong co thanh vien, ten cong ty van phai hien.
- `Thuong`: layout hien dai dang card. Moi cong ty/doan co tieu de rieng, thanh vien co ten, chuc vu va vai tro dang badge. Ho tro mau chu dao va mau rieng tung nguoi.
- `VIP`: layout don gian cho khach VIP. Chu WELCOME lon, danh sach ten khach o giua, logo/ten cong ty khach o goc trai duoi va logo PHIL o goc phai duoi.

## Chuc nang chinh

- Them/xoa cong ty hoac don vi.
- Them/xoa thanh vien.
- Sua ten, gioi tinh, chuc vu, vai tro.
- Keo tha de doi thu tu thanh vien trong cung mot cong ty.
- Bat/tat hien thi chuc vu va vai tro.
- Chon chuc vu xuong dong hoac nam cung dong.
- Chon font, co chu va mau chu dao.
- Chon mau rieng cho tung thanh vien.
- Nhap Excel va chon ngay hien thi.
- Tao preview PNG va tai file ve may.

## Cau truc code hien tai

Repo hien rat gon:

- `index.html`: toan bo ung dung da duoc bundle vao mot file HTML lon.
- `AGENTS.md`: quy tac lam viec bat buoc cho agent.
- `README.md`: tai lieu dinh huong cho nguoi dung va agent moi.

`index.html` khong phai source tach module. File nay gom:

- Loader tu giai nen bundle luc mo trang.
- Template HTML/CSS/JS duoc nhung trong `script type="__bundler/template"`.
- Asset/font/script duoc nhung trong manifest base64.
- Logic React/DC nam trong template da bundle, dac biet class `Component`.

Khi can sua logic, agent thuong can:

1. Tim trong `index.html` bang `rg` hoac dung Node de parse noi dung `__bundler/template`.
2. Sua dung chuoi/logic lien quan, han che dung cac phan asset base64.
3. Kiem tra lai template van parse duoc bang `JSON.parse`.
4. Neu sua UI, mo file tren trinh duyet de xem lai khi can.

## Cac diem logic quan trong

- Du lieu mac dinh nam trong `defaultData()`.
- Layout hien tai duoc chon bang `data.layout`: `old`, `standard`, hoac `vip`.
- Du lieu luu o localStorage key `wb-data-v2`.
- Render tab `Cu` dung danh sach tinh toan `oldCompanies`.
- Render tab `Thuong` dung danh sach tinh toan `companies`.
- Render tab `VIP` dung `vip.names`, `vip.guestLogo`, `vip.guestName`.
- Nhap Excel dung SheetJS trong ham `parseWorkbook`.
- Xuat PNG dung `html-to-image` trong `renderStagePng`.

## Cach chay

Mo truc tiep `index.html` bang trinh duyet. Khong can cai package.

Luu y: chuc nang xuat PNG co the can mang lan dau de tai/nhung Google Fonts.

## Dinh dang Excel

File Excel can co hang tieu de voi cac cot tieng Viet hoac tieng Anh tuong duong:

| Ten Cong ty | Ho va ten khach | Chuc vu | Vai tro | Gioi tinh | Ngay thang |
|-------------|-----------------|---------|---------|-----------|------------|
| Company name | Guest's full name | Position | Role | Gender | Date |

Cot bat buoc: ten cong ty va ho ten khach.

## Deploy GitHub Pages

1. Push `index.html` len branch `main`.
2. Vao GitHub repo `Settings -> Pages`.
3. Chon `Deploy from a branch`, branch `main`, folder `/root`.
4. Luu lai va doi GitHub Pages cap nhat.

## Quy tac lam viec cho agent

Moi phien agent moi phai doc `AGENTS.md` truoc khi sua code.

Tom tat quy trinh:

- Doc yeu cau va kiem tra ngu canh repo.
- Sua dung pham vi can thiet.
- Kiem tra lai thay doi.
- Bao cao sau khi lam xong: da lam gi, nguyen nhan loi neu co, cach sua, da kiem tra gi.
- Cho nguoi dung duyet.
- Chi commit va push sau khi nguoi dung noi ro da duyet.

Khong duoc tu y revert, xoa, format lai thay doi khong lien quan.

