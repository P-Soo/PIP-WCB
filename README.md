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
- Chon font, co chu va mau chu dao. Danh sach font co them `Malgun Gothic` va `Noto Sans KR` de hien thi tieng Han dong bo voi chu Latin.
- Can rieng ca cum logo + WELCOME va rieng dong WELCOME; khi can rieng, ben trai tra ve vi tri sat logo, o giua nam dung tam khung va ben phai nam sat mep doi dien logo. Dong WELCOME co font doc lap voi noi dung cong ty/nhan vien ben duoi.
- Chon rieng mau chu WELCOME, mau ten nguoi, mau chuc vu, mau vai tro va mau vien khung; moi o mau co bang mau nhanh va o chon mau tu do, kem nut dat lai mau mac dinh.
- Chon mau rieng cho tung thanh vien (o layout `Cu` mau nay ap cho ten nguoi, o layout `Thuong` mau nay ap cho vien the va badge vai tro).
- Chinh khoang cach tu header PHIL/WELCOME xuong ten cong ty dau tien va khoang cach giua cac cong ty.
- Layout Cu tu do cot ten theo noi dung dai nhat cua toan danh sach, dong bo cac cot giua cac cong ty. Dieu khien khoang cach hai ben dau `-` la dem moi ben (mac dinh 24px, buoc 4px), khong con la do rong ca o dau gach. Tu an khi khong co dau phan cach (vi du chi hien chuc vu xuong dong, khong co vai tro).
- Chuyen toan bo nhan sidebar giua tieng Viet va tieng Anh bang nut `VI` / `EN`; khong hien hai ngon ngu cung luc.
- Nhap Excel va chon ngay hien thi. Danh sach ngay duoc loai trung va sap tu moi den cu theo ngay thuc te; moi lan nhap tu chon ngay hop le moi nhat, khong phu thuoc vi tri dong trong Excel. Ngay khong hop le nam cuoi; neu khong co ngay hop le thi giu cach chon ngay dau tien nhu truoc.
- Nhap ngay export thu cong de dat ten PNG/ZIP/snapshot dung cho lan lam viec hien tai.
- Dan nhanh danh sach dang text: dong dau la cong ty, cac dong sau la `ten - chuc vu`; ho tro cac dau tach `-`, `:`, `–`, `—`, `|`, `->`, `=>`, `/`, `;`, `•`, tu bo so thu tu va nhan dien Mr./Ms./Mrs./ong/ba/anh/chi/co/chu.
- Khi nhap tu Excel hoac dan text, chuc vu va vai tro duoc tu dong viet hoa dau moi tu; snapshot JSON giu nguyen noi dung goc.
- Tao preview PNG va tai file ve may.
- Xuat file Word `.docx` bang nut `Tai Word` o thanh cong cu; chu trong file la text that, sua/copy duoc trong Word.

## Xuat file Word

Nut `Tai Word` sinh thang file `.docx` khong can render PNG truoc, khong can mang.

- Logo PHIL/INTER PHARMA dung anh PNG nhung san trong app cho ca 3 layout; dieu khien co PHIL thay doi kich thuoc toan logo va giu nguyen ti le.
- Khi xuat Word, logo PHIL duoc nhung vao `word/media/phil-logo.png`, khong can file anh ben ngoai. Noi dung khach van la text chinh sua duoc. Xuat PNG doi anh tren board tai xong truoc khi render.

- Kho giay A4 ngang 297x210mm, le trang 0.
- Khung board duoc ve bang shape `roundRect` cua DrawingML nen **giu nguyen bo goc**; ban kinh goc tinh dung theo `border-radius` cua board, do day vien va mau vien lay tu `frameColor`.
- Toan bo noi dung nam trong text box cua shape do (`wps:txbx`), van la doan van + bang Word that nen sua/copy duoc truc tiep. Shape dat `spAutoFit` va duoc can giua trang theo ca hai chieu, chieu cao khoi tao lay tu chieu cao that cua khung tren board.
- Ho tro ca 3 layout `Cu` / `Thuong` / `VIP`, va doc dung mau da chinh tren board.

Nhung diem **khong** giong 100% board, do Word va CSS khac mo hinh dan trang:

