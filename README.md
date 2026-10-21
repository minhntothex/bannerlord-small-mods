# Việt hóa các mod nhỏ

Submodule này tập hợp bản dịch tiếng Việt cho các mod Bannerlord nhỏ.

## Tiêu chí phạm vi

Một mod thuộc dự án khi catalog của ngôn ngữ nguồn chính có tối đa 200 ID duy nhất và khoảng 1.500 từ, đồng thời không có hệ thống lời thoại lớn cần quy ước giọng văn riêng. Ngôn ngữ nguồn chính ưu tiên tiếng Anh; khi mod không có catalog tiếng Anh, chọn một catalog khác và ghi lý do.

Chỉ đếm catalog của ngôn ngữ nguồn chính. Bản dịch có sẵn sang ngôn ngữ khác không được cộng vào khối lượng. Tiêu chí cũ (dưới 1.000 thẻ `<string>` cộng qua mọi ngôn ngữ và dưới 10 catalog) loại nhầm các mod có nhiều bản dịch sẵn nhưng ít chuỗi, nên được thay ngày 2026-10-21.

Mod có khối lượng lớn hơn được làm thành dự án riêng, như `mods/CrownAndKin`. Dramalord (479 ID, khoảng 4.900 từ, chủ yếu là lời thoại) nằm ngoài phạm vi này.

## Phạm vi hiện tại

Số liệu lấy từ các mod đang cài trong `~/Documents/bannerlord` ngày 2026-10-21. Cột "Từ" đếm từ trong catalog nguồn chính, không tính placeholder và mã biểu cảm.

| Mod | Thư mục cài đặt | Module ID | Phiên bản | Catalog nguồn chính | ID | Từ | Trạng thái |
|---|---|---|---|---|---:|---:|---|
| Agriculture Estate | `AgricultureEstate` | `AgricultureEstate` | v1.4.7.2 | `std_module_strings_xml.xml` (EN) | 107 | 693 | Đã dịch |
| Breakable Polearms | `BreakablePolearms` | `BreakablePolearms` | v1.0.7 | `str_EN.xml` (EN) | 20 | 128 | Đã dịch |
| Clan Migration Tweaks | `ClanMigrationTweaks` | `ClanMigrationTweaks` | v1.2.3 | `EN/cmt_strings.xml` (EN) | 42 | 433 | Đã dịch |
| Companion to Family | `CompanionToFamily` | `CompanionToFamily` | v1.0.0 | `EN/str_companiontofamily_en.xml` (EN) | 6 | 66 | Đã dịch |
| From Ranks to Lords | `FromRankstoLords` | `From_Ranks_To_Lords` | v1.0.0 | `language_strings.xml` (EN) | 19 | 271 | Đã dịch |
| Heroes Evolve | `HeroesEvolve` | `HeroesEvolve` | v1.4.2 | `DE/hev_strings_ger.xml` (DE; không có EN) | 15 | 198 | Đã dịch |
| Performance Tweaks | `PerformanceTweaks` | `PerformanceTweaks` | v1.0.0 | `EN/pt_strings.xml` (EN) | 9 | 59 | Đã dịch |
| Village Defense | `Xiangyong` | `Xiangyong` | v1.1.11 | `std_module_strings_xml.xml` (EN) và `CNs/std_module_strings_CNs.xml` (CNs) | 1 + 13 | 2 + 95 ký tự CNs | Đã dịch |
| Enhanced Tournaments | `EnhancedTournaments` | `EnhancedTournaments` | v1.1.1 | `ES/std_enhancedtournaments_strings_ES.xml` (ES; không có EN) | 70 | 317 | Chưa dịch |
| Bandit Militias Redux | `BanditMilitiasRedux` | `BanditMilitiasRedux` | v4.8.10 | `std_common_strings_xml.xml` (EN) | 122 | 909 | Chưa dịch |
| True Caravan Masters | `TrueCaravanMasters` | `TrueCaravanMasters` | v1.0.7.1 | `std_module_strings_xml.xml` (EN) | 169 | 1.343 | Chưa dịch |

Ghi chú cho các mod chưa dịch:

- Enhanced Tournaments không có catalog tiếng Anh. DLL của mod có văn bản tiếng Anh mặc định cho 50/70 ID; 20 ID còn lại cần đối chiếu catalog ES và IT. Danh sách giải đấu ghép mẫu `{TOWN_LINK}. {DIST_DESC}, {TRAVEL_ADVICE}…`, nên các mảnh như `ET_Dist_Close` và `ET_Advice_Safe` phải dịch thành mệnh đề ghép được vào mẫu.
- Bandit Militias Redux có 12 chuỗi dùng nhánh điều kiện `{?…}`. Catalog nguồn trùng tên `std_common_strings_xml.xml` với một catalog của Native nhưng nằm trong module riêng.
- True Caravan Masters nên dịch sau khi chốt thuật ngữ caravan; Native đang dùng cả "đoàn buôn" lẫn "đoàn lữ hành".

Chỉ đưa catalog đích tiếng Việt vào repo. Giữ catalog nguồn trong thư mục cài mod; không sao chép nguồn vào submodule. Đặt bản dịch theo cấu trúc `translations/<ModuleId>/ModuleData/Languages/VI/`.

## Thư viện phụ thuộc của các mod đã dịch

Danh sách đọc từ `SubModule.xml` của bản cài đặt ngày 2026-10-21; không tính game gốc.

| Mod | Thư viện phụ thuộc |
|---|---|
| Agriculture Estate | Harmony |
| Breakable Polearms | UIExtenderEx, MCM |
| Clan Migration Tweaks | Harmony, ButterLib, UIExtenderEx, MCM |
| Companion to Family | Không có |
| From Ranks to Lords | Không có |
| Heroes Evolve | Không có |
| Performance Tweaks | Harmony, ButterLib, UIExtenderEx, MCM |
| Village Defense (Xiangyong) | Harmony, MCM |

Heroes Evolve không có catalog tiếng Anh. Cấu hình dùng catalog tiếng Đức để kiểm độ phủ; DLL chứa văn bản mặc định tiếng Anh cho 15 ID, dùng để đối chiếu ngữ nghĩa.

## Quy tắc

- Đọc [bảng thuật ngữ chung](../../docs/glossary.md), [hướng dẫn dịch của dự án](docs/style-guide.md) và [bảng thuật ngữ của dự án](docs/glossary.md), rồi làm theo [quy trình chung](../../docs/workflow.md) và [quy tắc dịch chung](../../docs/translation-style.md).
- Giữ nguyên ID, placeholder, markup và cấu trúc catalog.
- Chỉ viết hướng dẫn cài đặt hoặc phát hành sau khi xác minh cách game nạp ngôn ngữ và tính tương thích.

## Kiểm tra bản dịch

Chạy từ thư mục gốc repo. `--game-dir` trỏ tới thư mục cha của `bannerlord`:

```sh
python3 tools/validate_localization.py --game-dir ~/Documents --mod SmallMods
```

Lệnh mặc định cho phép catalog chưa dịch trong phạm vi; dùng `--strict` khi kiểm một catalog hoặc phạm vi đã hoàn tất.
