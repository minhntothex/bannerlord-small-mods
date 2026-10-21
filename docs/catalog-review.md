# Rà soát bản dịch và thông tin nguồn

Ngày rà soát: 2026-10-21. Mốc catalog: commit `beb73ab` của repo SmallMods.

## Phạm vi và căn cứ

| Phần | Cách rà |
| --- | --- |
| 8 mod, 9 catalog, 223 chuỗi | Đọc toàn bộ và so từng chuỗi với nguồn. HeroesEvolve được so với catalog DE và FR; Xiangyong với CNs và CNt. |
| Validator | `python tools/validate_localization.py --game-dir ~/Documents --mod SmallMods --strict`: 0 lỗi, 0 cảnh báo. ID, placeholder, NFC và manifest đều đạt. |
| Thư mục mod `~/Documents/bannerlord` | Đếm lại catalog của 20 mod đang cài, đọc `SubModule.xml`, quét DLL để tìm ID văn bản `{=id}`. |
| Căn cứ | [Quy ước dịch](style-guide.md), [glossary dự án](glossary.md), [glossary chung](../../../docs/glossary.md). |

Chưa kiểm tra trong game. Chuỗi tiếng Anh viết cứng trong DLL mà không có `{=id}` chưa được quét đầy đủ.

P2 là lỗi sai nghĩa hoặc lệch lựa chọn đã duyệt trong glossary. P3 là lỗi biên tập nhỏ.

## P2: Lệch glossary chung

Hai thuật ngữ dưới đây đã duyệt trong [glossary chung](../../../docs/glossary.md), và chính các ID của SmallMods được dẫn làm nguồn.

| Thuật ngữ | Hiện tại | Glossary | Vị trí |
| --- | --- | --- | --- |
| clan | thị tộc | gia tộc | ClanMigrationTweaks: gần như mọi chuỗi có "clan", gồm `CMT_MCM_Group_ClanSettings`, `CMT_MCM_ClanDiscontinuation_Name`, `CMT_Body_DefectWar`, `CMT_Body_Mercenary`, `CMT_VassalJoin`. HeroesEvolve: `hev_strip_reply`, `hev_strip_vengeance`, `hev_strip_vengeance_reply`. From Ranks to Lords: `BIO_COMPANION`. |
| companion | bạn đồng hành | người đồng hành | CompanionToFamily: `CTF_DemoteOption`, `CTF_DemoteSuccess`. From Ranks to Lords: `BIO_COMPANION`, `PRTL_COMPJOIN`. |

## P2: Sai nghĩa và lệch giọng

| Mod / ID | Nguồn | Hiện tại | Đề xuất |
| --- | --- | --- | --- |
| AgricultureEstate `agricultureestate_tried_selling_clearing_land` | All owned land is being cleared. | Toàn bộ thửa đất đang sở hữu đều được khai khẩn. | Toàn bộ thửa đất đang sở hữu đều đang được khai khẩn. Câu hiện tại đọc như việc khai khẩn đã xong. |
| HeroesEvolve `hev_strip_friend_reply` | Von jedem hätte ich das erwartet, nur nicht von Euch. Nehmt sie also. Ich habe Euch nichts mehr zu sagen. | Ta có thể mong điều này từ bất cứ ai, trừ ngươi. Cứ lấy đi. Ta không còn gì để nói. | Ta có thể ngờ chuyện này từ bất kỳ ai, trừ ngươi. Cứ lấy đi. Ta không còn gì để nói với ngươi. "erwartet" là "ngờ tới", không phải "mong". |
| CompanionToFamily `CTF_PromoteResponse`, `CTF_DemoteResponse` | It would be my greatest honor… / As you command. I will continue to serve. | Người đồng hành xưng "thần" ở câu đầu, "Tôi" ở câu sau. | Chọn một cách xưng cho người đồng hành khi nói với chủ và dùng cho cả hai câu. |

## P3: Lỗi biên tập nhỏ