- Font phai duoc cai san tren may mo file. `Be Vietnam Pro` / `Montserrat` / `Playfair Display` / `Lora` la webfont nhung base64 trong app, may khac khong co thi Word tu thay font. Chon `Malgun Gothic` neu can chac chan (Windows nao cung co, va phu ca tieng Han).
- Layout `Thuong` mat bo goc cua tung the va badge bo tron cua vai tro (o cua bang Word khong bo goc duoc); day la layout kem trung thuc nhat.
- Logo anh cua khach VIP chua duoc dua vao file `.docx`.
- Neu noi dung tran khoi khung tren board thi file Word cung se cao theo. Giam co chu hoac bot nguoi de gon lai mot trang.

## Tieng Han

Bundle khong nhung glyph Hangul nao. Khi go tieng Han:

- Chon `Malgun Gothic` (font he thong Windows, khong can mang) hoac `Noto Sans KR` (tai tu Google Fonts luc chon, can mang) de chu Han va chu Latin dung cung mot typeface.
- Neu de font khac, chu Han van hien dung va van xuat PNG dung, nhung trinh duyet se muon mot font he thong khac cho phan Hangul nen net chu se khac phan Latin.
- Khi xuat PNG voi `Noto Sans KR`, `buildFontEmbedCSS()` chi tai dung cac ky tu co tren board qua tham so `text=` cua Google Fonts, tranh phai nhung ca tram subset.
- Trong file `.docx`, thuoc tinh `w:eastAsia` luon duoc dat de Word chon dung font cho phan tieng Han.

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

## Thu tu menu chinh sua

Giu 3 tab `Noi dung / Content`, `Thiet ke / Design`, `Du lieu / Data`.

- `Du lieu`: Nhap Excel / mo JSON (luon hien, kem bo chon ngay), Dan danh sach (thu gon duoc), Ngay xuat file, Xoa tat ca (luon hien o cuoi). Nhap du lieu khong tu chuyen tab. Nhap Excel / mo JSON cung truy cap duoc khi dang o layout VIP.
- `Noi dung`: danh sach cong ty va thanh vien hien ngay; tung cong ty van thu gon va doi thu tu bang nut len/xuong. VIP hien ten khach truoc, logo / ten cong ty khach sau, khong can mo collapse noi dung.
- Cac tab giu vi tri cuon rieng trong phien hien tai. Cac nhom thu gon giu trang thai khi chinh gia tri, doi ngon ngu hoac chuyen tab/layout.

## Cau truc tab `Thiet ke`

Tab `Thiet ke` gom 6 muc cha, moi muc chia tiep thanh cac nhom con:

1. `Kich thuoc khung`: bat/tat keo chinh ngang/doc, chieu cao khung theo cac dieu khien san co. Mo san lan dau vao Thiet ke.
2. `Thong tin hien thi`: bat/tat chuc vu, vai tro va chuc vu xuong dong.
3. `Phong & co chu noi dung`: font, co chu tong the va co chu tung phan (cong ty, ten nguoi, chuc vu, vai tro theo layout).
4. `Can chinh & khoang cach`: can giua danh sach (layout Cu), gian dong tung phan, khoang cach giua cong ty/quanh dau `-`, thut le toan nhom/ten nguoi.
5. `Logo & WELCOME`: can ca cum va can rieng WELCOME, font WELCOME, co logo/co WELCOME, khoang cach logo-WELCOME va khoang cach xuong noi dung.
6. `Mau sac & duong vien`: mau chu dao, mau tung loai chu, mau/do day vien, vien khung ten (layout Cu), dat lai mau mac dinh.

Cac hang chi ap cho mot layout duoc boc trong `sc-if` theo `isOld` / `isStandard`. Markup dung cac class dung chung `wb-group`, `wb-group-title`, `wb-row`, `wb-row-label`, `wb-step`, `wb-step-val`, `wb-toggle-row`, `wb-switch`, `wb-color-input`, `wb-seg`, `wb-hint` khai bao trong `<style>` cua template.

Luu y khi sua: DC bo qua attribute `open` khong gia tri tren `<details>`. `redesignEditor()` sap xep cac khoi template truoc khi DC bien dich; khong di chuyen DOM do React quan ly. Script hanh vi dung `data-wb-section` de mo mac dinh nhom khung va giu trang thai mo/dong cua tung nhom trong phien.

## Cac diem logic quan trong

