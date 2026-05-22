# tqsk — API Reference

16 endpoints.

---

## AdmetDetail

**Path:** `POST /tqsk/general/v1/chem/admet`

**Description:** 物质ADMET-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `pedia_id` | string | no | 物质id，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `pedia_id` | string | 物质id |
| `total` | integer | 总数 |
| `admet_info[].tag_info.grade_name_cn` | string |  |
| `admet_info[].tag_info.class_name_cn` | string |  |
| `admet_info[].value_cn` | string | 值（中文） |
| `admet_info[].ref` | string | 参考文献 |

---

## CodeDetail

**Path:** `POST /tqsk/general/v1/chem/code`

**Description:** 物质标识信息-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `pedia_id` | string | no | 物质id，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `pedia_id` | string | 物质id |
| `code.cas` | array | cas |
| `code.inchikey` | string | inchikey |
| `code.smiles` | string | smiles |
| `code.mol` | string | mol |
| `code.mdl` | array | mdl |
| `code.einecs` | array | einecs |
| `code.beilstein` | array | beilstein |
| `code.ec_num` | string | ec_num |
| `code.merck_id` | string | merck_id |

---

## CodeToImage

**Path:** `POST /tqsk/general/v1/trans/code`

**Description:** mol码smiles码转图片-接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `code_type` | Code Type | no | - code_type_mol: mol
 - code_type_smiles: smiles |
| `code` | array | no | mol码或smiles码 |
| `mol` | string | no | mol码，优先 |
| `smiles` | string | no | smiles码，仅在mol码不存在时使用 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `result[].code` | string | mol码或smiles码 |
| `result[].error` | string | 错误 |
| `result[].structure_image` | string | 结构式图片svg |

---

## CrystalDetail

**Path:** `POST /tqsk/general/v1/crystal/detail`

**Description:** 晶体信息-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `inchikey` | string | no | InChiKey，必填。例：YXFVVABEGXRONW-UHFFFAOYSA-N |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].pedia_id` | string | 物质id |
| `list[].cif` | string | 3D结构图 |
| `list[].spacegroup_name` | string | 空间群名称 |
| `list[].spacegroup_num` | string | 空间群符号 |
| `list[].cell_volume` | string | 晶胞体积 |
| `list[].length_a` | string | 晶胞参数 q |
| `list[].length_b` | string | 晶胞参数 b |
| `list[].length_c` | string | 晶胞参数 c |
| `list[].angle_alpha` | string | 晶胞参数 α |
| `list[].angle_beta` | string | 晶胞参数 β |
| `list[].angle_gamma` | string | 晶胞参数 γ |
| `list[].ref.author_name` | array | 作者名称 |
| `list[].ref.journals_name` | string | 期刊名称 |
| `list[].ref.page` | string | 页 |
| `list[].ref.volume` | string | 卷 |
| `list[].ref.year` | string | 年 |
| `list[].ref.doi` | string | DOI |
| `list[].r_factor` | string | R值 |
| `list[].melting_point` | string | 熔点 |
| `list[].temperature` | string | 温度 |

---

## CrystalSearch

**Path:** `POST /tqsk/general/v1/crystal/search`

**Description:** 晶体检索-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `molecular_formula` | string | no | 化学式。例：C7H8 |
| `doi` | string | no | doi。例：10.1021/acs.cgd.5b01538 |
| `spacegroup_name` | string | no | 空间群。例：Pbca |
| `cell_volume.min` | string | no | 最小值（空字符串表示不限制） |
| `cell_volume.max` | string | no | 最大值（空字符串表示不限制） |
| `angle_alpha.min` | string | no | 最小值（空字符串表示不限制） |
| `angle_alpha.max` | string | no | 最大值（空字符串表示不限制） |
| `angle_beta.min` | string | no | 最小值（空字符串表示不限制） |
| `angle_beta.max` | string | no | 最大值（空字符串表示不限制） |
| `angle_gamma.min` | string | no | 最小值（空字符串表示不限制） |
| `angle_gamma.max` | string | no | 最大值（空字符串表示不限制） |
| `length_a.min` | string | no | 最小值（空字符串表示不限制） |
| `length_a.max` | string | no | 最大值（空字符串表示不限制） |
| `length_b.min` | string | no | 最小值（空字符串表示不限制） |
| `length_b.max` | string | no | 最大值（空字符串表示不限制） |
| `length_c.min` | string | no | 最小值（空字符串表示不限制） |
| `length_c.max` | string | no | 最大值（空字符串表示不限制） |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].pedia_id` | string | 物质ID |
| `list[].title` | string | 标题 |
| `list[].inchikey` | string | InChiKey |
| `list[].molecular_formula` | string | 分子结构式 |
| `list[].molecular_weight` | number | 分子量 |
| `list[].cas` | array | CAS号 |
| `list[].name_cn` | array | 中文名称 |
| `list[].name_en` | array | 英文名称 |

---

## MedDetail

**Path:** `POST /tqsk/general/v1/med/detail`

