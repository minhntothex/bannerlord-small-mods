# Rà soát bản dịch và thông tin nguồn

Ngày rà soát: 2026-10-21. Mốc catalog: commit `beb73ab` của repo SmallMods.

Các bảng P2/P3 và N01–N07 bên dưới ghi nhận lần rà soát ban đầu. Sau khi áp dụng các sửa đổi, các lỗi câu chữ có thể sửa mà không làm lệch ID/placeholder và các thiếu sót tài liệu đã đóng; còn mục N04 và xác minh trong game chưa thể kết luận. Báo cáo được giữ lại cho tới khi các mục đó được xử lý.

## Trạng thái sau cập nhật

- Đã sửa các chuỗi P2/P3 có thể sửa mà không làm lệch ID/placeholder, thống nhất `gia tộc`, `người đồng hành`, và mẫu tên Xiangyong. Riêng `PRTL_COMPJOIN` vẫn cần xử lý cùng quyết định N04.
- Đã sửa chữ hoa/thường `source_root` (N01), thêm lệnh validator vào README (N02), ghi thư viện phụ thuộc (N03), lý do loại mod không có catalog vào backlog (N05), và nguồn tiếng Anh trong DLL của HeroesEvolve vào README (N07).
- N06 đã được xử lý trước đó: tiêu chí phạm vi đổi sang ID và số từ trong catalog nguồn chính.
- N04 còn mở: các ID DLL không có trong catalog nguồn và placeholder `{HERO}` của `PRTL_COMPJOIN` cần quyết định cách quản lý ID bổ sung; validator hiện không có ngoại lệ cho ID đích thừa.
- Chưa xác minh trong game cách hiển thị xuống dòng AgricultureEstate hoặc tên nhân vật trong `PRTL_COMPJOIN`. `agricultureestate_perk_rapiddevelopment` trùng nội dung nguồn với perk khác; đây là lỗi nguồn của mod, không thể sửa bằng cách đổi bản dịch theo catalog hiện tại.

## Phạm vi và căn cứ

| Phần | Cách rà |
| --- | --- |
| 8 mod, 9 catalog, 232 chuỗi | Đọc toàn bộ và so từng chuỗi với nguồn. Hồ sơ này ghi nhận HeroesEvolve được đối chiếu với DE và FR, Xiangyong với CNs và CNt. Chưa ghi nhận đối chiếu HeroesEvolve với RU, SP và TR theo style guide. |
| Validator | Trước khi thêm ba mod mới, `python tools/validate_localization.py --game-dir ~/Documents --mod SmallMods --strict` cho 0 lỗi, 0 cảnh báo. Lượt đầu sau khi thêm ba mod cho 0 lỗi, 9 cảnh báo. Sau khi sửa N01, chạy `python3 tools/validate_localization.py --game-dir ~/Documents --mod SmallMods`: 0 lỗi, 8 cảnh báo — 6 cảnh báo catalog và manifest chưa tạo của ba mod mới, 2 cảnh báo `CMT_MCM_Name` và `PT_MCM_Name` giống nguồn vì giữ tên mod tiếng Anh. |
| Thư mục mod `~/Documents/bannerlord` | Đếm lại catalog của 20 mod đang cài, đọc `SubModule.xml`, quét DLL để tìm ID văn bản `{=id}`. |
| Văn bản mặc định trong DLL | Lần rà bổ sung: so văn bản mặc định `{=id}…` trong DLL của 8 mod đã dịch với catalog nguồn, để tìm ID lệch nội dung hoặc placeholder. |
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
| From Ranks to Lords `PRTL_COMPJOIN` | has joined you as a companion. | đã gia nhập đội ngũ của bạn với tư cách bạn đồng hành. | DLL gọi `{=PRTL_COMPJOIN}{HERO} has joined you as a companion.`, nhưng catalog nguồn bỏ `{HERO}`. Khi catalog được nạp, tên nhân vật có thể biến mất ở cả bản Anh lẫn bản Việt. Đây là lỗi của mod. Thêm `{HERO}` vào bản Việt thì validator sẽ báo thừa placeholder, nên xử lý cùng quyết định ở N04 sau khi xem trong game. |

## P3: Lỗi biên tập nhỏ

