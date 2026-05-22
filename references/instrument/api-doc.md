# instrument — API Reference

1 endpoints.

---

## ChinaListedList

**Path:** `POST /instrument/general/v1/china_listed/list`

**Description:** 中国上市医疗器械库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.product_name` | string | no | 产品名称 |
| `search.manufacturer_re` | string | no | 注册/备案人名称 |
| `search.registration_number_remark` | string | no | 产品备案/注册证号 |
| `search.scope_and_use` | string | no | 适用范围/预期用途 |
| `search.structure_and_components` | string | no | 结构及组成/主要组成成分 |
| `search.approval_date.max` | string | no |  |
| `search.approval_date.min` | string | no |  |
| `search.valid_until.max` | string | no |  |
| `search.valid_until.min` | string | no |  |
| `search.registration_category` | string | no | 注册类型，可取值：注册 |
| `search.category` | string | no | 管理类别，可取值：Ⅱ、Ⅲ |
| `search.classify` | string | no | 产品类型，可取值：一次性使用医疗器械产品、一般医疗器械、体外诊断试剂 |
| `search.product_state` | string | no | 器械状态，可取值：已注销、已过期、有效 |
| `search.type` | string | no | 国产/进口，可取值：国产、进口 |
| `search.whether_yibao` | string | no | 是否纳入医保，可取值：是、否 |
| `search.certificate_state` | string | no | 注册状态，可取值：延续注册、重新注册、首次注册 |
| `search.prioritize_innovation` | string | no | 创新产品/优先审批，可取值：创新产品 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].keyid` | string | keyid |
| `list[].product_name` | string | 产品名称 |
| `list[].registration_number` | string | 产品备案/注册证号 |
| `list[].registration_number_remark` | string | 产品备案/注册证号（备注/合并字段） |
| `list[].category_year` | string | 分类目录-年份 |
| `list[].classification` | string | 一级分类 |
| `list[].first_category` | string | 二级分类 |
| `list[].secondary_category` | string | 三级分类 |
| `list[].category` | string | 管理类别（如 II、III） |
| `list[].manufacturer_re` | string | 注册/备案人名称 |
| `list[].registrant_domicile` | string | 注册人住所 |
| `list[].production_address` | string | 生产地址 |
| `list[].product_storage_conditions_and_expiry_date` | string | 产品储存条件及有效期 |
| `list[].scope_and_use` | string | 适用范围/预期用途 |
| `list[].agent_name` | string | 代理人 |
| `list[].change` | string | 变更情况 |
| `list[].model_specification` | string | 型号规格 |
| `list[].structure_and_components` | string | 结构及组成/主要组成成分 |
| `list[].approval_department` | string | 审批部门 |
| `list[].approval_date` | string | 批准日期/备案日期 |
| `list[].effective_date` | string | 生效日期 |
| `list[].valid_until` | string | 有效期至 |
| `list[].type` | string | 国产/进口 |
| `list[].whether_yibao` | string | 是否纳入医保 |
| `list[].remark` | string | 备注 |
| `list[].registration_category` | string | 注册类型 |
| `list[].province` | string | 省份 |
| `list[].city` | string | 城市 |
| `list[].region` | string | 区县/地区 |
| `list[].classify` | string | 产品类型 |
| `list[].product_state` | string | 器械状态 |
| `list[].certificate_state` | string | 注册状态 |
| `list[].prioritize_innovation` | string | 创新产品/优先审批 |
| `total` | integer |  |

---

