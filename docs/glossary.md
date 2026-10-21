# Bảng thuật ngữ

Bảng này ghi các thuật ngữ riêng của những mod nhỏ. Với thuật ngữ dùng chung, tra [bảng thuật ngữ chung](../../../docs/glossary.md); cột `Dự án` cho biết mod có thuật ngữ đó. Các cách dịch mới dưới đây đang chờ duyệt.

Mỗi mục cần có tên mod, đường dẫn catalog và ID để tra lại nguồn. Nếu catalog không phải tiếng Anh, ghi ngôn ngữ và chỗ còn mơ hồ.

Heroes Evolve chưa có catalog tiếng Anh. Các mục của mod này được đối chiếu với catalog DE/FR/RU/SP/TR: `ModuleData/Languages/DE/hev_strings_ger.xml`, `FR/hev_strings_fre.xml`, `RU/hev_strings_rus.xml`, `SP/hev_strings_spa.xml` và `TR/hev_strings_tur.xml`.

| Mod / Module ID | Thuật ngữ nguồn | Tiếng Việt | Loại | Trạng thái, nguồn và ghi chú |
| --- | --- | --- | --- | --- |
| AgricultureEstate | estate | điền trang | Tài sản / khu đất | Nháp, cần duyệt. `ModuleData/Languages/std_module_strings_xml.xml`, ID `agricultureestate_estate_village`, `agricultureestate_hint_show_ledger`. |
| AgricultureEstate | land management | quản lý đất đai | Giao diện | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_gamemenu_land_management`, `agricultureestate_ui_landmanagement`. |
| AgricultureEstate | land plot | thửa đất | Đơn vị đất | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_ui_landplots`, `agricultureestate_ui_undev_landplots`. |
| AgricultureEstate | land clearance | khai khẩn đất | Dự án | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_ui_land_clearance`, `agricultureestate_hint_land_clearing`. |
| AgricultureEstate | land rent | tiền thuê đất | Thu nhập | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_estimated_daily_output_rent`, `agricultureestate_ui_income_unused_land`. |
| AgricultureEstate | slave decline | tỷ lệ nô lệ trốn thoát | Chỉ số | Nháp, cần duyệt; gợi ý trong catalog định nghĩa đây là xác suất nô lệ trốn mỗi ngày. Cùng catalog, ID `agricultureestate_ui_slave_decline`, `agricultureestate_hint_slave_decline`. |
| AgricultureEstate | revolt risk | nguy cơ nổi loạn | Chỉ số | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_ui_revolt_risk`, `agricultureestate_hint_slave_decline`. |
| AgricultureEstate | stockpile | kho dự trữ | Kho vật phẩm | Nháp, cần duyệt. Cùng catalog, ID `agricultureestate_ui_stockpile`, `agricultureestate_hint_production`. |
| BanditMilitiasRedux | Bandit Militia (BM) | băng cướp | Đội quân | Đã chọn theo yêu cầu người dùng; tránh trùng "dân binh" của làng. Toán cướp thường của game vẫn là "toán cướp". `ModuleData/Languages/std_common_strings_xml.xml`, ID `BMStringSettingDefault`, `BMMergeSizeDesc`. |
| BanditMilitiasRedux | brigand chief / leader | tướng cướp / thủ lĩnh (băng cướp) | Nhân vật | Nháp, cần duyệt. Cùng catalog, ID `BMREncBase`, `BMExecHonorXp`. |
| BanditMilitiasRedux | merge / split | sáp nhập / tách băng | Cơ chế | Nháp, cần duyệt. Cùng catalog, ID `BMMergeSize`, `BMSplit`, `BMCooldown`. |
| BreakablePolearms | swinging / non-swinging polearm | vũ khí cán dài có / không có đòn vung | Nhóm vũ khí | Nháp, cần duyệt. Cùng catalog, ID `BreakableOptG001`, `BreakableOptG002`. |
| BreakablePolearms | hit points | độ bền | Thuộc tính vũ khí | Nháp, cần duyệt. Cùng catalog, ID `BreakableOpt002`, `BreakableOpt004`. |
| ClanMigrationTweaks | defection | đổi phe | Quan hệ chính trị | Nháp, cần duyệt; dùng cho một gia tộc rời vương quốc để gia nhập phe khác. Cùng catalog, ID `CMT_DefectOffer`, `CMT_Body_DefectWar`. |
| CompanionToFamily | adopt into the family | nhận vào gia tộc | Quan hệ gia tộc | Nháp, cần duyệt. Cùng catalog, ID `CTF_PromoteOption`, `CTF_PromoteSuccess`. |
| CompanionToFamily | noble status | thân phận quý tộc | Địa vị | Nháp, cần duyệt. Cùng catalog, ID `CTF_PromoteOption`, `CTF_DemoteOption`. |
| EnhancedTournaments | prize / grand prize | giải thưởng / giải thưởng chính | Phần thưởng giải đấu | Nháp, cần duyệt; khớp Native "Giải thưởng giải đấu". Nguồn ES `ModuleData/Languages/ES/std_enhancedtournaments_strings_ES.xml` (EN trong DLL), ID `ET_Set_Reroll`, `ET_List_Item_Natural`. |
| EnhancedTournaments | reroll / negotiate for a different prize | đổi giải thưởng / thương lượng đổi giải thưởng | Hành động | Nháp, cần duyệt. Cùng catalog, ID `ET_Set_Reroll`, `ET_Menu_Reroll`, `ET_Set_MaxRerolls`. |
| EnhancedTournaments | sponsorship | tài trợ / tiền tài trợ | Thu nhập | Nháp, cần duyệt; khoản denar nhận hằng ngày theo thứ hạng. Cùng catalog, ID `ET_Grp_Sponsor`, `ET_Set_SpBase`, `ET_Msg_SponsorDaily`. |
| EnhancedTournaments | participants | những người tham gia (giải đấu) | Nhân vật | Nháp, cần duyệt. Cùng catalog, ID `ET_Set_Relation_Hint`, `ET_Msg_RelAll`. |
| From_Ranks_To_Lords | rank and file | binh lính thường | Cấp bậc quân đội | Nháp, cần duyệt. `ModuleData/Languages/language_strings.xml`, ID `frc_promo_confident`. |
| From_Ranks_To_Lords | promotion | thăng chức | Thăng tiến | Nháp, cần duyệt. Cùng catalog, ID `BIO_PROMOTION`, `0Jqye`. |
| HeroesEvolve | `Waffen und Rüstung` (DE); `armes et armure` (FR); `armas y armadura` (SP); `оружие и доспехи` (RU); `silahlar ve zırh` (TR) | tước vũ khí và giáp | Hành động / chiến lợi phẩm | Nháp, cần duyệt; không có catalog tiếng Anh. Các cụm xuất hiện trong lời yêu cầu giao nộp trang bị, ID `hev_strip`, và thông báo mất trang bị, ID `hev_robbed`. |
| HeroesEvolve | `Vergeltung` (DE); `représailles` (FR); `в отместку` (RU); `en represalia` (SP); `misilleme` (TR) | trả đũa | Hành động đáp trả | Nháp, cần duyệt; không có catalog tiếng Anh. Từ chỉ hành động trả đũa có trong thông báo ở ID `hev_robbed_reprisal` và lời thoại ở `hev_strip_vengeance`. |
| HeroesEvolve | `zusammengesucht` (DE); `récupéré` (FR); `раздобыли` (RU); `rapiñado` (SP); `topladın` (TR) | trang bị nhặt được | Trang bị | Nháp, cần duyệt; không có catalog tiếng Anh. Các động từ mô tả việc kiếm/nhặt trang bị trong ID `hev_released_scavenged`; từ chỉ trang bị tương ứng là `Ausrüstung`, `équipement`, `снаряжение`, `equipo`, `teçhizat`. |
| PerformanceTweaks | romance optimization | tối ưu hóa hệ thống tình cảm | Tối ưu hiệu năng | Nháp, cần duyệt. `ModuleData/Languages/EN/pt_strings.xml`, ID `PT_MCM_Enable_Name`, `PT_MCM_Enable_Desc`. |
| PerformanceTweaks | cache validation | kiểm tra bộ nhớ đệm | Kiểm tra kỹ thuật | Nháp, cần duyệt. Cùng catalog, ID `PT_MCM_RomanceValidate_Name`, `PT_MCM_RomanceValidate_Desc`. |
| TrueCaravanMasters | Merchant Guild License / guild charter | giấy phép Thương hội (khu vực) / giấy phép thương hội | Giấy phép | Nháp, cần duyệt; "charter" dịch là giấy phép vì mod dùng như từ đồng nghĩa với license. `ModuleData/Languages/std_module_strings_xml.xml`, ID `tcm_buy_license_ask`, `tcm_buy_license_cost_response`. |
| TrueCaravanMasters | sponsor (a license) | bảo trợ | Hành động | Nháp, cần duyệt. Cùng catalog, ID `tcm_buy_license_cost_response`, `tcm_mcm_min_prosperity_for_license_hint`. |
| TrueCaravanMasters | Caravan Master | Trưởng đoàn buôn | Vai trò nhân vật | Nháp, cần duyệt; khớp Native "Trưởng Đoàn Buôn Lo Lắng". Cùng catalog, ID `tcm_ransom_text`, `tcm_mcm_spawn_companions`. |
| TrueCaravanMasters | Basic / Elite / Master caravan | đoàn buôn Thường / Tinh nhuệ / Thượng hạng | Bậc đoàn buôn | Nháp, cần duyệt. Cùng catalog, ID `tcm_mcm_base_size_basic`, `tcm_mcm_base_size_elite`, `tcm_mcm_base_size_master`. |
| TrueCaravanMasters | caravan slot | suất đoàn buôn | Giới hạn | Nháp, cần duyệt. Cùng catalog, ID `tcm_mcm_disable_limits_hint`, `tcm_mcm_limit_req_hint`. |
| Xiangyong | Xiangyong / 乡勇 / 鄉勇 | dân binh Xiangyong | Đơn vị dân quân | Dùng tên riêng theo catalog EN `Xiangyong of {SETTLEMENT_NAME}`; thống nhất mẫu `Dân binh Xiangyong của {tên địa điểm}` cho cả catalog mặc định và CNs/CNt. Nguồn: `ModuleData/Languages/std_module_strings_xml.xml`, ID `str_xy_militia_name`, và `CNs/std_module_strings_CNs.xml` / `CNt/std_module_strings_CNt.xml`, ID `xy119_militia_name`. |