| Mod / ID | Quan sát | Đề xuất |
| --- | --- | --- |
| From Ranks to Lords `BIO_OPEN_FIELD` | "chiến trường ngoài trời" ghép vào `BIO_BATTLE_LINE` thành "trận chiến tại chiến trường ngoài trời". | "vùng đồng trống", như Native ID `a3uKkLez`. |
| From Ranks to Lords `BIO_ENEMY_BANDITS` | "cướp" ghép thành "chống lại cướp". | "bọn cướp". |
| From Ranks to Lords `frc_promo_humble` | "Your Grace" được dịch thành "Thưa ngài", mất mức tôn kính. | Chọn cách gọi trang trọng hơn theo [quy ước xưng hô của Native](../../Native/docs/forms-of-address.md). |
| HeroesEvolve `hev_strip_reply` | "kẻ đã bị đánh bại" bỏ mất ý "người ngươi đã đánh bại", và người nói tự gọi mình là "kẻ". | "Ngươi định tước vũ khí của người mà ngươi đã đánh bại sao?" |
| AgricultureEstate `agricultureestate_hint_sell_goods_to_village`, `agricultureestate_hint_auto_buy_prisoners` | "Nhấp để {STATUS} tính năng này" lấy `{STATUS}` từ nhãn "Bật"/"Tắt". DLL xác nhận biến này nhận văn bản của `agricultureestate_on` và `agricultureestate_off`, nên câu hiện "Nhấp để Bật tính năng này", có chữ hoa giữa câu. Hai nhãn này còn dùng ở chỗ khác nên không sửa nhãn. | "Nhấp để chuyển sang: {STATUS}." |
| AgricultureEstate `agricultureestate_hint_slave_decline` | "violently rebel in mass" được dịch thành "đồng loạt nổi dậy", mất nghĩa "violently". | "…xác suất nô lệ đồng loạt nổi dậy bạo lực trong ngày." |
| AgricultureEstate `agricultureestate_perk_*` (10 ID) | Tiền tố "Agriculture Estate :" được dịch thành "Điền trang nông nghiệp:", trong khi `CMT_MCM_Name` và `PT_MCM_Name` giữ tên mod tiếng Anh. | Chốt một quy tắc cho tên mod và ghi vào style guide. |
| ClanMigrationTweaks `CMT_DefectOfferNotif` | "đang cân nhắc gia nhập {KINGDOM} bằng cách đổi phe" bị vòng vo. | "Thị tộc {CLAN} đang cân nhắc đổi phe sang {KINGDOM}." (sau khi sửa "thị tộc" theo mục P2 thì dùng "Gia tộc"). |
| ClanMigrationTweaks `CMT_MCM_DebugAlwaysPass_Name` | "Luôn cho phép thị tộc gia nhập/đổi phe…" nói quá. Nguồn chỉ cho qua lượt kiểm tra điểm, và mô tả ghi quy tắc denar vẫn áp dụng. | "Luôn đạt kiểm tra gia nhập/đổi phe vào vương quốc người chơi (Gỡ lỗi)" |
| From Ranks to Lords `AgLoj` | "I have served with honor" được dịch thành "đã chiến đấu hết mình", mất ý danh dự. | "…tôi đã phục vụ trong các chiến dịch của ngài và giữ trọn danh dự." |
| From Ranks to Lords `frc_promo_confident` | "cả hai ta đều biết vậy" lệch cặp xưng hô tôi/ngài của người nói. | "ngài và tôi đều biết vậy" |
| CompanionToFamily `CTF_DemoteOption` | Nguồn "I am revoking" là hành động ngay lúc nói; "Ta sẽ tước bỏ" chuyển thành ý tương lai. | "Ta tước bỏ thân phận quý tộc của ngươi." |
| PerformanceTweaks `PT_MCM_Enable_Desc` | "giảm tải CPU mỗi ngày" dễ hiểu thành ngày ngoài đời; nguồn là "daily tick". | "…giảm tải CPU ở mỗi lượt cập nhật ngày trong game…" |
| AgricultureEstate `agricultureestate_last_day_income` | "Thu nhập ngày trước" | "Thu nhập hôm qua" |
| AgricultureEstate `agricultureestate_hint_auto_buy_prisoners` | "toán quân" cho party. | "đội quân", như Native. |
| AgricultureEstate `agricultureestate_hint_land_clearing`, `..._patrol_upgrade`, `..._storehouse_upgrade` | "Chi phí: {…}{GOLD_ICON} denar" thêm chữ "denar" ngay sau biểu tượng tiền. Nguồn không có chữ này. | Bỏ "denar" sau `{GOLD_ICON}`. |
| Xiangyong `str_xy_militia_name`, `xy119_militia_name` | Catalog mặc định ghi "Dân binh Xiangyong của {SETTLEMENT_NAME}", bản CNs ghi "Dân binh {VILLAGE_NAME}". Bản CNs trùng tên với dân binh gốc của game. | Chốt mục Xiangyong trong glossary (đang chờ duyệt) rồi dùng một mẫu tên. |

## Cần kiểm tra trong game