| Mod / ID | Quan sát | Đề xuất |
| --- | --- | --- |
| From Ranks to Lords `BIO_OPEN_FIELD` | "chiến trường ngoài trời" ghép vào `BIO_BATTLE_LINE` thành "trận chiến tại chiến trường ngoài trời". | "vùng đồng trống", như Native ID `a3uKkLez`. |
| From Ranks to Lords `BIO_ENEMY_BANDITS` | "cướp" ghép thành "chống lại cướp". | "bọn cướp". |
| From Ranks to Lords `frc_promo_humble` | "Your Grace" được dịch thành "Thưa ngài", mất mức tôn kính. | Chọn cách gọi trang trọng hơn theo [quy ước xưng hô của Native](../../Native/docs/forms-of-address.md). |
| HeroesEvolve `hev_strip_reply` | "kẻ đã bị đánh bại" bỏ mất ý "người ngươi đã đánh bại", và người nói tự gọi mình là "kẻ". | "Ngươi định tước vũ khí của người mà ngươi đã đánh bại sao?" |
| AgricultureEstate `agricultureestate_hint_sell_goods_to_village`, `agricultureestate_hint_auto_buy_prisoners` | "Nhấp để {STATUS} tính năng này" lấy `{STATUS}` từ nhãn "Bật"/"Tắt", nên hiện chữ hoa giữa câu. | Viết lại để `{STATUS}` đứng đầu mệnh đề, hoặc kiểm tra nguồn gán `{STATUS}`. |
| AgricultureEstate `agricultureestate_last_day_income` | "Thu nhập ngày trước" | "Thu nhập hôm qua" |
| AgricultureEstate `agricultureestate_hint_auto_buy_prisoners` | "toán quân" cho party. | "đội quân", như Native. |
| AgricultureEstate `agricultureestate_hint_land_clearing`, `..._patrol_upgrade`, `..._storehouse_upgrade` | "Chi phí: {…}{GOLD_ICON} denar" thêm chữ "denar" ngay sau biểu tượng tiền. Nguồn không có chữ này. | Bỏ "denar" sau `{GOLD_ICON}`. |
| Xiangyong `str_xy_militia_name`, `xy119_militia_name` | Catalog mặc định ghi "Dân binh Xiangyong của {SETTLEMENT_NAME}", bản CNs ghi "Dân binh {VILLAGE_NAME}". Bản CNs trùng tên với dân binh gốc của game. | Chốt mục Xiangyong trong glossary (đang chờ duyệt) rồi dùng một mẫu tên. |

## Cần kiểm tra trong game

- AgricultureEstate: 10 chuỗi nguồn ghi `\n` dạng chữ; bản Việt dùng ký tự xuống dòng `&#10;`. DLL của mod không có đoạn đổi `\n` thành xuống dòng, nên bản Việt có thể hiển thị đúng hơn bản gốc. Cần xem trong game.
- AgricultureEstate `agricultureestate_perk_rapiddevelopment`: nguồn trùng nguyên văn `agricultureestate_perk_insuranceplans`, và bản dịch chép theo. Đây là lỗi của mod.

## Thông tin nguồn còn thiếu

### N01. Đường dẫn thư mục mod sai chữ hoa/thường

| Vị trí | Hiện ghi | Thực tế |
| --- | --- | --- |
| [README](../README.md), dòng 7 | `~/Documents/Bannerlord` | `~/Documents/bannerlord` |
| [`backlogs/mod-catalog-counts.md`](../../../backlogs/mod-catalog-counts.md), dòng 1 | `~/Documents/Bannerlord` | `~/Documents/bannerlord` |
| [`localization-validator.json`](../localization-validator.json), dòng 5 | `"source_root": "Bannerlord"` | `bannerlord` |

Lệnh vẫn chạy trên macOS vì ổ đĩa không phân biệt chữ hoa/thường. Trên hệ thống có phân biệt, validator sẽ không tìm thấy nguồn.

### N02. Thiếu lệnh validator và giá trị `--game-dir`

README không có lệnh kiểm tra. `--game-dir` phải là thư mục cha `~/Documents`, vì `source_root` trỏ tới thư mục mod bên trong nó:

```sh
python tools/validate_localization.py --game-dir ~/Documents --mod SmallMods --strict
```

### N03. Chưa ghi phiên bản mod và thư viện phụ thuộc

README và cấu hình validator (không có `source_version`) chưa ghi phiên bản mod được dịch. Thiếu thông tin này thì không biết khi nào nguồn thay đổi, và không dùng được `--scope-exclusions`. Phiên bản đang cài, đọc từ `SubModule.xml`:

| Mod | Phiên bản | Phụ thuộc ngoài game gốc |
| --- | --- | --- |
| AgricultureEstate | v1.4.7.2 | Harmony |
| BreakablePolearms | v1.0.7 | UIExtenderEx, MCM |
| ClanMigrationTweaks | v1.2.3 | Harmony, ButterLib, UIExtenderEx, MCM |
| CompanionToFamily | v1.0.0 | Không có |
| FromRankstoLords | v1.0.0 | Không có |
| HeroesEvolve | v1.4.2 | Không có |
| PerformanceTweaks | v1.0.0 | Harmony, ButterLib, UIExtenderEx, MCM |
| Xiangyong | v1.1.11 | Harmony, MCM |

### N04. Mod gọi ID không có trong catalog nguồn

Validator chỉ so catalog nguồn với catalog đích nên không thấy các ID này. Quét chuỗi `{=id}` trong DLL của 8 mod cho kết quả:

