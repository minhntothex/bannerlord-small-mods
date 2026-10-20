# Việt hóa các mod nhỏ

Submodule này tập hợp bản dịch tiếng Việt cho các mod Bannerlord có tổng số thẻ `<string>` dưới 1.000 và dưới 10 catalog chuỗi.

## Phạm vi hiện tại

Số liệu lấy từ các mod đang cài trong `~/Documents/Bannerlord` ngày 2026-10-20. Catalog là tệp XML trong `ModuleData/Languages` có ít nhất một thẻ `<string>`; `language_data.xml` không được tính. Số thẻ cộng qua mọi ngôn ngữ, nên các bản dịch lặp cùng ID vẫn được tính riêng.

| Mod | Thư mục cài đặt | Module ID | Catalog | Thẻ `<string>` |
|---|---|---|---:|---:|
| Agriculture Estate | `AgricultureEstate` | `AgricultureEstate` | 2 | 213 |
| Breakable Polearms | `BreakablePolearms` | `BreakablePolearms` | 2 | 40 |
| Clan Migration Tweaks | `ClanMigrationTweaks` | `ClanMigrationTweaks` | 1 | 42 |
| Companion to Family | `CompanionToFamily` | `CompanionToFamily` | 2 | 12 |
| From Ranks to Lords | `FromRankstoLords` | `From_Ranks_To_Lords` | 6 | 113 |
| Heroes Evolve | `HeroesEvolve` | `HeroesEvolve` | 5 | 75 |
| Performance Tweaks | `PerformanceTweaks` | `PerformanceTweaks` | 1 | 9 |
| Village Defense | `Xiangyong` | `Xiangyong` | 3 | 27 |
| **Tổng** |  |  | **22** | **531** |

Chỉ đưa catalog đích tiếng Việt vào repo. Giữ catalog nguồn trong thư mục cài mod; không sao chép nguồn vào submodule. Đặt bản dịch theo cấu trúc `translations/<ModuleId>/ModuleData/Languages/VI/`.

## Quy tắc

- Đọc [hướng dẫn dịch của dự án](docs/style-guide.md) và [bảng thuật ngữ](docs/glossary.md), rồi làm theo [quy trình chung](../../docs/workflow.md) và [quy tắc dịch chung](../../docs/translation-style.md).
- Giữ nguyên ID, placeholder, markup và cấu trúc catalog.
- Chỉ viết hướng dẫn cài đặt hoặc phát hành sau khi xác minh cách game nạp ngôn ngữ và tính tương thích.