**Description:** 文摘信息-详情信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `tqid` | string | yes | 文献id |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `tqid` | string | tqid |
| `title` | string | 篇名 |
| `abstract` | string | 摘要 |
| `keywords` | array | 关键词 |
| `doi` | string | doi |
| `author_info[].author_name` | string | 作者 |
| `author_info[].is_first` | string | 第一作者 |
| `author_info[].is_correspond` | string | 通讯作者 |
| `author_info[].email` | array | 邮箱 |
| `author_info[].author_orcid` | string | 作者编号 |
| `author_info[].corporation_index` | array | 机构编号 |
| `journal_full` | string | 期刊全称 |
| `publish_date` | string | 发表时间 |
| `last_if` | string | 最新影响因子 |
| `five_year_if` | string | 五年影响因子 |
| `pmid` | string | pmid |
| `pmcid` | string | pmcid |
| `is_oa` | string | 公开标识 |
| `article_url` | string | 原文链接 |
| `year` | string | 年份 |
| `volume` | string | 期 |
| `issue` | string | 卷 |
| `start_page` | string | 起始页 |
| `end_page` | string | 结束页 |
| `publication_type` | array | 文献类型 |
| `citation_count` | string | 被引次数 |
| `corporation[].index` | string | 机构编号 |
| `corporation[].name` | string | 机构名称 |
| `corporation[].address` | string | 机构地址 |
| `corporation[].tel` | string | 机构电话 |
| `ref_info[].ref_title` | string | 篇名 |
| `ref_info[].ref_author` | array | 作者 |
| `ref_info[].ref_info` | string | 文献信息 |
| `ref_info[].ref_doi` | string | doi |
| `ref_info[].ref_url` | string | url |
| `ref_info[].ref_pmid` | string | pmid |
| `ref_info[].is_relate` | string | 相关文献 |
| `mesh_major[].mesh_term` | string | mesh主题词 |
| `mesh_major[].tree_numbers` | array | mesh树状结构号 |
| `mesh_major[].mesh_subheadings` | array | mesh副主题词 |
| `mesh_normal[].mesh_term` | string | mesh主题词 |
| `mesh_normal[].tree_numbers` | array | mesh树状结构号 |
| `mesh_normal[].mesh_subheadings` | array | mesh副主题词 |
| `update_date` | string | 更新日期 |
| `update_time` | string | 更新时间 |

---

## MedHybridSearch

**Path:** `POST /tqsk/general/v1/med/hybrid_search`

**Description:** 文摘信息-混合检索

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `question` | string | no | 用户提问 - 用于向量相似度检索 |
| `keywords` | array | no | 检索关键词 - 一般从用户提问中 提取关键词用于补充 混合检索 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].tqid` | string | tqid |
| `list[].abstract` | string | 摘要 |
| `list[].title` | string | 篇名 |
| `list[].author_name` | array | 作者信息 |
| `list[].doi` | string | doi |
| `list[].journal_full` | string | 期刊全称 |
| `list[].keywords` | array | 关键词 |
| `list[].publish_date` | string | 发表时间 |
| `list[].last_if` | string | 最新影响因子 |

---

## MedSearch

**Path:** `POST /tqsk/general/v1/med/search`

**Description:** 文摘信息-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `title` | string | no | 标题 |
| `keywords` | string | no | 关键词 |
| `abstract` | string | no | 摘要 |
| `doi` | string | no | doi |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].tqid` | string | tqid |
| `list[].abstract` | string | 摘要 |
| `list[].title` | string | 篇名 |
| `list[].author_name` | array | 作者信息 |
| `list[].doi` | string | doi |
| `list[].journal_full` | string | 期刊全称 |
| `list[].keywords` | array | 关键词 |
| `list[].publish_date` | string | 发表时间 |
| `list[].last_if` | string | 最新影响因子 |

---

## PediaSearch

**Path:** `POST /tqsk/general/v1/chem/search`