| Mod | ID trong DLL | Văn bản mặc định | Hệ quả |
| --- | --- | --- | --- |
| ClanMigrationTweaks | `CMT_Body_VassalJoin` | {CLAN} wishes to join {KINGDOM} as a vassal. | Catalog nguồn chỉ có `CMT_VassalJoin`, nên thông báo đề nghị chư hầu hiện tiếng Anh dù đã có bản dịch. |
| From Ranks to Lords | `PRTL_COMP_LIMIT_INCREASED` | Your clan's companion limit has increased. | Hiện tiếng Anh. |
| From Ranks to Lords | `PRTL_NO_BATTLES` | several battles, unrecorded by the scribes | Hiện tiếng Anh trong tiểu sử. |
| From Ranks to Lords | `BIO_FULL` | {SERVICE} {PROMOTION} {BATTLES} {COMPANION} | Chỉ ghép các đoạn; có thể giữ nguyên thứ tự. |

Muốn dịch các chuỗi này thì phải thêm ID không có trong nguồn vào catalog Việt. Validator hiện sẽ báo đó là ID thừa. Cần quyết định có làm việc này không, và nếu có thì ghi cơ chế ngoại lệ trong cấu hình hoặc tài liệu.

### N05. Lý do loại các mod không có catalog chưa được ghi

Backlog chỉ ghi chung là "không có thẻ `<string>`". Kết quả kiểm tra:

| Mod | Phiên bản | Quan sát |
| --- | --- | --- |
| Slavery | v1.0.1 | Tệp vật phẩm trong `ModuleData/items` dùng lại ID vật phẩm gốc, nên catalog Native đã phủ. Còn 12 tên vật phẩm và 19 chuỗi trong `Slavery.dll` dùng `{=!}`, loại game không cho dịch qua catalog. Thư mục `bin` chứa trọn bộ DLL của game và NavalDLC. |
| BetterPatrols, FrontlineMod, Performance, SpearPreference, TrueSpoilsOfWar, WaitIKnowYou | v1.0.0, v1.2.8, v1.6.0, v1.6.2, v0.4.2, v1.0.1 | Không có catalog, DLL không có chuỗi `{=id}`. Chữ hiển thị nếu có (ví dụ menu MCM) là tiếng Anh viết cứng, không dịch được qua XML. |

### N06. Tiêu chí phạm vi bỏ sót mod nhỏ

Tiêu chí hiện tại (dưới 1.000 thẻ `<string>` và dưới 10 catalog) đếm cả bản dịch sang ngôn ngữ khác. Vì vậy một số mod ít chuỗi bị loại:

| Mod | ID duy nhất | Catalog | Thẻ `<string>` | Lý do bị loại |
| --- | ---: | ---: | ---: | --- |
| EnhancedTournaments | 70 | 13 | 910 | Quá 10 catalog |
| BanditMilitiasRedux | 122 | 13 | 1.586 | Quá cả hai ngưỡng |
| TrueCaravanMasters | 169 | 6 | 1.014 | Quá 1.000 thẻ |

AgricultureEstate, mod đang trong phạm vi, có 107 ID. Nếu tính theo ID nguồn duy nhất, cả ba mod trên đều thuộc nhóm mod nhỏ.

Đã xử lý ngày 2026-10-21. Người dùng chốt tiêu chí mới: catalog nguồn chính có tối đa 200 ID duy nhất và khoảng 1.500 từ, không có hệ thống lời thoại lớn. [README](../README.md#tiêu-chí-phạm-vi) đã ghi tiêu chí và bảng phạm vi 11 mod. EnhancedTournaments, BanditMilitiasRedux và TrueCaravanMasters đã được thêm vào `localization-validator.json`. Validator ở chế độ mặc định báo 0 lỗi và 6 cảnh báo, tất cả là catalog và manifest chưa tạo của ba mod này. Dramalord (479 ID, khoảng 4.900 từ, chủ yếu là lời thoại) cần dự án riêng.

Khi rà soát, số catalog và số thẻ của 8 mod cũ trong README khớp với bản cài đặt.

## Những phần đạt

BreakablePolearms, PerformanceTweaks và phần thiết lập MCM của ClanMigrationTweaks (ngoài thuật ngữ "thị tộc") giữ đủ điều kiện, giá trị mặc định và số liệu. Lời thoại HeroesEvolve giữ được giọng mỉa mai và đe dọa của nguồn, ví dụ `hev_strip_reprisal_reply`.

## Thứ tự xử lý đề xuất

1. Đồng bộ "gia tộc" và "người đồng hành" theo glossary chung.
2. Sửa ba lỗi nghĩa và xưng hô ở mục P2.
3. Sửa N01 và N02, ghi phiên bản mod (N03) vào README và `source_version`.
4. Quyết định cách xử lý ID ngoài nguồn (N04). Ba mod mới cũng có ID loại này: BanditMilitiasRedux `BMRPrisonerPretalk`, `BMRPrisonerExecuteCancel`, `BMREncDefected`; TrueCaravanMasters `tcm_tooltip_wage_floor`, `tcm_tooltip_prisoner_limit`.
5. Sửa các mục P3, rồi kiểm tra xuống dòng của AgricultureEstate trong game.
