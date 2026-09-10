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
- Chon rieng mau chu WELCOME, mau ten nguoi, mau chuc vu, mau vai tro va mau vien khung; moi o mau co bang mau nhanh va o chon mau tu do, kem nut dat lai mau mac dinh.
- Chon mau rieng cho tung thanh vien (o layout `Cu` mau nay ap cho ten nguoi, o layout `Thuong` mau nay ap cho vien the va badge vai tro).
- Chinh khoang cach tu header PHIL/WELCOME xuong ten cong ty dau tien va khoang cach giua cac cong ty.
- Chuyen toan bo nhan sidebar giua tieng Viet va tieng Anh bang nut `VI` / `EN`; khong hien hai ngon ngu cung luc.
- Nhap Excel va chon ngay hien thi.
- Nhap ngay export thu cong de dat ten PNG/ZIP/snapshot dung cho lan lam viec hien tai.
- Dan nhanh danh sach dang text: dong dau la cong ty, cac dong sau la `ten - chuc vu`; ho tro cac dau tach `-`, `:`, `–`, `—`, `|`, `->`, `=>`, `/`, `;`, `•`, tu bo so thu tu va nhan dien Mr./Ms./Mrs./ong/ba/anh/chi/co/chu.
- Khi nhap tu Excel hoac dan text, chuc vu va vai tro duoc tu dong viet hoa dau moi tu; snapshot JSON giu nguyen noi dung goc.
- Tao preview PNG va tai file ve may.

## Cau truc code hien tai

Repo hien rat gon:

- `index.html`: toan bo ung dung da duoc bundle vao mot file HTML lon.
- `AGENTS.md`: quy tac lam viec bat buoc cho agent.
- `README.md`: tai lieu dinh huong cho nguoi dung va agent moi.

`index.html` khong phai source tach module. File nay gom:

- Loader tu giai nen bundle luc mo trang.
- Ham `redesignEditor()` trong loader sap xep lai sidebar thanh 3 khu vuc `Noi dung / Content`, `Thiet ke / Design`, `Du lieu / Data` truoc khi render template. Cac muc thuoc tab `Thiet ke` da mang san `data-wb-panel-view="design"` trong template, khong con bi patch tu `redesignEditor()`.
- Template HTML/CSS/JS duoc nhung trong `script type="__bundler/template"`.
- Asset/font/script duoc nhung trong manifest base64.
- Logic React/DC nam trong template da bundle, dac biet class `Component`.

Khi can sua logic, agent thuong can:

1. Tim trong `index.html` bang `rg` hoac dung Node de parse noi dung `__bundler/template`.
2. Sua dung chuoi/logic lien quan, han che dung cac phan asset base64.
3. Kiem tra lai template van parse duoc bang `JSON.parse`.
4. Neu sua UI, mo file tren trinh duyet de xem lai khi can.

## Cau truc tab `Thiet ke`

Tab `Thiet ke` gom 6 muc cha, moi muc chia tiep thanh cac nhom con:

1. `Hien thi & danh sach`: nhom `Hien thi thong tin` (chuc vu / vai tro / chuc vu xuong dong) va nhom `Danh sach` (can giua danh sach, vien khung ten) - nhom sau chi hien o layout `Cu`.
2. `Header PHIL / WELCOME`: nhom `Can header`, nhom `Co chu header` (co PHIL, co WELCOME), nhom `Khoang cach khoi` (khoang cach PHIL/WELCOME, khoang cach header xuong ten cong ty dau tien).
3. `Kieu chu`: nhom `Kieu chu` (font, co chu tong the) va nhom `Co chu tung phan`.
4. `Mau sac`: nhom `Mau chu dao` (bang mau + chon mau tu do), nhom `Mau chu`, nhom `Khung & vien` (mau vien + dat lai mau mac dinh).
5. `Khoang cach & thut le`: nhom `Gian dong`, nhom `Khoang cach khoi` (giua cac cong ty, khoang cach quanh dau `-`), nhom `Thut le`.
6. `Khung bang`: do day vien, bat/tat keo chinh kich thuoc, chieu cao khung.

Cac hang chi ap cho mot layout duoc boc trong `sc-if` theo `isOld` / `isStandard`. Markup dung cac class dung chung `wb-group`, `wb-group-title`, `wb-row`, `wb-row-label`, `wb-step`, `wb-step-val`, `wb-toggle-row`, `wb-switch`, `wb-color-input`, `wb-seg`, `wb-hint` khai bao trong `<style>` cua template.

Luu y khi sua: DC bo qua attribute `open` khong gia tri tren `<details>`, nen moi muc luon dong khi render lan dau; trang thai mo/dong do nguoi dung bam se duoc giu qua cac lan re-render.

## Cac diem logic quan trong

- Du lieu mac dinh nam trong `defaultData()`.
- Layout hien tai duoc chon bang `data.layout`: `old`, `standard`, hoac `vip`.
- Du lieu luu o localStorage key `wb-data-v2`.
- Mau sac luu o cac key `primary`, `welcomeColor`, `nameColor`, `positionColor`, `roleColor`, `frameColor`. Cac key nay deu optional; khi khong co thi lay mac dinh theo layout, nen bo qua tat ca se cho ra dung giao dien goc.
- Mau duoc day xuong board bang CSS variable tren khung: `--pri`, `--cname`, `--cpos`, `--crole`.
- Khoang cach khoi luu o `oldHeaderBodyGap` / `oldGroupGap` (layout `Cu`) va `stdHeaderBodyGap` / `stdGroupGap` (layout `Thuong`).
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