- Du lieu mac dinh nam trong `defaultData()`.
- Layout hien tai duoc chon bang `data.layout`: `old`, `standard`, hoac `vip`.
- Du lieu luu o localStorage key `wb-data-v2`.
- Mau sac luu o cac key `primary`, `welcomeColor`, `nameColor`, `positionColor`, `roleColor`, `frameColor`. Cac key nay deu optional; khi khong co thi lay mac dinh theo layout, nen bo qua tat ca se cho ra dung giao dien goc.
- Mau duoc day xuong board bang CSS variable tren khung: `--pri`, `--cname`, `--cpos`, `--crole`.
- Khoang cach khoi luu o `oldHeaderBodyGap` / `oldGroupGap` (layout `Cu`) va `stdHeaderBodyGap` / `stdGroupGap` (layout `Thuong`).
- Render tab `Cu` dung danh sach tinh toan `oldCompanies`.
- `oldListMetrics(d)` do chu bang canvas theo font/co chu hien tai, dung chung cho layout Cu va Word. Cot ten/chuc vu/vai tro dung chieu rong do tu toan danh sach; neu khung hep thi gioi han cot va cho chu xuong dong. Tinh lai sau khi font tai xong. Cot ten keo tay `oldNameWidth` chi duoc uu tien khi bat chinh kich thuoc; tat toggle se xoa gia tri nay de tro ve tu dong.
- `oldSeparatorPadding` la so px dem moi ben dau phan cach (0-120, gioi han them theo khung de tranh tran). Snapshot cu chi co `oldDashGap` van doc duoc: quy doi tu do rong o cu sang dem hai ben theo glyph dau gach cua font dang dung. Khong sua du lieu snapshot khi mo; lan chinh khoang cach tiep theo ghi truong moi.
- Render tab `Thuong` dung danh sach tinh toan `companies`.
- Render tab `VIP` dung `vip.names`, `vip.guestLogo`, `vip.guestName`.
- Nhap Excel dung SheetJS trong ham `parseWorkbook`.
- `sortedImportDates()` va `importDateTime()` trong loader sap ngay Excel cho ca luong nhap chinh va luong du phong. Chi sap danh sach ngay, khong sap lai dong du lieu; chap nhan ngay da chuan hoa tu serial Excel va chuoi dd/mm/yyyy hoac yyyy-mm-dd (ca dau `.` / `-` / `/`), kiem tra ngay thuc te theo UTC de tranh loi mui gio va ngay tran thang. JSON khong di qua buoc sap nay.
- Xuat PNG dung `html-to-image` trong `renderStagePng`.
- Xuat `.docx` bat dau tu `buildDocx()`. File `.docx` la mot zip chua OOXML nen dung lai `makeZip()` (tham so thu hai la MIME) va `crc32()` co san, khong them thu vien nao. `makeZip()` ghi che do STORE khong nen, Word chap nhan binh thuong; entry dau tien bat buoc la `[Content_Types].xml`.
- Noi dung Word dung trong `docxDocumentXml()`, moi layout mot ham: `docxOldBody()`, `docxStandardBody()`, `docxVipBody()`. Cac helper `docxRun/docxPara/docxCell/docxTable` phat XML dung thu tu schema cua WordprocessingML (vi du `w:rPr` phai la rFonts, b, caps, color, spacing, sz, lang).
- Khung bo goc: `docxDocumentXml()` boc toan bo noi dung trong `mc:AlternateContent`, nhanh `mc:Choice` la `wp:anchor` + `wps:wsp` voi `a:prstGeom prst="roundRect"`, nhanh `mc:Fallback` la `v:roundrect` (VML) cho reader cu. `w:tbl` nam trong `w:txbxContent` la hop le, Word doc binh thuong.
- `docxFrameSizePx()` doc chieu cao that cua khung tren DOM luc export de dat `wp:extent`; neu khong co DOM thi dung gia tri uoc luong va de `spAutoFit` cho Word tu co gian.
- Ban kinh bo goc: `a:gd name="adj"` tinh theo 1/100000 cua canh ngan hon, nen `border-radius` cua board duoc quy doi truc tiep sang ti le tuong duong.
- Quy doi kich thuoc: 1 px tren board = `docxScale()` point, tinh tu chieu rong khung board anh xa sang bang rong 270mm. Tu do co `docxHalfPt()` cho co chu va `docxTwips()` cho chieu rong/khoang cach.
- Giai dong dung `docxExactLine()` voi `w:lineRule="exact"`. Neu de `auto`, Word cong them leading cua font va lam board tran sang trang 2; san 1.2em de khong cat dau tieng Viet va chu Han.
- Bang thanh vien layout Cu trong DOCX dung cot co dinh tu `oldListMetrics`, khong chia phan trong con lai cho chuc vu/vai tro hay dung autofit. O dau phan cach khong cong le ngang rieng, de giu dung khoang dem tren board. Tai Word doi font san sang truoc khi do cot.

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