- AgricultureEstate: 10 chuỗi nguồn ghi `\n` dạng chữ; bản Việt dùng ký tự xuống dòng `&#10;`. DLL của mod không có đoạn đổi `\n` thành xuống dòng. Văn bản mặc định trong DLL dùng ký tự xuống dòng thật, nên tác giả muốn xuống dòng và bản Việt đúng ý nguồn. Chỉ còn cần xác nhận cách hiển thị trong game.
- From Ranks to Lords `PRTL_COMPJOIN`: xem tên nhân vật có hiện trong thông báo không (mục P2).
- Enhanced Tournaments: đọc danh sách giải đấu với đủ 9 tổ hợp `ET_Dist_*` + `ET_Advice_*`, và xem `{TIER}` có đúng là số bậc không.
- Bandit Militias Redux: xem nhánh giới tính `{?LEADER.GENDER}` trong tiểu sử thủ lĩnh, và tên băng cướp khi chưa có tệp cài đặt MCM.
- True Caravan Masters: xem catalog Việt có được dùng khi game chạy tiếng Việt và MCM "Selected Language" để "Tự động".
- AgricultureEstate `agricultureestate_perk_rapiddevelopment`: nguồn trùng nguyên văn `agricultureestate_perk_insuranceplans`, và bản dịch chép theo. Đây là lỗi của mod.

## Thông tin nguồn còn thiếu

### N01. Đường dẫn thư mục mod sai chữ hoa/thường

| Vị trí | Khi phát hiện | Trạng thái hiện tại |
| --- | --- | --- |
| [README](../README.md) | `~/Documents/Bannerlord` | Đã sửa thành `~/Documents/bannerlord` (dòng 15). |
| [`backlogs/mod-catalog-counts.md`](../../../backlogs/mod-catalog-counts.md) | `~/Documents/Bannerlord` | Đã sửa thành `~/Documents/bannerlord` (dòng 1). |
| [`localization-validator.json`](../localization-validator.json) | `"source_root": "Bannerlord"` | Đã sửa thành `bannerlord`. |

Lệnh vẫn chạy trên macOS vì ổ đĩa không phân biệt chữ hoa/thường. Trên hệ thống có phân biệt, validator sẽ không tìm thấy nguồn.

Trước khi sửa, validator cảnh báo vì tên thư mục trong cấu hình không khớp chữ hoa/thường với thư mục trên đĩa.

### N02. Lệnh validator và giá trị `--game-dir`

Đã thêm lệnh kiểm tra vào README. `--game-dir` phải là thư mục cha `~/Documents`, vì `source_root` trỏ tới thư mục mod bên trong nó. Dùng chế độ mặc định khi kiểm tra SmallMods hiện tại vì ba mod mới chưa có catalog đích:

```sh
python3 tools/validate_localization.py --game-dir ~/Documents --mod SmallMods
```

### N03. Thư viện phụ thuộc