**Description:** 物质检索-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `pedia_search[].logic_symbol` | Logic Symbol | no | 逻辑运算符 |
| `pedia_search[].filter.field` | Search Field | no | 检索字段 |
| `pedia_search[].filter.value.str` | string | no | 值检索 |
| `pedia_search[].filter.value.multi_str` | array | no | 多值检索 |
| `extend` | boolean | no | 扩展检索 |
| `pedia_name` | string | no | 化合物名称。例：甲苯 |
| `molecular_formula` | string | no | 化学式。例：C7H8 |
| `cas` | string | no | CAS号。例：108-88-3 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].pedia_id` | string | 物质ID |
| `list[].title` | string | 标题 |
| `list[].inchikey` | string | InChiKey |
| `list[].molecular_formula` | string | 分子结构式 |
| `list[].molecular_weight` | number | 分子量 |
| `list[].cas` | array | CAS号 |
| `list[].name_cn` | array | 中文名称 |
| `list[].name_en` | array | 英文名称 |

---

## PropDetail

**Path:** `POST /tqsk/general/v1/chem/prop`

**Description:** 物化性质及计算性质-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `pedia_id` | string | no | 物质id，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `pedia_id` | string | 物质id |
| `comp_prop[].show_name` | string | 性质描述 |
| `comp_prop[].value` | number | 值 |
| `comp_prop[].unit` | string | 单位 |
| `phy_prop[].show_name` | string | 性质描述 |
| `phy_prop[].value` | string | 物化性质值 |

---

## SafetySdsDetail

**Path:** `POST /tqsk/general/v1/chem/safety_sds`

**Description:** 物质安全信息及SDS-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `pedia_id` | string | no | 物质id，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `pedia_id` | string | 物质id |
| `safety_info.danger_goods_mark` | array | 危险品标志 |
| `safety_info.safety_note` | array | 安全说明 |
| `safety_info.danger_code` | array | 危险类别码 |
| `safety_info.danger_trans_num` | array | 危险品运输编号 |
| `safety_info.danger_describe` | array | 危险性说明 |
| `safety_info.danger_protect_note` | array | 危险性防范说明 |
| `safety_info.danger_mark` | array | 危险性标志 |
| `safety_info.wgk_germany` | array | WGK Germany |
| `safety_info.rtecs` | array | RTECS号 |
| `safety_info.customs_code` | array | 海关编码 |
| `safety_info.pack_level` | array | 包装等级 |
| `safety_info.hazard_class` | array | 危险类别 |
| `sds[].manufacture` | string | 提供商 |
| `sds[].pdf` | string | 文档地址 |
| `sds[].revision_date` | string | 修订日期 |

---

## SpectraDetail

**Path:** `POST /tqsk/general/v1/spectra/detail`

**Description:** 谱图信息-详情

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `inchikey` | string | no | InChiKey，必填。例：YXFVVABEGXRONW-UHFFFAOYSA-N |
| `type` | Spectra Peak Type Enum | no | 谱图类型 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].pedia_id` | string | 物质id |
| `list[].show_type` | string | 显示名称 |
| `list[].inchikey` | string | inChiKey |
| `list[].inchi` | string | inChi |
| `list[].spectra_img` | string | 谱图渲染图 |
| `list[].peak_data_text` | string | 峰位数据渲染数据 |
| `list[].condition.test_frequency` | string | 测试频率 |
| `list[].condition.sample_amount` | string | 样品用量 |
| `list[].condition.solvent` | array | 溶剂 |
| `list[].condition.solvent_amount` | string | 溶剂用量 |
| `list[].source` | string | 数据来源 |

---

## SpectraPredict

**Path:** `POST /tqsk/general/v1/spectra/predict`

**Description:** 谱图预测-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `type` | Spectra Peak Type Enum | no | 谱图类型 |
| `solvent` | Solvent Enum | no | 溶剂 |
| `mol` | string | no | mol码，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `img` | string | 谱图渲染图 |
| `data[].no` | number |  |
| `data[].delta` | number |  |

---

## SpectraSearch

**Path:** `POST /tqsk/general/v1/spectra/search`

**Description:** 谱图检索-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `peak_data` | string | no | 谱图数据，必填。例：172.77,133.83,130 |
| `type` | Spectra Peak Type Enum | no | - peak_type_cnmr: C NMR |
| `solvent` | Solvent Enum | no | 溶剂 |
| `tolerance` | Spectra Peak Tolerance Enum | no | - peak_tolerance_2: ±2.0
 - peak_tolerance_1: ±1.0
 - peak_tolerance_05: ±0.5 |
| `peak_match` | Spectra Peak Match Enum | no | - peak_match_equal: 精确
 - peak_match_greater: 模糊 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].pedia_id` | string | 物质ID |
| `list[].title` | string | 标题 |
| `list[].inchikey` | string | InChiKey |
| `list[].molecular_formula` | string | 分子结构式 |
| `list[].molecular_weight` | number | 分子量 |
| `list[].cas` | array | CAS号 |
| `list[].name_cn` | array | 中文名称 |
| `list[].name_en` | array | 英文名称 |

---

## StructureRecognition

**Path:** `POST /tqsk/general/v1/ocr/structure`

**Description:** 结构式识图-接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `image_url` | string | no | 图片地址，必填 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `mol` | string | mol码 |
| `smiles` | string | smiles码 |
| `inchikey` | string | InChiKey |

---

## SynthSearch

**Path:** `POST /tqsk/general/v1/synth/search`

**Description:** 反应检索-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `page` | integer | no | 分页 |
| `pedia_search.pedia_id` | string | no | 物质ID |
| `pedia_search.smiles` | string | no | 物质smiles码 |
| `synth_search.rxn` | string | no | 反应smiles码 |
| `smiles` | string | no | 物质或反应smiles。例：Cc1ccccc1 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `total` | integer | 总数 |
| `list[].rxn` | string | 反应smiles |
| `list[].detail[].doi` | string | doi |
| `list[].detail[].title` | string | 标题 |
| `list[].detail[].condition` | array | 反应描述（只在没有优化描述时存在） |

---