Đã ghi các thư viện phụ thuộc của 8 mod đã dịch trong README, theo `SubModule.xml` của bản cài ngày rà soát. Cấu hình chưa có `source_version`; theo [hướng dẫn validator](../../../docs/validator.md#id-ngoài-phạm-vi), trường này dùng để đối chiếu CSV khi dự án khai báo `--scope-exclusions`. Nó không tự phát hiện phiên bản catalog đang cài, nên chỉ cần thêm khi dùng cơ chế loại trừ đó.

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

`PRTL_COMPJOIN` (mục P2) có cùng nguyên nhân: ID có trong nguồn, nhưng văn bản trong DLL có placeholder `{HERO}` mà catalog nguồn không có. Cơ chế ngoại lệ, nếu có, cần bao cả ID thừa lẫn placeholder thừa.

Muốn dịch các chuỗi này thì phải thêm ID không có trong nguồn vào catalog Việt. Validator hiện sẽ báo đó là ID thừa. Cần quyết định có làm việc này không, và nếu có thì ghi cơ chế ngoại lệ trong cấu hình hoặc tài liệu.

### N05. Lý do loại các mod không có catalog

Backlog hiện ghi lý do loại từng nhóm mod. Kết quả kiểm tra chi tiết:

| Mod | Phiên bản | Quan sát |
| --- | --- | --- |
| Slavery | v1.0.1 | Tệp vật phẩm trong `ModuleData/items` dùng lại ID vật phẩm gốc, nên catalog Native đã phủ. Còn 12 tên vật phẩm và 19 chuỗi trong `Slavery.dll` dùng `{=!}`, loại game không cho dịch qua catalog. Thư mục `bin` chứa trọn bộ DLL của game và NavalDLC. |
| BetterPatrols, FrontlineMod, Performance, SpearPreference, TrueSpoilsOfWar, WaitIKnowYou | v1.0.0, v1.2.8, v1.6.0, v1.6.2, v0.4.2, v1.0.1 | Không có catalog, DLL không có chuỗi `{=id}`. Chữ hiển thị nếu có (ví dụ menu MCM) là tiếng Anh viết cứng, không dịch được qua XML. |

### N06. Tiêu chí phạm vi bỏ sót mod nhỏ

Tiêu chí cũ (dưới 1.000 thẻ `<string>` và dưới 10 catalog) đếm cả bản dịch sang ngôn ngữ khác. Vì vậy một số mod ít chuỗi bị loại:

| Mod | ID duy nhất | Catalog | Thẻ `<string>` | Lý do bị loại |
| --- | ---: | ---: | ---: | --- |
| EnhancedTournaments | 70 | 13 | 910 | Quá 10 catalog |
| BanditMilitiasRedux | 122 | 13 | 1.586 | Quá cả hai ngưỡng |
| TrueCaravanMasters | 169 | 6 | 1.014 | Quá 1.000 thẻ |

AgricultureEstate, mod đang trong phạm vi, có 107 ID. Nếu tính theo ID nguồn duy nhất, cả ba mod trên đều thuộc nhóm mod nhỏ.

Đã xử lý ngày 2026-10-21. Người dùng chốt tiêu chí mới: catalog nguồn chính có tối đa 200 ID duy nhất và khoảng 1.500 từ, không có hệ thống lời thoại lớn. [README](../README.md#tiêu-chí-phạm-vi) đã ghi tiêu chí và bảng phạm vi 11 mod. EnhancedTournaments, BanditMilitiasRedux và TrueCaravanMasters đã được thêm vào `localization-validator.json`. Sau khi sửa `source_root`, validator ở chế độ mặc định báo 0 lỗi và 8 cảnh báo: 6 cảnh báo catalog và manifest chưa tạo của ba mod mới, 2 cảnh báo văn bản giữ nguyên tên mod. Dramalord (479 ID, khoảng 4.900 từ, chủ yếu là lời thoại) cần dự án riêng.

Khi rà soát, số catalog và số thẻ của 8 mod cũ trong README khớp với bản cài đặt.

### N07. HeroesEvolve có văn bản tiếng Anh trong DLL

`~/Documents/bannerlord/HeroesEvolve/bin/Win64_Shipping_Client/HeroesEvolve.dll` có văn bản tiếng Anh mặc định cho cả 15 ID, ví dụ `{=hev_strip}Hand over your arms and armour.` và `{=hev_of_faction}{NAME} of the {FACTION}`. README, style guide và glossary ghi đúng rằng mod không có catalog tiếng Anh; các tài liệu này chưa ghi nhận văn bản tiếng Anh mặc định trong DLL.

README hiện ghi catalog DE là nguồn cho validator và văn bản tiếng Anh trong DLL là căn cứ đối chiếu ngữ nghĩa. Bản tiếng Anh khớp với đề xuất cho `hev_strip_friend_reply` ở mục P2: "I expected this from anyone but you. Take them, then. I have nothing else to say to you."

## Những phần đạt

BreakablePolearms, PerformanceTweaks và phần thiết lập MCM của ClanMigrationTweaks (ngoài thuật ngữ "thị tộc") giữ đủ điều kiện, giá trị mặc định và số liệu. Lời thoại HeroesEvolve giữ được giọng mỉa mai và đe dọa của nguồn, ví dụ `hev_strip_reprisal_reply`.

Manifest `language_data.xml` của 8 mod đều trỏ đúng `xml_path` và dùng dạng đầy đủ hợp lệ. "vũ khí cán dài" và tên kỹ năng "Quản trị" khớp Native. Nghĩa của `CMT_MCM_ClanDiscontinuation_*` (số ngày trước khi gia tộc độc lập giải thể) khớp với khóa cài đặt `IndependentClanSurvivalDays` trong DLL.

## Các mục còn mở

1. Quyết định cách quản lý ID và placeholder không có trong catalog nguồn (N04, `PRTL_COMPJOIN`). Ba mod chưa dịch cũng có ID DLL kiểu này: BanditMilitiasRedux `BMRPrisonerPretalk`, `BMRPrisonerExecuteCancel`, `BMREncDefected`; TrueCaravanMasters `tcm_tooltip_wage_floor`, `tcm_tooltip_prisoner_limit`. Backlog validator ghi nhận cần thiết kế cơ chế riêng trước khi thêm các ID này.
2. Kiểm tra trong game cách hiển thị xuống dòng của AgricultureEstate và tên nhân vật trong thông báo `PRTL_COMPJOIN`.
3. Báo lỗi nội dung trùng của `agricultureestate_perk_rapiddevelopment` cho tác giả mod; giữ nguyên bản dịch cho tới khi nguồn được sửa.
