# pharma — API Reference

71 endpoints.

---

## CenterPurchaseList

**Path:** `POST /pharma/general/v1/center_purchase/list`

**Description:** 药品集中采购-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.specification` | string | no | 规格 |
| `search.company` | string | no | 中选企业 |
| `search.approval_number` | string | no | 批准文号 |
| `search.date.max` | string | no |  |
| `search.date.min` | string | no |  |
| `search.execution_date.max` | string | no |  |
| `search.execution_date.min` | string | no |  |
| `search.level` | string | no | 国家集采。可选值：4+7试点、4+7扩围、第二批集采、第三批集采、第四批集采、第五批集采、第六批集采（胰岛素专项）、第七批集采、第八批集采、第九批集采、第十批集采 |
| `search.level_1` | string | no | 地方集采。可选值：京津冀“3+N”联盟、省际联盟中药配方颗粒带量采购、甘肃省带量采购（中药配方颗粒专项）、广东联盟、江苏省带量采购、西藏自治区“三进”集采、云南省带量采购、江西省带量采购、福建省带量采购、京津冀联盟、广东省带量采购、甘肃省带量采购、河南十七省(区、兵团)联盟、全国中成药采购联盟、河南十三省(区、兵团)联盟、四川联盟、渝川蒙鄂滇藏陕宁联盟、浙江省带量采购、河北省带量采购、苏陕联盟、苏桂陕联盟、安徽省带量采购、豫晋蒙鄂湘桂琼渝贵青宁新兵团十三省(区、市、兵团)联盟、渝鄂桂琼黔滇青宁新新疆兵团联盟、北京市中成药带量采购、陕西九省联盟、河南十九省(区、兵团)联盟、长三角沪浙皖联盟、上海十五省(区、市)联盟、京津冀赣联盟、山东省带量采购、湖南省带量采购、河南省带量采购、山东省带量采购（中成药专项）、新疆二十六省联盟、豫晋蒙赣粤桂渝贵滇陕青宁新兵团十四省(区、市、兵团)联盟、豫晋蒙鄂湘桂琼渝贵青宁新兵团十四省(区、市、兵团)联盟、易短缺和急抢救药联盟、湖北省带量采购、鲁晋联盟、渝黔联盟、上海市中成药带量采购、中成药省际联盟、河南十六省(区、兵团)联盟、青海牵头七省(区、兵团)联盟、新疆2+N联盟、新疆南部联盟、陕西十一省联盟、三明联盟、八省二区联盟、渝豫桂琼滇青宁新新疆兵团联盟、26省(区、市)联盟、渝鄂琼滇青宁新新疆兵团联盟、江西十六省(区、市)联盟、渝黔滇湘桂联盟、重庆5省市联盟、十四省联盟(进口抗癌药)、江西干扰素省际联盟、安徽省中成药带量采购、河南省豫东片区联盟、甘陕联盟、黑龙江省带量采购、株洲湘潭岳阳常德邵阳首批带量采购、陕西省带量采购、新疆中部联盟、山西省带量采购、河南中部片区联盟、六省二区联盟、赣粤豫鄂四省联盟、酒泉市市际联盟、平凉市市际联盟、兰州市市际联盟、四川省带量采购、头孢氨苄药品联盟 |
| `search.region` | string | no | 供应地区。可选值：安徽、北京、重庆、福建、广西、贵州、甘肃、广东、海南、湖南、河北、河南、黑龙江、湖北、江西、吉林、江苏、辽宁、宁夏、内蒙古、青海、四川、陕西、上海、山西、山东、天津、西藏、新疆（含兵团）、云南、浙江 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name` | string | 药品名称 |
| `list[].medical_insurance_type` | array | "医保分类"标签 |
| `list[].manufacturer` | string | 中选企业 |
| `list[].manufacturer_province` | array | 企业所属地区 |
| `list[].dosage_form` | string | 剂型 |
| `list[].specification` | string | 规格包装 |
| `list[].number` | string | 规格包装数量 |
| `list[].pre_price` | number | 中选前价格(元) |
| `list[].price` | number | 中选价格（元） |
| `list[].price_decline` | number | 中选前后降幅 |
| `list[].minimum_price` | number | 单位制剂价格（元） |
| `list[].conversion_coefficient` | string | 转换系数 |
| `list[].approval_number` | array | 批准文号 |
| `list[].region` | array | 供应地区 |
| `list[].source` | string | 官方文件 |
| `list[].link` | string | 官方文件链接 |
| `list[].level` | string | 集采批次 |
| `list[].level_type` | string | 集采类型 |
| `list[].purchasing_cycle` | string | 采购周期 |
| `list[].cgnumber` | number | 采购量（万片/万支） |
| `list[].converted_cgnumber` | string | 折算采购量（万片/万支) |
| `list[].company_count` | string | 中选企业数 |
| `list[].date` | string | 公布日期 |
| `list[].execution_date` | string | 执行日期 |
| `list[].expiry_date` | string | 截止日期 |
| `list[].status` | string | 执行状态 |
| `list[].type_shaixuan` | array | 药物类型 |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `total` | integer |  |

---

## ClinicalAmericaList

**Path:** `POST /pharma/general/v1/en_clinical_usa/list`

**Description:** 美国临床试验-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.registration_number` | string | no | 试验登记号 |
| `search.phase_json` | string | no | 试验阶段 |
| `search.recruitment_status_json` | string | no | 招募状态 |
| `search.country_territory_json` | string | no | string	开展国家/地区 |
| `search.publications_results` | string | no | 是否有临床试验结果 |
| `search.endpoint_types_json` | string | no | 终点类型 |
| `search.study_type_json` | string | no | 试验类型 |
| `search.primary_purpose_json` | string | no | 试验目标 |
| `search.drug_name_json` | string | no | 药品名称 |
| `search.indication_json` | string | no | 适应症 |
| `search.target_json` | string | no | 靶点 |
| `search.intervention_info` | string | no | 干预信息 |
| `search.manufacturer_json` | string | no | 申办单位 |
| `search.company_json` | string | no | 合作方 |
| `search.start_date.max` | string | no |  |
| `search.start_date.min` | string | no |  |
| `search.end_date.max` | string | no |  |
| `search.end_date.min` | string | no |  |
| `search.primary_completion_date.max` | string | no |  |
| `search.primary_completion_date.min` | string | no |  |
| `search.first_enrollment_date.max` | string | no |  |
| `search.first_enrollment_date.min` | string | no |  |
| `search.first_posted.max` | string | no |  |
| `search.first_posted.min` | string | no |  |
| `search.last_change_date.max` | string | no |  |
| `search.last_change_date.min` | string | no |  |
| `page` | integer | no | 页码 |
| `page_size` | integer | no | 每页大小 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].registration_number` | string | 试验登记号 |
| `list[].registration_url` | string | 官网链接 |
| `list[].first_posted` | string | 登记日期 |
| `list[].registration_number_1_json` | array | 其他试验登记号 |
| `list[].title` | string | 试验标题 |
| `list[].scientific_title` | string | 正式的科学名称 |
| `list[].country_territory_json[].cn` | string |  |
| `list[].country_territory_json[].en` | string |  |
| `list[].manufacturer_json[].cn` | string |  |
| `list[].manufacturer_json[].en` | string |  |
| `list[].company_json[].cn` | string |  |
| `list[].company_json[].en` | string |  |
| `list[].linked_study_record` | array | 试验关联记录 |
| `list[].start_date` | string | 开始日期 |
| `list[].primary_completion_date` | string | 主要终点完成日期 |
| `list[].end_date` | string | 结束日期 |
| `list[].result_date` | string | 结果发布日期 |
| `list[].last_change_date` | string | 最近更新日期 |
| `list[].recruitment_status_json.cn` | string |  |
| `list[].recruitment_status_json.en` | string |  |
| `list[].registration_authority` | string | 注册机构 |
| `list[].drug_name_json[].cn` | string |  |
| `list[].drug_name_json[].en` | string |  |
| `list[].drug_category` | array | 药物类别 |
| `list[].intervention_info[].name` | string |  |
| `list[].intervention_info[].type` | string |  |
| `list[].target_json[].name_full` | string |  |
| `list[].target_json[].name_short` | string |  |
| `list[].target_json[].name_cn` | string |  |
| `list[].target_json[].alias` | array |  |
| `list[].target_json[].url` | string |  |
| `list[].target_role[].cn` | string |  |
| `list[].target_role[].en` | string |  |
| `list[].technologies_json[].cn` | string |  |
| `list[].technologies_json[].en` | string |  |
| `list[].indication_json[].cn` | string |  |
| `list[].indication_json[].en` | string |  |
| `list[].active_indications_json[].cn` | string |  |
| `list[].active_indications_json[].en` | string |  |
| `list[].indication_area` | array | 治疗领域 |
| `list[].phase_json[].cn` | string |  |
| `list[].phase_json[].en` | string |  |
| `list[].study_type_json[].cn` | string |  |
| `list[].study_type_json[].en` | string |  |
| `list[].primary_purpose_json[].cn` | string |  |
| `list[].primary_purpose_json[].en` | string |  |
| `list[].category_json[].cn` | string |  |
| `list[].category_json[].en` | string |  |
| `list[].allocation` | string | 干预分组方式 |
| `list[].intervention_model` | string | 干预模型 |
| `list[].masking` | string | 盲法 |
| `list[].blinded` | string | 设盲对象 |
| `list[].observation_model` | string | 观察模型 |
| `list[].observational_perspective` | string | 观察时间点 |
| `list[].patient_registry` | string | 患者登记研究 |
| `list[].follow_up_time` | string | 患者登记随访持续时间 |
| `list[].biospecimen_retention` | string | 生物标本存放形式 |
| `list[].biospecimen_description` | string | 生物标本说明 |
| `list[].biomarker` | string | 生物标记物 |
| `list[].biomarker_type_1` | string | 生物标记物类型 |
| `list[].biomarker_role` | string | 生物标记物作用 |
| `list[].endpoint_types_json[].cn` | string |  |
| `list[].endpoint_types_json[].en` | string |  |
| `list[].primary_endpoints[].endpoint` | string |  |
| `list[].primary_endpoints[].timepoint` | string |  |
| `list[].primary_endpoints[].description` | string |  |
| `list[].secondary_endpoints[].endpoint` | string |  |
| `list[].secondary_endpoints[].timepoint` | string |  |
| `list[].secondary_endpoints[].description` | string |  |
| `list[].other_endpoints[].endpoint` | string |  |
| `list[].other_endpoints[].timepoint` | string |  |
| `list[].other_endpoints[].description` | string |  |
| `list[].reference_json[].text` | string |  |
| `list[].reference_json[].url` | string |  |
| `list[].first_enrollment_date` | string | 首例受试者入组日期 |
| `list[].anticipated_enrollment_count` | string | 目标入组人数 |
| `list[].actual_enrollment_count` | string | 实际入组人数 |
| `list[].age_range` | string | 年龄范围 |
| `list[].gender` | string | 性别 |
| `list[].accepts_healthy_volunteers` | string | 是否接受健康受试者 |
| `list[].enrollment_period` | string | 入组期限 |
| `list[].enrollment_rate` | string | 入组率 |
| `list[].inclusion_and_exclusion_criteria` | string | 入选/排除标准 |
| `list[].contact_json[].name` | string |  |
| `list[].contact_json[].type` | string |  |
| `list[].contact_json[].contact_information` | string |  |
| `list[].site_json` | array | 试验点信息 |
| `list[].publications_results` | string | 是否有临床试验结果 |
| `list[].result_json[].text` | string |  |
| `list[].result_json[].url` | string |  |
| `list[].documents_json[].text` | string |  |
| `list[].documents_json[].url` | string |  |
| `total` | integer |  |

---

## CnClinicalTrialBaseInfo

**Path:** `POST /pharma/general/v1/cn_clinical_trial/baseinfo`

**Description:** 中国临床试验库-基础信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `registration_number` | string | 登记号 |
| `status` | string | 试验状态 |
| `enlist_status` | string | 招募状态 |
| `trial_phase_original` | string | 试验分期 |
| `type` | string | 药品类型 |
| `type_shaixuan` | array | 药物类型 |
| `bool_combination` | string | 联合用药 |
| `innovation_type` | string | 创新类型 |
| `link` | string | 官网全文链接 |
| `registration_number_1` | array | 相关登记号 |
| `drug_name_cn` | string | 药品名称 |
| `drug_name_standard` | string | 规范名称 |
| `molecule` | string | 曾用名 |
| `indication` | string | 适应症 |
| `therapy_area_cn` | array | 治疗领域 |
| `target` | array | 靶点 |
| `combination` | string | 联合用药 |
| `manufacturer` | array | 申请人名称 |
| `scientific_title` | string | 试验专业题目 |
| `title` | string | 试验通俗题目 |
| `first_public_date` | string | 首次公示信息日期 |
| `version_date` | string | 版本日期 |
| `acceptances_number` | array | 临床申请受理号 |
| `scheme_number` | string | 试验方案编号 |
| `latest_version` | string | 方案最新版本 |

---

## CnClinicalTrialEthicsCommitteeInfo

**Path:** `POST /pharma/general/v1/cn_clinical_trial/ethics_committee_info`

**Description:** 中国临床试验库-伦理委员会信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].name` | string | 伦理委员会名称 |
| `list[].conclusion` | string | 审查结论 |
| `list[].approval_date` | string | 批准日期/备案日期 |
| `total` | integer |  |

---

## CnClinicalTrialJoinInstitution

**Path:** `POST /pharma/general/v1/cn_clinical_trial/join_institution`

**Description:** 中国临床试验库-参与临床机构信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].institution_name` | string | 机构名称 |
| `list[].main_researcher` | string | 主要研究人 |
| `list[].country` | string | 国家 |
| `list[].province` | string | 省（州） |
| `list[].city` | string | 城市 |
| `total` | integer |  |

---

## CnClinicalTrialList

**Path:** `POST /pharma/general/v1/cn_clinical_trial/list`

**Description:** 中国临床试验库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.indication` | string | no | 适应症 |
| `search.sponsor` | string | no | 申办单位 |
| `search.clinical_institution` | string | no | 临床机构 |
| `search.trial_phase` | string | no | 试验分期，可取值：Ⅰ期、Ⅱ期、Ⅲ期、Ⅳ期、BE试验、探索性研究/预试验、回顾性研究、基础科学研究、临床预试验、诊断试验新技术临床试验、卫生服务研究、治疗新技术临床试验、上市后药物、其它 |
| `search.design_type` | string | no | 试验设计，可取值：平行分组、交叉设计、单臂试验、析因设计 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].registration_number` | string | 登记号 |
| `list[].drug_name_cn` | string | 药品名称 |
| `list[].indication` | string | 适应症 |
| `list[].trial_phase` | string | 试验分期 |
| `list[].design_type` | string | 试验设计 |
| `list[].sponsor[].name` | string | 企业名称 |
| `list[].main_clinical_institution` | array | 主要临床机构 |
| `list[].join_clinical_institution` | array | 参与临床机构 |
| `total` | integer |  |

---

## CnClinicalTrialPrimaryInstitution

**Path:** `POST /pharma/general/v1/cn_clinical_trial/primary_institution`

**Description:** 中国临床试验库-主要临床机构信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].institution_name` | string | 研究者单位名称 |
| `list[].investigator_name` | string | 研究者姓名 |
| `list[].degree` | string | 学位 |
| `list[].title` | string | 研究者职称 |
| `list[].phone` | string | 研究者电话 |
| `list[].email` | string | 研究者邮箱 |
| `list[].postal_code` | string | 研究者邮编 |
| `list[].address` | string | 研究者邮政地址 |
| `total` | integer |  |

---

## CnClinicalTrialSponsorInfo

**Path:** `POST /pharma/general/v1/cn_clinical_trial/sponsor_info`

**Description:** 中国临床试验库-申办单位信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `contact_name` | string | 联系人姓名 |
| `sponsor_name` | string | 申请人名称 |
| `contact_phone` | string | 联系人座机 |
| `contact_mobile` | string | 联系人手机 |
| `contact_email` | string | 联系人邮箱 |
| `contact_address` | string | 联系人邮政地址 |
| `contact_postcode` | string | 联系人邮编 |

---

## CnClinicalTrialSummary

**Path:** `POST /pharma/general/v1/cn_clinical_trial/summary`

**Description:** 中国临床试验库-结果摘要

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].version` | string | 版本号 |
| `list[].version_date` | string | 版本日期 |
| `total` | integer |  |

---

## CnClinicalTrialTestInfo

**Path:** `POST /pharma/general/v1/cn_clinical_trial/test_info`

**Description:** 中国临床试验库-试验信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `objective` | string | 试验目的 |
| `trial_type_original` | string | 试验分类 |
| `trial_phase_original` | string | 试验分期 |
| `design_type` | string | 试验设计 |
| `random` | string | 随机化 |
| `blinding` | string | 盲法 |
| `trial_range` | string | 试验范围 |
| `subject_information.age` | array | 受试者年龄 |
| `subject_information.gender` | array | 受试者性别 |
| `subject_information.healthy_subjects` | array | 健康受试者 |
| `subject_information.inclusion_criteria` | array | 受试者入选标准 |
| `subject_information.exclusion_criteria` | array | 受试者排除标准 |
| `test_drug.name` | array | 试验药名称 |
| `test_drug.usage` | array | 试验药用法 |
| `control_drug.name` | array | 对照药名称 |
| `control_drug.usage` | array | 对照药用法 |
| `primary_endpoint.endpoint` | array | 主要终点指标 |
| `primary_endpoint.evaluation_time` | array | 主要终点指标评价时间 |
| `primary_endpoint.selection` | array | 主要终点指标选择 |
| `secondary_endpoint.endpoint` | array | 主要终点指标 |
| `secondary_endpoint.evaluation_time` | array | 主要终点指标评价时间 |
| `secondary_endpoint.selection` | array | 主要终点指标选择 |
| `dmc` | string | 数据安全监查委员会（DMC) |
| `insurance` | string | 为受试者购买试验伤害保险 |
| `test_status.status` | array | 试验状态（招募状态） |
| `test_status.target_enrollment` | array | 目标入组人数 |
| `test_status.current_enrollment` | array | 已入组人数 |
| `test_status.total_enrollment` | array | 实际入组总例数 |
| `test_status.first_consent_date` | array | 第一例受试者签署知情同意书日期 |
| `test_status.first_enrollment_date` | array | 第一例受试者入组日期 |
| `test_status.completion_date` | array | 试验完成日期 |

---

## CnClinicalTrialTimeline

**Path:** `POST /pharma/general/v1/cn_clinical_trial/timeline`

**Description:** 中国临床试验库-临床时间轴

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `registration_number` | string | no | 登记号(必传) *** 必须从GeneralV1_CnClinicalTrialList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].date` | string | 日期 |
| `list[].title` | string | 阶段 |
| `list[].state` | string | 状态 |
| `list[].remark` | array | 备注 |
| `total` | integer |  |

---

## CnDrugApprovalBaseInfo

**Path:** `POST /pharma/general/v1/cn_drug_approval/baseinfo`

**Description:** 中国药品批文库-基础信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `approval_number` | string | 批准文号 |
| `bool_exclusivity` | string | 是否独家 |
| `approval_type` | string | 国产或进口 |
| `marketing_status` | string | 市场状态 |
| `number_status` | string | 文号状态 |
| `drug_name` | string | 药品名称 |
| `formulation_type_single` | string | 单方/复方 |
| `drug_name_en` | string | 药品名称(英文) |
| `trade_name` | string | 商品名称 |
| `trade_name_cn` | string | 商品名称(中文) |
| `dosage_form` | string | 剂型 |
| `innovation_type` | string | 创新类型 |
| `specification` | string | 简化规格 |
| `type` | string | 药品类型 |
| `type_shaixuan` | array | 药物类型 |
| `specification_1` | string | 规格 |
| `package` | string | 包装规格(进口) |
| `target` | array | 靶点 |
| `active_ingredient_en` | array | 活性成分(英文) |
| `active_ingredient_cn` | string | 活性成分(中文) |
| `atc_shaixuan` | array | ATC分类 |
| `therapy_area_cn` | array | 治疗领域 |
| `low_price` | string | 纳入国家低价药品目录 |
| `yizhixing_tongguo` | string | 是否通过一致性评价 |
| `number_manufacturer` | string | 同品种厂家数 |
| `number_approval` | string | 同品种批文数 |
| `standard_code` | string | 药品本位码 |
| `standard_code_remark` | string | 药品本位码备注 |

---

## CnDrugApprovalEssentialDrugsStatus

**Path:** `POST /pharma/general/v1/cn_drug_approval/essential_drugs_status`

**Description:** 中国药品批文库-基药情况

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `essential_yes_no` | string | 是否2018版基药 |
| `number_essential` | string | 2018版基药序号 |
| `essential_name` | string | 2018版基药品种名称 |
| `essential_form` | string | 2018版基药剂型 |
| `varieties_289` | string | 是否289品种 |

---

## CnDrugApprovalList

**Path:** `POST /pharma/general/v1/cn_drug_approval/list`

**Description:** 中国药品批文库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.approval_number` | string | no | 批准文号，比如：国药准字Z20053943 |
| `search.drug_name` | string | no | 药品名称 |
| `search.company` | string | no | 生产企业 |
| `search.license_holder` | string | no | 上市许可持有人，比如：石家庄四药有限公司 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].approval_number` | string | 批准文号 |
| `list[].drug_name` | string | 药品名称 |
| `list[].corporation_cn` | array | 上市许可持有人 |
| `list[].corporation` | array | 持有人(英文) |
| `list[].manufacturer_cn` | array | 生产企业(中文) |
| `list[].manufacturer` | array | 生产企业(英文) |
| `list[].marketing_status` | string | 市场状态 |
| `total` | integer |  |

---

## CnDrugApprovalListingInfo

**Path:** `POST /pharma/general/v1/cn_drug_approval/listing_info`

**Description:** 中国药品批文库-上市信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `approval_number` | string | 批准文号 |
| `approval_number_1` | string | 原批准文号 |
| `remarks` | string | 注册证号备注（进口） |
| `approval_number_2` | string | 分包装批准文号（进口） |
| `approval_date` | string | 批准日期 |
| `corporation_cn` | array | 上市许可持有人（中文） |
| `corporation` | array | 上市许可持有人（英文） |
| `corporation_address_cn` | array | 上市许可持有人地址（中文） |
| `corporation_address` | array | 上市许可持有人地址（英文） |
| `company_cn` | array | 公司名称（进口）（中文） |
| `company` | array | 公司名称（进口）（英文） |
| `company_address_cn` | array | 公司地址（进口）（中文） |
| `company_address` | array | 公司地址（进口）（英文） |
| `company_country_cn` | array | 国家/地区（中文） |
| `company_country` | array | 国家/地区（英文） |
| `manufacturer_cn` | array | 生产企业（中文） |
| `manufacturer` | array | 生产企业（英文） |
| `manufacturer_address_cn` | array | 生产地址（中文） |
| `manufacturer_address` | array | 生产地址（英文） |
| `manufacturer_country_cn` | array | 厂商国家/地区（中文） |
| `manufacturer_country` | array | 厂商国家/地区（英文） |
| `end_date` | string | 有效截止日期 |
| `packaging_approval_date` | string | 分包装文号批准日期（进口） |
| `packaging_end_date` | string | 分包装文号有效期截止日（进口） |
| `packaging_enterprise` | string | 分包装企业名称（进口） |
| `packaging_address` | string | 分包装企业地址（进口） |

---

## CnDrugApprovalMedicalInsuranceStatus

**Path:** `POST /pharma/general/v1/cn_drug_approval/medical_insurance_status`

**Description:** 中国药品批文库-医保情况

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `medical_insurance_type` | array | 2024年医保分类 |
| `medical_insurance_number` | string | 2024年医保编号 |
| `medical_insurance_name` | string | 2024年医保药品名称 |
| `medical_insurance_form` | string | 2024年医保剂型 |
| `limit` | string | 2024年医保限制使用范围 |
| `medical_insurance_supplement` | string | 2024年增补情况 |

---

## CnDrugApprovalOtcStatus

**Path:** `POST /pharma/general/v1/cn_drug_approval/otc_status`

**Description:** 中国药品批文库-otc情况

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `otc_type` | string | OTC/处方药 |
| `double_span_yes_no` | string | OTC双跨 |
| `otc_specification` | string | OTC规格 |
| `composition` | string | 处方组成 |
| `otc_source` | string | OTC通知 |

---

## CnDrugApprovalResearchTimeline

**Path:** `POST /pharma/general/v1/cn_drug_approval/research_timeline`

**Description:** 中国药品批文库-文号研发历程

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].date` | string | 日期 |
| `list[].title` | string | 阶段 |
| `list[].data[].approval_number` | string | 再注册批准文号 |
| `list[].data[].record_number` | string | 备案号 |
| `list[].data[].content` | string | 备案内容 |
| `total` | integer |  |

---

## CnDrugApprovalTcmProtection

**Path:** `POST /pharma/general/v1/cn_drug_approval/tcm_protection`

**Description:** 中国药品批文库-中药保护

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `approval_number` | string | no | 批准文号(必传) *** 必须从GeneralV1_CnDrugApprovalList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `number_traditional` | string | 中药保护品种编号 |
| `traditional_yes_no` | string | 是否中药保护品种 |
| `traditional_level` | string | 中药保护级别 |
| `traditional_begin` | string | 中药保护起始时间 |
| `traditional_end` | string | 中药保护终止时间 |

---

## CnDrugEvaluationBaseInfo

**Path:** `POST /pharma/general/v1/cn_drug_evaluation/baseinfo`

**Description:** 中国药品审评库-基础信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `acceptances_number` | string | no | 受理号(必传) *** 必须从GeneralV1_CnDrugEvaluationList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `acceptances_number` | string | 受理号 |
| `drug_name` | string | 药品名称 |
| `formulation_type_single` | string | 单方/复方 |
| `review_conclusions` | string | 审评结论 |
| `conclusion_date` | string | 审评结论日期 |
| `bool_license` | string | 是否临床默示许可 |
| `bool_direct` | string | 是否直接行政审批 |
| `projects` | string | 是否重大专项品种 |
| `special_review` | string | 是否特殊审批品种 |
| `priority_review` | string | 是否纳入优先审评 |
| `breakthrough_treatment` | string | 突破性治疗品种 |
| `type` | string | 一致性评价类型 |
| `bool_first_clinical_apply` | string | 首次申报临床 |
| `bool_first_clinical_approval` | string | 首次批准临床 |
| `bool_first_list_apply` | string | 首次申请上市 |
| `bool_first_list_approval` | string | 首次批准上市 |
| `bool_first` | string | 首家申报 |
| `bool_first_pass` | string | 首家过评 |
| `bool_exclusivity_pass` | string | 独家过评 |
| `bool_first_generic` | string | 首仿品种 |
| `registration_classification_1` | string | 注册类型 |
| `application_type_2` | string | 申请类型 |
| `application_type` | string | 申报内容 |
| `drug_type` | string | 药品类型 |
| `dosage_form` | string | 剂型 |
| `type_shaixuan` | array | 药物类型 |
| `manufacturer` | array | NMPA企业名称 |
| `company` | array | CDE企业名称 |
| `atc_shaixuan` | array | ATC分类 |
| `active_ingredient_cn` | array | 活性成分 |
| `active_ingredient_en` | array | 活性成分英文名 |
| `target` | array | 靶点（简） |
| `license_clinical_date` | string | 临床默认许可日期 |
| `license_indication` | string | 临床默示许可适应症 |
| `therapy_area_cn` | array | 治疗领域 |
| `otc_type` | array | OTC/处方药 |
| `drug_jicai` | string | 国家集采品种 |
| `approval_type` | string | 国产/进口 |
| `undertake_date` | string | 承办日期 |
| `last_update_date` | string | 状态开始日期(摩熵) |
| `review_status` | string | 办理状态(摩熵) |
| `review_sub_status` | string | 办理详情(摩熵) |
| `review_marker` | array | 申报里程碑 |
| `state_start_time` | string | NMPA状态开始日期 |
| `processing_status_1` | string | NMPA办理状态 |
| `review_pass` | array | 过评情况 |
| `approval_number` | array | 批准文号 |
| `approval_date` | string | 官方批准日期 |
| `medical_insurance_type` | array | 2024年医保品种 |
| `review_province` | string | 受理局省份 |
| `target_short` | array | 靶点 |
| `company_history` | array | 历史CDE企业名称 |
| `review_sequence` | array | 任务类型 |
| `sequence_number` | string | 序列号 |
| `indication_standard` | array | 适应症（摩熵） |
| `priority_reason` | array | 优先审评纳入理由 |
| `number_review` | string | 申报企业数 |
| `number_approval` | string | 获批企业数 |

---

## CnDrugEvaluationList

**Path:** `POST /pharma/general/v1/cn_drug_evaluation/list`

**Description:** 中国药品审评库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.acceptances_number` | string | no | 受理号,比如：JXHB2500095 |
| `search.drug_name` | string | no | 药品名称 |
| `search.company` | string | no | 企业名称 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].acceptances_number` | string | 受理号 |
| `list[].drug_name` | string | 药品名称 |
| `list[].company` | array | CDE企业名称 |
| `list[].manufacturer` | array | NMPA企业名称 |
| `total` | integer |  |

---

## CnDrugEvaluationOverview

**Path:** `POST /pharma/general/v1/cn_drug_evaluation/overview`

**Description:** 中国药品审评库-审评概况

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `acceptances_number` | string | no | 受理号(必传) *** 必须从GeneralV1_CnDrugEvaluationList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `approval_number` | array | 批准文号 |
| `report_matter` | string | 申报事项 |
| `report_strength` | string | 申报规格 |
| `report_indication` | array | 受理号适应症 |
| `remarks` | string | 备注 |
| `fees` | string | 收费情况 |
| `notification_time` | string | 通知时间 |
| `notification_content` | string | 通知内容 |

---

## CnDrugEvaluationPatentInfo

**Path:** `POST /pharma/general/v1/cn_drug_evaluation/patent_info`

**Description:** 中国药品审评库-专利声明信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `acceptances_number` | string | no | 受理号(必传) *** 必须从GeneralV1_CnDrugEvaluationList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].registered_patent_number` | string | 登记的专利号 |
| `list[].registered_claim_number` | string | 登记的权利要求项编号 |
| `list[].patent_declaration_type` | string | 专利声明类型 |
| `list[].registered_note` | string | 备注 |
| `total` | integer |  |

---

## CnDrugEvaluationReferenceDrug

**Path:** `POST /pharma/general/v1/cn_drug_evaluation/reference_drug`

**Description:** 中国药品审评库-被仿制药相关信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `acceptances_number` | string | no | 受理号(必传) *** 必须从GeneralV1_CnDrugEvaluationList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `drugs` | string | 药品名称 |
| `approval_number` | string | 批准文号 |
| `corporation` | string | 持有人姓名 |

---

## CnHospitalList

**Path:** `POST /pharma/general/v1/cn_hospital/list`

**Description:** 全国医院大全库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.name` | string | no | 医院名称 |
| `search.introduction` | string | no | 医院简介 |
| `search.address` | string | no | 地址 |
| `search.name_of_dean` | string | no | 院长姓名 |
| `search.year` | string | no | 建院年份 |
| `search.departments` | string | no | 医院科室 |
| `search.equipment` | string | no | 医院设备 |
| `search.nature` | array | no | 医院性质，可取值：公立、民营、合资、外资 |
| `search.type` | array | no | 医院类型，可取值：综合医院、专科医院、中医医院、中西医结合医院、口腔医院、肿瘤医院、骨科医院、精神病医院、中医骨伤专科医院、康复医院、心血管病医院、眼科医院、妇幼保健院(所、站)、儿童医院、妇产(科)医院、传染病医院、民族医医院、胸科医院、肛肠医院、藏医医院、皮肤病医院、生殖专科医院、中心卫生院、乡镇卫生院、护理院(站)、疗养院、专科疾病防治院(所、站)、村卫生所(室)、卫生监督所(中心)、疾病预防控制中心、计划生育服务中心、急救中心(站)、其他 |
| `search.level` | array | no | 医院等级,可取值：三级甲等、三级乙等、三级丙等、二级甲等、二级乙等、二级丙等、一级甲等、一级乙等、一级丙等、三级未定、二级未定、一级未定、未定级、其他 |
| `search.province` | array | no | 省份，可取值：北京市、天津市、河北省、山西省、内蒙古自治区、辽宁省、吉林省、黑龙江省、上海市、江苏省、浙江省、安徽省、福建省、江西省、山东省、河南省、湖北省、湖南省、广东省、广西壮族自治区、海南省、重庆市、四川省、贵州省、云南省、西藏自治区、陕西省、甘肃省、青海省、宁夏回族自治区、新疆维吾尔自治区、台湾省、香港、澳门 |
| `search.city` | array | no | 地市，可取值：北京市、天津市、石家庄市、唐山市、秦皇岛市、邯郸市、邢台市、保定市、张家口市、承德市、沧州市、廊坊市、衡水市、太原市、大同市、阳泉市、长治市、晋城市、朔州市、晋中市、运城市、忻州市、临汾市、吕梁市、呼和浩特市、包头市、乌海市、赤峰市、通辽市、鄂尔多斯市、呼伦贝尔市、巴彦淖尔市、乌兰察布市、兴安盟、锡林郭勒盟、阿拉善盟、沈阳市、大连市、鞍山市、抚顺市、本溪市、丹东市、锦州市、营口市、阜新市、辽阳市、盘锦市、铁岭市、朝阳市、葫芦岛市、长春市、吉林市、四平市、辽源市、通化市、白山市、松原市、白城市、延边朝鲜族自治州、哈尔滨市、齐齐哈尔市、鸡西市、鹤岗市、双鸭山市、大庆市、伊春市、佳木斯市、七台河市、牡丹江市、黑河市、绥化市、大兴安岭地区、上海市、南京市、无锡市、徐州市、常州市、苏州市、南通市、连云港市、淮安市、盐城市、扬州市、镇江市、泰州市、宿迁市、杭州市、宁波市、温州市、嘉兴市、湖州市、绍兴市、金华市、衢州市、舟山市、台州市、丽水市、合肥市、芜湖市、蚌埠市、淮南市、马鞍山市、淮北市、铜陵市、安庆市、黄山市、滁州市、阜阳市、宿州市、六安市、亳州市、池州市、宣城市、福州市、厦门市、莆田市、三明市、泉州市、漳州市、南平市、龙岩市、宁德市、南昌市、景德镇市、萍乡市、九江市、新余市、鹰潭市、赣州市、吉安市、宜春市、抚州市、上饶市、济南市、青岛市、淄博市、枣庄市、东营市、烟台市、潍坊市、济宁市、泰安市、威海市、日照市、临沂市、德州市、聊城市、滨州市、菏泽市、郑州市、开封市、洛阳市、平顶山市、安阳市、鹤壁市、新乡市、焦作市、濮阳市、许昌市、漯河市、三门峡市、南阳市、商丘市、信阳市、周口市、驻马店市、济源市、武汉市、黄石市、十堰市、宜昌市、襄阳市、鄂州市、荆门市、孝感市、荆州市、黄冈市、咸宁市、随州市、恩施土家族苗族自治州、仙桃市、潜江市、天门市、神农架林区、长沙市、株洲市、湘潭市、衡阳市、邵阳市、岳阳市、常德市、张家界市、益阳市、郴州市、永州市、怀化市、娄底市、湘西土家族苗族自治州、广州市、韶关市、深圳市、珠海市、汕头市、佛山市、江门市、湛江市、茂名市、肇庆市、惠州市、梅州市、汕尾市、河源市、阳江市、清远市、东莞市、中山市、潮州市、揭阳市、云浮市、南宁市、柳州市、桂林市、梧州市、北海市、防城港市、钦州市、贵港市、玉林市、百色市、贺州市、河池市、来宾市、崇左市、海口市、三亚市、三沙市、儋州市、五指山市、琼海市、文昌市、万宁市、东方市、定安县、屯昌县、澄迈县、临高县、白沙黎族自治县、昌江黎族自治县、乐东黎族自治县、陵水黎族自治县、保亭黎族苗族自治县、琼中黎族苗族自治县、重庆市、成都市、自贡市、攀枝花市、泸州市、德阳市、绵阳市、广元市、遂宁市、内江市、乐山市、南充市、眉山市、宜宾市、广安市、达州市、雅安市、巴中市、资阳市、阿坝藏族羌族自治州、甘孜藏族自治州、凉山彝族自治州、贵阳市、六盘水市、遵义市、安顺市、毕节市、铜仁市、黔西南布依族苗族自治州、黔东南苗族侗族自治州、黔南布依族苗族自治州、昆明市、曲靖市、玉溪市、保山市、昭通市、丽江市、普洱市、临沧市、楚雄彝族自治州、红河哈尼族彝族自治州、文山壮族苗族自治州、西双版纳傣族自治州、大理白族自治州、德宏傣族景颇族自治州、怒江傈僳族自治州、迪庆藏族自治州、拉萨市、日喀则市、昌都市、林芝市、山南市、那曲市、阿里地区、西安市、铜川市、宝鸡市、咸阳市、渭南市、延安市、汉中市、榆林市、安康市、商洛市、兰州市、嘉峪关市、金昌市、白银市、天水市、武威市、张掖市、平凉市、酒泉市、庆阳市、定西市、陇南市、临夏回族自治州、甘南藏族自治州、西宁市、海东市、海北藏族自治州、黄南藏族自治州、海南藏族自治州、果洛藏族自治州、玉树藏族自治州、海西蒙古族藏族自治州、银川市、石嘴山市、吴忠市、固原市、中卫市、乌鲁木齐市、克拉玛依市、吐鲁番市、哈密市、昌吉回族自治州、博尔塔拉蒙古自治州、巴音郭楞蒙古自治州、阿克苏地区、克孜勒苏柯尔克孜自治州、喀什地区、和田地区、伊犁哈萨克自治州、塔城地区、阿勒泰地区、石河子市、阿拉尔市、图木舒克市、五家渠市、北屯市、铁门关市、双河市、可克达拉市、昆玉市、胡杨河市、新星市、香港、澳门 |
| `search.yibao` | string | no | 是否医保定点，可取值：是、否 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].name` | string | 医院名称 |
| `list[].name_1` | string | 医院别称 |
| `list[].nature` | string | 医院性质 |
| `list[].type` | string | 医院类型 |
| `list[].level` | string | 医院等级 |
| `list[].province` | string | 省份 |
| `list[].city` | string | 地市 |
| `list[].address` | string | 地址 |
| `list[].yibao` | string | 是否医保定点 |
| `list[].code` | string | 医保定点机构编码 |
| `total` | integer |  |

---

## CnMarketDrugPatentList

**Path:** `POST /pharma/general/v1/cn_market_drug_patent/list`

**Description:** 中国上市药品专利-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.approval_number` | string | no | 批准文号 |
| `search.specification` | string | no | 规格 |
| `search.dosage_form` | string | no | 剂型 |
| `search.public_date.max` | string | no |  |
| `search.public_date.min` | string | no |  |
| `search.company` | string | no | 上市许可持有人 |
| `search.application_number` | string | no | 专利号 |
| `search.name` | string | no | 专利名称 |
| `search.drug_type` | string | no | 药品类型 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].approval_number` | string | 批准文号 |
| `list[].registration_type` | string | 登记表类型 |
| `list[].registration_status` | string | 登记状态 |
| `list[].public_date` | string | 公开日期 |
| `list[].created_date` | string | 创建日期 |
| `list[].drug_name` | string | 药品名称 |
| `list[].dosage_form` | string | 剂型 |
| `list[].drug_type` | string | 药品类型 |
| `list[].specification` | string | 规格 |
| `list[].company` | string | 上市许可持有人 |
| `list[].bidder_contact` | string | 境内联系人 |
| `list[].contact_tel` | string | 境内联系电话 |
| `list[].e_mail` | string | 电子邮箱 |
| `list[].postal_address` | string | 境内通讯地址 |
| `list[].public_details[].application_number` | string | 相关专利号 |
| `list[].public_details[].name` | string | 专利名称 |
| `list[].public_details[].inventor` | string | 专利权人 |
| `list[].public_details[].assignee` | string | 专利被许可人 |
| `list[].public_details[].approval_date` | string | 专利授权日期 |
| `list[].public_details[].relation_licence` | string | 上市许可持有人与专利权人的关系 |
| `total` | integer |  |

---

## DrugBiddingList

**Path:** `POST /pharma/general/v1/drug_bidding/list`

**Description:** 药品招投标-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.specification` | string | no | 规格 |
| `search.manufacturer` | string | no | 生产企业/MAH |
| `search.company` | string | no | 企业名称 |
| `search.approval_number` | string | no | 批准文号 |
| `search.begin_time.max` | string | no |  |
| `search.begin_time.min` | string | no |  |
| `search.province` | string | no | 省份 |
| `search.price_character` | string | no | 价格属性 |
| `search.drug_type_guifan` | string | no | 药品类型 |
| `page` | integer | no | 页码 |
| `page_size` | integer | no | 每页大小 |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].id` | string |  |
| `list[].keyid` | string | 数据唯一标识 |
| `list[].drug_name` | string | 药品名称 |
| `list[].drug_name_standard` | string | 规范名称 |
| `list[].approval_number` | string | 批准文号 |
| `list[].dosage_form_1` | string | // 医保代码
   string review_level = 6;
剂型 |
| `list[].specification` | string | 规格 |
| `list[].conversion_coefficient` | string | 转化系数 |
| `list[].minimum_price` | string | 最小制剂单位价格（元） |
| `list[].price` | string | 价格 |
| `list[].price_character` | string | // 最新中标价(元)
   string price_new = 12;
价格属性 |
| `list[].company_1` | string | 企业名称（MAH优先） |
| `list[].company` | string | 投标企业 |
| `list[].province` | string | 省份 |
| `list[].date` | string | 公布时间 |
| `list[].source` | string | 公布文件 |
| `list[].link` | string | 文件链接 |
| `list[].jicai_tag` | array | 药品集中采购(标签) |
| `list[].jicai_pinzhong` | array | // 药品集中采购
   repeated string jicai_pici = 21;
品种集采类型 |
| `list[].approval_type` | string | 国产或进口 |
| `list[].medical_insurance_type` | array | 2024年医保分类 |
| `list[].essential_yes_no` | string | 2018版基药 |
| `list[].yizhixing_tg[].approval_number_piwen` | string |  |
| `list[].yizhixing_tg[].yizhixing_tongguo` | string |  |
| `list[].otc_type` | string | OTC/处方药 |
| `list[].bool_exclusivity` | string | 是否独家 |
| `list[].formulation_type` | string | 单方/复方 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `list[].type_shaixuan` | array | // 红黄标
   string red_yellow = 31;
药物类型 |
| `total` | string |  |

---

## DrugInstructionBarApprovalInsuranceUnion

**Path:** `POST /pharma/general/v1/drug_instruction_bar_approval_insurance_union/list`

**Description:** 中国上市药品编码-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.approval_number` | array | no | 批文号 |
| `search.company` | string | no | 公司名称 |
| `search.drug_name` | string | no | 药品名称 |
| `search.trade_code` | string | no | 商品条码 |
| `search.drug_code` | string | no | 医保分类代码 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].approval.approval_number` | string | 批准文号 |
| `list[].approval.drug_name` | string | 药品名称 |
| `list[].approval.corporation_cn` | array | 上市许可持有人 |
| `list[].approval.corporation` | array | 持有人(英文) |
| `list[].approval.manufacturer_cn` | array | 生产企业(中文) |
| `list[].approval.manufacturer` | array | 生产企业(英文) |
| `list[].approval.marketing_status` | string | 市场状态 |
| `list[].instruction[].drug_name` | string | 药品名称 |
| `list[].instruction[].trade_name` | array | 商品名 |
| `list[].instruction[].dosage_form` | string | 剂型 |
| `list[].instruction[].specifications` | string | 规格 |
| `list[].instruction[].indication` | string | 适应症 |
| `list[].instruction[].side_effects` | string | 不良反应 |
| `list[].instruction[].usage` | string | 用法用量 |
| `list[].instruction[].taboo` | string | 禁忌 |
| `list[].instruction[].manufacturer` | array | 生产厂家 |
| `list[].instruction[].manufacturer_1` | array | 上市许可持有人 |
| `list[].instruction[].approval_number` | array | 批准文号 |
| `list[].instruction[].last_date` | string | 最新日期 |
| `list[].instruction[].revise_date` | string | 修订日期 |
| `list[].trade_bar_code[].bar_code` | string | 条码图片 |
| `list[].trade_bar_code[].package_pic` | array | 药品图片 |
| `list[].trade_bar_code[].marketing_date` | string | 上市日期 |
| `list[].trade_bar_code[].content` | string | 净含量 |
| `list[].trade_bar_code[].specification` | string | 规格 |
| `list[].trade_bar_code[].class` | string | 产品分类 |
| `list[].trade_bar_code[].status` | string | 条码状态 |
| `list[].trade_bar_code[].trade` | string | 品牌名称 |
| `list[].trade_bar_code[].drug_name` | string | 药品名称 |
| `list[].trade_bar_code[].company` | string | 企业名称 |
| `list[].trade_bar_code[].approval_number` | array | 批准文号 |
| `list[].trade_bar_code[].trade_code` | string | 商品条码（69码） |
| `list[].medical_insurance_number[].drug_code` | string | 药品代码 |
| `list[].medical_insurance_number[].drug_name` | string | 注册名称 |
| `list[].medical_insurance_number[].drug_name_1` | string | 药品名称 |
| `list[].medical_insurance_number[].drug_classification` | string | 药品分类（功能） |
| `list[].medical_insurance_number[].native_code` | string | 药品本位码 |
| `list[].medical_insurance_number[].manufacturer` | string | 药品企业 |
| `list[].medical_insurance_number[].trade_name` | string | 商品名 |
| `list[].medical_insurance_number[].registered_dosage_form` | string | 注册剂型 |
| `list[].medical_insurance_number[].dosage_form_standard` | string | 剂型（标准） |
| `list[].medical_insurance_number[].registration_specifications` | string | 注册规格 |
| `list[].medical_insurance_number[].specifications` | string | 规格（标准） |
| `list[].medical_insurance_number[].registration_specifications_1` | string | 包装材质 |
| `list[].medical_insurance_number[].minimum_package_quantity` | string | 最小包装数量 |
| `list[].medical_insurance_number[].minimum_preparation_unit` | string | 最小制剂单位 |
| `list[].medical_insurance_number[].minimum_packing_unit` | string | 最小包装单位 |
| `list[].medical_insurance_number[].approval_number` | string | 批准文号 |
| `list[].medical_insurance_number[].approval_number_old` | string | 批准文号（原） |
| `list[].medical_insurance_number[].type` | string | 医保类型 |
| `list[].medical_insurance_number[].dosage_form` | string | 剂型 |
| `list[].medical_insurance_number[].number` | string | 编号 |
| `list[].medical_insurance_number[].note` | string | 备注 |
| `total` | integer |  |

---

## DrugInstructionList

**Path:** `POST /pharma/general/v1/drug_instruction/list`

**Description:** 药品说明书-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.approval_number` | string | no | 批准文号 |
| `search.company` | string | no | 生产企业 |
| `search.drug_name` | string | no | 药品名称 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name` | string | 药品名称 |
| `list[].trade_name` | array | 商品名 |
| `list[].dosage_form` | string | 剂型 |
| `list[].specifications` | string | 规格 |
| `list[].indication` | string | 适应症 |
| `list[].side_effects` | string | 不良反应 |
| `list[].usage` | string | 用法用量 |
| `list[].taboo` | string | 禁忌 |
| `list[].manufacturer` | array | 生产厂家 |
| `list[].manufacturer_1` | array | 上市许可持有人 |
| `list[].approval_number` | array | 批准文号 |
| `list[].last_date` | string | 最新日期 |
| `list[].revise_date` | string | 修订日期 |
| `list[].items[].title` | string | 段落标题 |
| `list[].items[].content` | string | 段落内容 |
| `total` | integer |  |

---

## DrugstoreDaquanList

**Path:** `POST /pharma/general/v1/drugstore/list`

**Description:** 药品经营企业（含药店）-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.license_number` | string | no | 许可证编号 |
| `search.business_scope` | string | no | 经营范围 |
| `search.approval_date.max` | string | no |  |
| `search.approval_date.min` | string | no |  |
| `search.expiry_date.max` | string | no |  |
| `search.expiry_date.min` | string | no |  |
| `search.province` | string | no | 省份 |
| `search.city` | string | no | 城市 |
| `search.shaixuan` | string | no | 经营方式 |
| `search.yibao` | string | no | 是否医保定点 |
| `search.yibao_tanpan` | string | no | 是否医保谈判 |
| `search.status` | string | no | 状态 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].license_number` | string | 许可证编号 |
| `list[].company` | string | 经营企业/药店名称 |
| `list[].registered_address` | string | 注册地址 |
| `list[].province` | string | 省份 |
| `list[].city` | string | 城市 |
| `list[].warehouse_address` | string | 仓库地址 |
| `list[].legal_representative` | string | 法人代表 |
| `list[].header` | string | 企业负责人 |
| `list[].quality` | string | 质量负责人 |
| `list[].business_mode` | string | 经营方式 |
| `list[].business_scope` | string | 经营范围 |
| `list[].approval_date` | string | 发证日期 |
| `list[].expiry_date` | string | 证书有效期 |
| `list[].licensing_institutions` | string | 发证机构 |
| `list[].state` | string | 许可证状态 |
| `list[].yibao` | string | 是否医保定点 |
| `list[].code` | string | 医保定点机构编码 |
| `list[].yibao_tanpan` | string | 是否医保谈判 |
| `list[].status` | string | 状态 |
| `total` | integer |  |

---

## DrugstoreSalesFastList

**Path:** `POST /pharma/general/v1/drugstore_sales/list`

**Description:** 实体药店销售数据-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.keyword` | string | no | 通用名 |
| `search.active_ingredient` | string | no | 活性成分 |
| `search.manufacturer` | string | no | 企业名称 |
| `search.target` | string | no | 靶点 |
| `search.dosage_form` | string | no | 剂型 |
| `search.delivery_route` | string | no | 给药途径 |
| `search.indication` | string | no | 品种获批适应症 |
| `search.drug_type` | string | no | 药品类型 |
| `search.therapy_area_cn` | string | no | 治疗领域 |
| `search.year` | string | no | 年份 |
| `search.quarter` | string | no | 季度 |
| `search.number_of_manufacturers` | string | no | 品种过评厂家数 |
| `search.bool_exclusivity` | string | no | 是否独家 |
| `search.formulation_type` | string | no | 单方/复方 |
| `search.drug_jicai` | string | no | 国家集采品种 |
| `search.medical_insurance_type` | string | no | 医保分类 |
| `search.essential_yes_no` | string | no | 2018版基药 |
| `search.traditional_yes_no` | string | no | 中药保护品种 |
| `search.varieties_289` | string | no | 289品种 |
| `search.otc_type` | string | no | OTC/处方药 |
| `search.double_span_yes_no` | string | no | 是否双跨 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].year` | string | 年份 |
| `list[].quarter` | string | 季度 |
| `list[].drug_name` | string | 药品名称 |
| `list[].keyword` | string | 通用名 |
| `list[].dosage_form` | string | 剂型 |
| `list[].active_ingredient_cn` | string | 活性成分 |
| `list[].manufacturer` | string | MAH/生产企业 |
| `list[].money` | string | 销售额（元） |
| `list[].number` | string | 销售量 |
| `list[].corporation` | string | 集团/公司 |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `list[].indication` | string | 品种获批适应症 |
| `list[].target` | string | 靶点 |
| `list[].drug_type` | string | 药品类型 |
| `list[].type_shaixuan` | array | 药物类型 |
| `list[].delivery_route` | string | 给药途径 |
| `list[].number_of_manufacturers` | string | 品种过评厂家数 |
| `list[].bool_exclusivity` | string | 是否独家 |
| `list[].formulation_type` | string | 单方/复方 |
| `list[].drug_jicai` | array | 国家集采品种 |
| `list[].medical_insurance_type` | array | 医保分类 |
| `list[].essential_yes_no` | string | 2018版基药 |
| `list[].traditional_yes_no` | string | 中药保护品种 |
| `list[].varieties_289` | string | 289品种 |
| `list[].otc_type` | string | OTC/处方药 |
| `list[].double_span_yes_no` | string | 是否双跨 |
| `list[].manufacturer_location_code` | array | 企业所在地 |
| `list[].keyid` | string | keyid |
| `total` | integer |  |

---

## EnListedScreenBritain

**Path:** `POST /pharma/general/v1/en_listed_screen/britain/detail`

**Description:** 全球上市筛选-英国药品

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `delivery_route_code[].code` | array | code |
| `delivery_route_code[].content` | string | 名称 |
| `delivery_route_code[].path` | array | 路径 |
| `delivery_route_2` | string | 给药途径小类 |
| `delivery_route_1` | string | 给药途径大类 |
| `route` | string | 给药途径 |
| `orphan_market_date` | string | 孤儿药市场独占期 |
| `drug_tag_code` | string | 药品标签编号 |
| `drug_tag` | array | 药品标签 |
| `note` | string | 适应症备注 |
| `indication` | string | 适应症 |
| `dosage_form_code[].code` | array | code |
| `dosage_form_code[].content` | string | 名称 |
| `dosage_form_code[].path` | array | 路径 |
| `bool_review_report` | string | 审评文件 |
| `dosage_form_2` | string | 剂型小类 |
| `dosage_form_1` | string | 剂型（中） |
| `dosage_form` | string | 剂型 |
| `review_report_type` | array | 审评文件 |
| `source_url` | string | 官网 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_instruction` | string | 说明书 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `legal_category_cn` | string | 处方类型 (摩熵) |
| `bool_price` | string | 价格 |
| `bool_inactive_ingredient` | string | 辅料 |
| `strength` | string | 规格 |
| `company_1` | array | 公司 |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `par_relative_path` | string | 公共评估报告 |
| `pil_relative_path` | string | 患者版下载 |
| `spc_relative_path` | string | 专业版下载 |
| `manufacturer` | string | 公司 |
| `drug_name` | string | 药品名称 |
| `approval_number` | string | 授权编号 |
| `source` | string | 说明书查看 |
| `application_type` | string | 申报类型 |
| `active_ingredient_en` | string | 活性成分（英） |
| `country` | string | 国家 |
| `units` | string | 单位 |
| `quantity` | string | 活性成分含量 |
| `legal_category` | string | 处方类型 |
| `approval_date` | string | 批准日期 |
| `active_ingredient_cn` | string | 活性成分（中） |
| `active_ingredient` | string | 活性成分 |

---

## EnListedScreenChinaApproval

**Path:** `POST /pharma/general/v1/en_listed_screen/china_approval/detail`

**Description:** 全球上市筛选-中国药品批文

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `approval_number` | string | 批准文号 |
| `bool_exclusivity` | string | 是否独家 |
| `approval_type` | string | 国产或进口 |
| `marketing_status` | string | 市场状态 |
| `number_status` | string | 文号状态 |
| `drug_name` | string | 药品名称 |
| `formulation_type_single` | string | 单方/复方 |
| `drug_name_en` | string | 药品名称 (英文) |
| `trade_name` | string | 商品名称 (英文) |
| `trade_name_cn` | string | 商品名称 (中文) |
| `dosage_form` | string | 剂型 |
| `innovation_type` | string | 创新类型 |
| `specification` | string | 简化规格 |
| `type` | string | 药品类型 |
| `type_shaixuan` | array | 药物类型 |
| `specification_1` | string | 规格 |
| `package` | string | 包装规格 (进口) |
| `target` | array | 靶点 |
| `active_ingredient_en` | array | 活性成分 (英文) |
| `active_ingredient_cn` | string | 活性成分 (中文) |
| `atc_shaixuan` | array | ATC 分类 |
| `therapy_area_cn` | array | 治疗领域 |
| `active_indications` | array | 参考适应症 |
| `indication` | string | 品种获批适应症 |
| `low_price` | string | 纳入国家低价药品目录 |
| `yizhixing_tongguo` | string | 是否通过一致性评价 |
| `number_manufacturer` | string | 同品种厂家数 |
| `number_approval` | string | 同品种批文数 |
| `standard_code` | string | 药品本位码 |
| `standard_code_remark` | string | 药品本位码备注 |
| `approval_number_1` | string | 原批准文号 |
| `remarks` | string | 注册证号备注（进口） |
| `approval_number_2` | string | 分包装批准文号（进口） |
| `approval_date` | string | 批准日期 |
| `corporation_cn` | array | 上市许可持有人 (中文) |
| `corporation` | array | 上市许可持有人 (英文) |
| `corporation_address_cn` | array | 上市许可持有人地址 (中文) |
| `corporation_address` | array | 上市许可持有人地址 (英文) |
| `company_cn` | array | 公司名称 (进口)(中文) |
| `company` | array | 公司名称 (进口)(英文) |
| `company_address_cn` | array | 公司地址 (进口)(中文) |
| `company_address` | array | 公司地址 (进口)(英文) |
| `company_country_cn` | array | 国家/地区 (中文) |
| `company_country` | array | 国家/地区 (英文) |
| `manufacturer_cn` | array | 生产企业 (中文) |
| `manufacturer` | array | 生产企业 (英文) |
| `manufacturer_address_cn` | array | 生产地址 (中文) |
| `manufacturer_address` | array | 生产地址 (英文) |
| `responsible_person` | string | 境内责任人名称 |
| `responsible_person_address` | string | 境内责任人通讯地址 |
| `manufacturer_country_cn` | array | 厂商国家/地区 (中文) |
| `manufacturer_country` | array | 厂商国家/地区 (英文) |
| `end_date` | string | 有效截止日期 |
| `packaging_approval_date` | string | 分包装文号批准日期（进口） |
| `packaging_end_date` | string | 分包装文号有效期截止日（进口） |
| `packaging_enterprise` | string | 分包装企业名称（进口） |
| `packaging_address` | string | 分包装企业地址（进口） |
| `medical_insurance_type` | array | N 年医保分类 |
| `medical_insurance_number` | string | N 年医保编号 |
| `medical_insurance_name` | string | N 年医保药品名称 |
| `medical_insurance_form` | string | N 年医保剂型 |
| `limit` | string | N 年医保限制使用范围 |
| `medical_insurance_supplement` | string | N 年增补情况 |
| `essential_yes_no` | string | 是否 2018 版基药 |
| `number_essential` | string | 2018 版基药序号 |
| `essential_name` | string | 2018 版基药品种名称 |
| `essential_form` | string | 2018 版基药剂型 |
| `varieties_289` | string | 是否 289 品种 |
| `otc_type` | string | OTC/处方药 |
| `double_span_yes_no` | string | OTC 双跨 |
| `otc_specification` | string | OTC 规格 |
| `composition` | string | 处方组成 |
| `otc_source` | string | OTC 通知 |
| `number_traditional` | string | 中药保护品种编号 |
| `traditional_yes_no` | string | 是否中药保护品种 |
| `traditional_level` | string | 中药保护级别 |
| `traditional_begin` | string | 中药保护起始时间 |
| `traditional_end` | string | 中药保护终止时间 |
| `zhuce_info[].acceptance_number` | string | 受理号 |
| `zhuce_info[].applicant_address` | string | 申请人地址 |
| `zhuce_info[].applicant_contact` | string | 申请人联系人 |
| `zhuce_info[].applicant_contact_tel` | string | 申请人联系电话 |
| `zhuce_info[].applicant_e_mail` | string | 申请人电子邮箱 |
| `zhuce_info[].company[].content` | string |  |
| `zhuce_info[].drug_name` | string | 药品名称 |
| `zhuce_info[].drug_type` | string | 药品类型 |
| `zhuce_info[].registrate_classification` | string | 注册分类 |
| `zhuce_info[].specification` | string | 简化规格 |
| `patent_declaration[].patent_declaration_type` | string | 专利声明类型 |
| `patent_declaration[].registered_claim_number` | string | 登记号 |
| `patent_declaration[].registered_note` | string | 登记备注 |
| `patent_declaration[].registered_patent_number` | string | 登记专利号 |
| `patent_declaration[].registration_no` | string | 注册编号 |
| `public_details[].application_number` | string | 申请号 |
| `public_details[].approval_date` | string | 批准日期 |
| `public_details[].approval_file[].name` | string | 文件名 |
| `public_details[].approval_file[].url` | string | 文件链接 |
| `public_details[].assignee` | string | 受让人 |
| `public_details[].inventor` | string | 发明人 |
| `public_details[].name` | string | 名称 |
| `public_details[].relation_drug[].claim_number` | string | 权利要求项数 |
| `public_details[].relation_drug[].expired_at` | string | 到期日 |
| `public_details[].relation_drug[].note` | string | 备注 |
| `public_details[].relation_drug[].number` | string | 编号 |
| `public_details[].relation_drug[].patent_type` | string | 专利类型 |
| `public_details[].relation_drug[].state` | string | 状态 |
| `public_details[].relation_licence` | string | 关联许可 |
| `research_timeline[].ctime` | string | 创建时间 |
| `research_timeline[].ctime_datetime` | string | 创建时间（日期格式） |
| `research_timeline[].data[].approval_number` | string | 批准文号 |
| `research_timeline[].data[].change` | array | 变更内容 |
| `research_timeline[].data[].company` | array | 公司 |
| `research_timeline[].data[].company_address` | array | 公司地址 |
| `research_timeline[].data[].content` | string | 内容 |
| `research_timeline[].data[].corporation` | array | 企业 |
| `research_timeline[].data[].corporation_address` | array | 企业地址 |
| `research_timeline[].data[].dosage_form` | string | 剂型 |
| `research_timeline[].data[].drug_name` | array | 药品名称 |
| `research_timeline[].data[].manufacturer` | array | 生产企业 |
| `research_timeline[].data[].manufacturer_address` | array | 生产地址 |
| `research_timeline[].data[].record_number` | string | 记录号 |
| `research_timeline[].data[].source_date` | string | 来源日期 |
| `research_timeline[].data[].specification` | string | 规格 |
| `research_timeline[].data[].trade_name` | array | 商品名 |
| `research_timeline[].date` | string | 日期 |
| `research_timeline[].title` | string | 标题 |
| `research_timeline[].type` | string | 类型 |

---

## EnListedScreenEuCenter

**Path:** `POST /pharma/general/v1/en_listed_screen/eu_center/detail`

**Description:** 全球上市筛选-欧盟药品-集中审批

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `marketing_not_authorisation_date` | string | 上市许可撤销/到期/失效日期 |
| `withdrawal_of_marketing_authorisation_date` | string | 撤回批准日期 |
| `withdrawal_of_application_date` | string | 撤回申请日期 |
| `opinion_status` | string | 意见状态 |
| `advanced_therapy` | string | 先进疗法 |
| `priority_medicine` | string | 优先药物 |
| `delivery_route_code[].code` | array | code |
| `delivery_route_code[].content` | string | 名称 |
| `delivery_route_code[].path` | array | 路径 |
| `delivery_route_2` | string | 给药途径小类 |
| `delivery_route_1` | string | 给药途径（中文） |
| `dosage_form_code[].code` | array | code |
| `dosage_form_code[].content` | string | 名称 |
| `dosage_form_code[].path` | array | 路径 |
| `approval_number` | string | 产品编号 |
| `approval_number_1` | string | 授权编号 |
| `bool_review_report` | string | 审评文件 |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `status` | array | 市场状态（摩熵） |
| `source_url` | string | 官网 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_instruction` | string | 说明书 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `pharm_classes` | string | 药理分类 |
| `drug_tag_code` | string | 药物标签（摩熵） |
| `drug_tag` | array | 药物标签（摩熵） |
| `bool_price` | string | 价格 |
| `bool_inactive_ingredient` | string | 辅料 |
| `company_1` | array | 公司 |
| `review_report_type` | array | 审评文件 |
| `par_relative_path` | string | 评估报告 |
| `indication` | string | 适应症 |
| `manufacturer` | string | 公司 |
| `drug_name` | string | 药品名称 |
| `additional_monitoring` | string | 补充监测 |
| `url` | string | url |
| `risk_path_last_updated` | string | 更新日期（风险评估） |
| `risk_path_first_published` | string | 发布日期 |
| `risk_path` | string | 风险管理计划 |
| `refusal_marketing_authorisation_date` | string | 拒绝申请日期 |
| `product_information_path` | string | 药品说明书 |
| `product_information_last_updated` | string | 更新日期（药品说明书） |
| `product_information_first_published` | string | 发布日期 |
| `patient_safety` | string | 患者安全 |
| `overview_source` | string | 药物概述查看 |
| `overview_path` | string | 药物概述下载 |
| `overview_last_updated` | string | 更新日期（药物概述） |
| `overview_first_published` | string | 发布日期 |
| `orphan_medicine` | string | 孤儿药 |
| `last_updated_date` | string | 更新日期 |
| `generic` | string | 仿制药 |
| `exceptional_circumstances` | string | 特殊情况批准 |
| `dosage_form_2` | string | 剂型小类 |
| `dosage_form_1` | string | 剂型（中文） |
| `date_of_opinion` | string | 意见日期 |
| `conditional_approval` | string | 条件批准 |
| `biosimilar` | string | 生物类似药 |
| `authorised_presentations_url` | string | 授权产品链接 |
| `authorised_presentations_path` | string | 授权产品信息 |
| `authorised_presentations_last_updated` | string | 更新日期（授权产品信息） |
| `authorised_presentations_first_published` | string | 发布日期 |
| `approval_type_cn` | string | 药品类型 |
| `active_ingredient_en` | string | 活性成分（英） |
| `accelerated_assessment` | string | 加速审评 |
| `atc_shaixuan` | array | ATC 筛选 |
| `therapeutic_area` | string | 治疗领域 |
| `approval_type` | string | 药品类型 |
| `pharmacotherapeutic_group` | string | 药物治疗分类 |
| `atc` | array | ATC |
| `approval_date` | string | 批准日期 |
| `marketing_status` | array | 市场状态 |
| `route` | string | 给药途径 |
| `dosage_form` | string | 剂型 |
| `strength` | string | 规格 |
| `active_ingredient_cn` | string | 活性成分（中） |
| `active_ingredient` | string | 活性成分 |
| `inn` | string | 通用名 |
| `country` | string | 国家 |

---

## EnListedScreenEuMutual

**Path:** `POST /pharma/general/v1/en_listed_screen/eu_mutual/detail`

**Description:** 全球上市筛选-欧盟药品-互认程序

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `dosage_form_code[].code` | array | code |
| `dosage_form_code[].content` | string | 名称 |
| `dosage_form_code[].path` | array | 路径 |
| `bool_review_report` | string | 审评文件 |
| `review_report_type` | array | 审评文件 |
| `source_url` | string | 官网 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_instruction` | string | 说明书 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `drug_tag_code` | string | 药物标签（摩熵） |
| `drug_tag` | array | 药物标签（摩熵） |
| `type` | string | 药品类型 (摩熵) |
| `bool_price` | string | 价格 |
| `bool_inactive_ingredient` | string | 辅料 |
| `company_1` | array | 公司 |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `status` | array | 市场状态（摩熵） |
| `drug_name_1` | string | 药品名称 (RMS） |
| `manufacturer` | string | 公司 |
| `drug_name` | string | 药品名称 |
| `approval_number` | string | MR 编号 |
| `rms_cn` | string | 参照成员国 (RMS) |
| `legal_category_cn` | string | 处方类型 (中) |
| `drug_category_cn` | string | 药品分类 (中) |
| `dosage_form_2` | string | 剂型小类 |
| `dosage_form_1` | string | 剂型（中） |
| `application_type_level_3_cn` | string | 申请类型 3(中) |
| `application_type_level_2_cn` | string | 申请类型 2(中) |
| `application_type_level_1_cn` | string | 申请类型 1(中) |
| `application_type_level_1` | string | 申请类型 1 |
| `application_type_detail_cn` | string | 申请类型 (中) |
| `application_type_detail` | string | 申请类型 |
| `application_type_cn` | string | 申请类型 (中) |
| `application_type` | string | 申请类型 |
| `active_ingredient_strength` | string | 活性成分 |
| `approval_date` | string | 批准日期 |
| `active_ingredient_en` | string | 活性成分（英） |
| `atc_shaixuan` | array | ATC 筛选 |
| `relative_path` | string | 药品说明书 |
| `date_of_last_change` | string | 更新日期 |
| `drug_category` | string | 药品分类 |
| `active_ingredient_cn` | string | 活性成分（中） |
| `application_type_level_2` | string | 申请类型 2 |
| `application_type_level_3` | string | 申请类型 3 |
| `rms` | string | 参照成员国（RMS) |
| `atc` | array | ATC |
| `legal_category` | string | 处方类型 |
| `marketing_status` | array | 市场状态 |
| `dosage_form` | string | 剂型 |
| `strength` | string | 规格 |
| `active_ingredient` | string | 活性成分 |
| `country` | string | 国家 |

---

## EnListedScreenFdaCber

**Path:** `POST /pharma/general/v1/en_listed_screen/fda_cber/detail`

**Description:** 全球上市筛选-美国FDA药品-CBER

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `atc_shaixuan` | array | ATC 分类 |
| `bool_para_iv` | string | ParaIV 声明 |
| `para_iv_detail.detail[].date_of_first_applicant_approval` | string | 首次申请人批准日期 |
| `para_iv_detail.detail[].date_of_first_commercial_marketing_by_ftf` | string | FTF 首次商业营销日期 |
| `para_iv_detail.detail[].date_of_submission` | string | 提交日期 |
| `para_iv_detail.detail[].day_decision_posting_date` | string | 决定公布日期 |
| `para_iv_detail.detail[].day_status` | string | 状态 |
| `para_iv_detail.detail[].expiration_date_of_last_qualifying_patent` | string | 最后符合条件的专利到期日 |
| `para_iv_detail.detail[].number_of_andas_submitted` | string | 提交的 ANDA 数量 |
| `para_iv_detail.detail[].source_url` | string | 官网链接 |
| `para_iv_detail.detail[].strength` | string | 规格 |
| `para_iv_detail.dosage_form` | string | 剂型 |
| `para_iv_detail.drug_name` | string | 药物名称 |
| `ref_product_proper_name` | string | 参考产品 (英文) |
| `ref_product_proper_name_cn` | string | 参考产品 (中文) |
| `product_exclusivity_date` | string | 参考产品独占期 |
| `product_information[].type` | string | 类型 |
| `product_information[].name` | string | 名称 |
| `product_information[].path` | string | 路径 |
| `product_information[].source` | string | 来源 |
| `legal_category` | string | 处方类型 (英文) |
| `legal_category_cn` | string | 处方类型 (中文) |
| `exclusivity_expiration_date` | string | 独占期 |
| `inactive_ingredient` | string | 辅料 (英文) |
| `inactive_ingredient_cn` | string | 辅料 (中文) |
| `route` | string | 给药途经 |
| `delivery_route` | string | 给药途径（摩熵） |
| `delivery_route_code_content` | array | 给药途径 |
| `company_1` | array | 公司名称（筛选系统） |
| `orphan` | string | 孤儿药 |
| `orphan_exclusivity_date` | string | 孤儿药独占期 |
| `source_url` | string | 官网 |
| `strength` | string | 规格 |
| `country` | string | 国家 |
| `dosage_form` | string | 剂型 |
| `dosage_form_code_content` | array | 剂型（摩熵） |
| `price` | string | 价格 |
| `first_interchangeable_exclusivity_date` | string | 可互换产品独占期 |
| `supplement[].approval_date` | string | 批准日期 |
| `supplement[].indication` | string | 适应症 |
| `supplement[].submission` | string | submission |
| `approval_date` | string | 批准日期 |
| `company_keywords` | string | 企业关键字 |
| `company` | string | 企业集团 |
| `manufacturer` | string | 申报企业 |
| `manufacturer_cn` | string | 申报企业 |
| `approval_number` | string | 申请号 |
| `application_type` | string | 申请类型 |
| `application_type_cn` | string | 申请类型 |
| `apply_type` | string | 申请途径 |
| `review_route` | array | 审评通道 |
| `review_route_cn` | array | 审评通道 |
| `bool_review_report` | string | 审评文件 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `marketing_status_cn` | array | 市场状态 |
| `bool_inactive_ingredient` | string | 是否有辅料 |
| `bool_price` | string | 是否有价格 |
| `bool_instruction` | string | 是否有说明书 |
| `indication` | string | 适应症 |
| `data_source` | string | 数据来源 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `review_route_detail[].accelerated_approval[].accelerated_approval_date` | string | accelerated_approval_date |
| `review_route_detail[].accelerated_approval[].approval_basis` | string | approval_basis |
| `review_route_detail[].accelerated_approval[].conversion_withdrawal_status` | string | conversion_withdrawal_status |
| `review_route_detail[].accelerated_approval[].fda_receive_date` | string | fda_receive_date |
| `review_route_detail[].accelerated_approval[].full_approval_conversion_withdrawal_date` | string | full_approval_conversion_withdrawal_date |
| `review_route_detail[].accelerated_approval[].indication` | string | 适应症 |
| `review_route_detail[].accelerated_approval[].total_time_to_accelerated_approval_months` | string | total_time_to_accelerated_approval_months |
| `review_route_detail[].breakthrough_therapy[].approval_date` | string | 批准日期 |
| `review_route_detail[].breakthrough_therapy[].indication` | string | 适应症 |
| `review_route_detail[].breakthrough_therapy[].submission_type` | string | submission_type |
| `review_route_detail[].cgt[].cgt_exclusivity_forfeiture` | string | cgt_exclusivity_forfeiture |
| `review_route_detail[].cgt[].date_of_approval` | string | date_of_approval |
| `review_route_detail[].cgt[].date_of_first_commercial_marketing_of_cgt_with_exclusivity` | string | date_of_first_commercial_marketing_of_cgt_with_exclusivity |
| `review_route_detail[].cgt[].eligible_for_cgt_exclusivity` | string | eligible_for_cgt_exclusivity |
| `review_route_detail[].cgt[].nda_number` | string | nda_number |
| `review_route_detail[].cgt[].rld_name` | string | rld_name |
| `review_route_detail[].cgt[].source_url` | string | 官网 |
| `review_route_detail[].fast_track[].approval_date` | string | 批准日期 |
| `review_route_detail[].fast_track[].indication` | string | 适应症 |
| `active_ingredient` | string | 通用名（英文） |
| `active_ingredient_cn` | string | 通用名（中文） |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `list_offpatent` | string | 无仿药的已过专利期及独占期药品 |
| `pharm_classes[].cn` | string | cn |
| `pharm_classes[].en` | string | en |
| `type` | string | 药品类型 |
| `drug_name` | string | 药品名称 |
| `drug_tag` | array | 药物标签 |
| `drug_tag_code` | array | 药物标签 |
| `general_information` | string | 药物简述 |
| `box_warning` | string | 黑框警告 |
| `bool_box_warning` | string | 是否黑框警告 |
| `supporting_documents[].type` | string | 类型 |
| `supporting_documents[].name` | string | 名称 |
| `supporting_documents[].path` | string | 路径 |
| `supporting_documents[].source` | string | 来源 |
| `company_china` | string | 中国企业申报 |
| `orange_purple` | string | 紫皮书 |
| `latest_approval_date` | string | 最新批准日期 |

---

## EnListedScreenFdaCder

**Path:** `POST /pharma/general/v1/en_listed_screen/fda_cder/detail`

**Description:** 全球上市筛选-美国FDA-CDER

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `data_source` | string | 数据来源 |
| `drug_tag` | array | 药物标签 |
| `drug_name` | string | 药品名称 |
| `approval_number` | string | 申请号 |
| `application_type` | string | 申请类型（英文） |
| `application_type_cn` | string | 申请类型（中文） |
| `apply_type` | string | 申请途径 |
| `manufacturer` | string | 申报企业（英文） |
| `manufacturer_cn` | string | 申报企业（中文） |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `active_ingredient` | string | 活性成分（英文） |
| `active_ingredient_cn` | string | 活性成分（中文） |
| `approval_date` | string | 批准日期 |
| `strength` | string | 规格 |
| `dosage_form_or_route` | string | 剂型/给药途径 |
| `delivery_route_code_content` | array | 给药途径 |
| `dosage_form_code_content` | array | 剂型 |
| `latest_approval_date` | string | 最新批准日期 |
| `marketing_status_cn` | array | 市场状态 |
| `rld` | string | 参比制剂 (RLD) |
| `rs` | string | 对照制剂 (RS) |
| `te_code` | array | 治疗等效代码 |
| `orange_purple` | string | 橙皮书/紫皮书 |
| `first_generic` | string | 首仿药 |
| `list_offpatent` | string | 无仿药的已过专利期及独占期药品 |
| `indication` | string | 适应症 |
| `pharm_classes[].cn` | string | cn |
| `pharm_classes[].en` | string | en |
| `inactive_ingredient` | string | 辅料 |
| `inactive_ingredient_cn` | string | 辅料 |
| `general_information` | string | 药物简述 |
| `box_warning` | string | 黑框警告 |
| `bool_box_warning` | string | 是否黑框警告 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_review_report` | string | 审评文件 |
| `atc_shaixuan` | array | ATC 分类 |
| `atc` | string | ATC |
| `source_url` | string | 官网 |
| `submission_class_cn` | string | 提交类型 |
| `submission_class` | string | 提交类型 |
| `orphan` | string | 孤儿药 |
| `review_route` | array | 审评通道 |
| `review_route_cn` | array | 审评通道 |
| `review_route_detail[].accelerated_approval[].accelerated_approval_date` | string | accelerated_approval_date |
| `review_route_detail[].accelerated_approval[].approval_basis` | string | approval_basis |
| `review_route_detail[].accelerated_approval[].conversion_withdrawal_status` | string | conversion_withdrawal_status |
| `review_route_detail[].accelerated_approval[].fda_receive_date` | string | fda_receive_date |
| `review_route_detail[].accelerated_approval[].full_approval_conversion_withdrawal_date` | string | full_approval_conversion_withdrawal_date |
| `review_route_detail[].accelerated_approval[].indication` | string | 适应症 |
| `review_route_detail[].accelerated_approval[].total_time_to_accelerated_approval_months` | string | total_time_to_accelerated_approval_months |
| `review_route_detail[].breakthrough_therapy[].approval_date` | string | 批准日期 |
| `review_route_detail[].breakthrough_therapy[].indication` | string | 适应症 |
| `review_route_detail[].breakthrough_therapy[].submission_type` | string | submission_type |
| `review_route_detail[].cgt[].cgt_exclusivity_forfeiture` | string | cgt_exclusivity_forfeiture |
| `review_route_detail[].cgt[].date_of_approval` | string | date_of_approval |
| `review_route_detail[].cgt[].date_of_first_commercial_marketing_of_cgt_with_exclusivity` | string | date_of_first_commercial_marketing_of_cgt_with_exclusivity |
| `review_route_detail[].cgt[].eligible_for_cgt_exclusivity` | string | eligible_for_cgt_exclusivity |
| `review_route_detail[].cgt[].nda_number` | string | nda_number |
| `review_route_detail[].cgt[].rld_name` | string | rld_name |
| `review_route_detail[].cgt[].source_url` | string | 官网 |
| `review_route_detail[].fast_track[].approval_date` | string | 批准日期 |
| `review_route_detail[].fast_track[].indication` | string | 适应症 |
| `bool_para_iv` | string | ParaIV 声明 |
| `para_iv_detail.detail[].date_of_first_applicant_approval` | string | 首次申请人批准日期 |
| `para_iv_detail.detail[].date_of_first_commercial_marketing_by_ftf` | string | FTF 首次商业营销日期 |
| `para_iv_detail.detail[].date_of_submission` | string | 提交日期 |
| `para_iv_detail.detail[].day_decision_posting_date` | string | 决定公布日期 |
| `para_iv_detail.detail[].day_status` | string | 状态 |
| `para_iv_detail.detail[].expiration_date_of_last_qualifying_patent` | string | 最后符合条件的专利到期日 |
| `para_iv_detail.detail[].number_of_andas_submitted` | string | 提交的 ANDA 数量 |
| `para_iv_detail.detail[].source_url` | string | 官网链接 |
| `para_iv_detail.detail[].strength` | string | 规格 |
| `para_iv_detail.dosage_form` | string | 剂型 |
| `para_iv_detail.drug_name` | string | 药物名称 |
| `status` | array | 市场状态 (摩熵) |
| `company_1` | array | 公司名称（筛选系统） |
| `country` | string | 国家 |
| `price` | string | 价格 |
| `bool_price` | string | 是否有价格 |
| `bool_inactive_ingredient` | string | 是否有辅料 |
| `bool_instruction` | string | 是否有说明书 |
| `type` | string | 药品类型 |
| `legal_category_cn` | string | 处方类型（筛选系统） |
| `legal_category` | string | 处方类型 |
| `cid` | array | cid |

---

## EnListedScreenJpBio

**Path:** `POST /pharma/general/v1/en_listed_screen/jp_bio/detail`

**Description:** 全球上市筛选-日本药品-生物药

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `country` | string | 国家 |
| `inn` | string | 通用名 |
| `drug_name` | string | 药品名称 |
| `trade_name_1.cn` | string | 中文 |
| `trade_name_1.en` | string | 英文 |
| `trade_name_1.jp` | string | 日文 |
| `manufacturer_standard[].manufacturer_type` | string | 厂商类型 |
| `manufacturer_standard[].manufacturer_type_cn` | string | 厂商名称（中） |
| `manufacturer_standard[].manufacturer` | string | 厂商名称 |
| `company_1` | array | 公司 |
| `yj_code` | string | YJ 编号 |
| `company_no` | string | 企业编号 |
| `approval_number` | string | 注册号 |
| `drug_type` | string | 药物类型 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `related_documents[].name` | string | 文档名称 |
| `related_documents[].data[].name` | string | 文档名称 |
| `related_documents[].data[].url` | string | 文档 URL |
| `bool_instruction` | string | 是否有说明书 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `source_url` | string | 官网 |
| `bool_review_report` | string | 是否有审评文件 |
| `review_report_type` | array | 审评文件 |

---

## EnListedScreenJpOtc

**Path:** `POST /pharma/general/v1/en_listed_screen/jp_otc/detail`

**Description:** 全球上市筛选-日本药品-非处方药

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `country` | string | 国家 |
| `legal_category` | string | 处方类型 |
| `drug_type` | string | 药效分类 |
| `drug_name` | string | 药品名称 |
| `trade_name_1.cn` | string | 中文 |
| `trade_name_1.en` | string | 英文 |
| `trade_name_1.jp` | string | 日文 |
| `inn` | string | 通用名 |
| `drug_description` | string | 药品描述 |
| `indication` | array | 适应症 |
| `drug_interaction` | string | 药效相互作用 |
| `use_method` | string | 使用方法 |
| `ues_notes` | string | 使用注意 |
| `active_ingredient` | string | 活性成分 |
| `active_ingredient_en` | string | 活性成分（英文） |
| `active_ingredient_cn` | string | 活性成分（中文） |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `active_ingredient_map[].jp` | string | 日文 |
| `active_ingredient_map[].cn` | string | 中文 |
| `active_ingredient_map[].quantity` | string | 数量 |
| `inactive_ingredient` | string | 辅料（英文） |
| `inactive_ingredient_cn` | string | 辅料（中文） |
| `manufacturer_standard[].manufacturer_type` | string | 厂商类型 |
| `manufacturer_standard[].manufacturer_type_cn` | string | 厂商名称（中） |
| `manufacturer_standard[].manufacturer` | string | 厂商名称 |
| `company_1` | array | 公司 |
| `dosage_form_code_content` | array | 剂型 (摩熵) |
| `dosage_form` | string | 剂型 |
| `riskclass` | string | 风险等级 |
| `smalldrug_type` | string | 药效具体分类（英文） |
| `smalldrug_type_cn` | string | 药效具体分类（中文） |
| `yj_code` | string | YJ 编号 |
| `company_no` | string | 企业编号 |
| `bool_inactive_ingredient` | string | 有无辅料 |
| `package` | string | 包装 |
| `otchtml_relative_path` | string | otc 药物详情页 |
| `source_url` | string | 官网 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `instruction_route_1[].manufacturer` | string |  |
| `instruction_route_1[].data[].date` | string | 日期 |
| `instruction_route_1[].data[].name` | string | 名称 |
| `instruction_route_1[].data[].source` | string | 来源 |
| `instruction_route_1[].data[].type` | string | 类型 |
| `instruction_route_1[].data[].update` | string | 更新信息 |
| `instruction_route_1[].data[].url` | string | URL |
| `related_documents[].name` | string | 文档名称 |
| `related_documents[].data[].name` | string | 文档名称 |
| `related_documents[].data[].url` | string | 文档 URL |
| `bool_instruction` | string | 是否有说明书 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_review_report` | string | 是否有审评文件 |
| `review_report_type` | array | 审评文件 |

---

## EnListedScreenJpRx

**Path:** `POST /pharma/general/v1/en_listed_screen/jp_rx/detail`

**Description:** 全球上市筛选-日本药品-处方药

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球上市筛选-列表信息’接口获取 *** 必须从GeneralV1_EnListedScreenList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `keyid` | string | 唯一标识 |
| `country` | string | 国家 |
| `yj_code` | string | YJ 编号 |
| `company_no` | string | 企业编号 |
| `revision_date` | array | 创建或修订日期 |
| `version` | string | 版本 |
| `sccjno` | string | 日本标准商品分类编号 |
| `therapeutic_area` | string | 治疗药效分类 |
| `therapeutic_area_cn` | string | 治疗药效分类（中） |
| `drug_name` | string | 药品名称 |
| `trade_name_1.cn` | string | 中文 |
| `trade_name_1.en` | string | 英文 |
| `trade_name_1.jp` | string | 日文 |
| `approval_number` | string | 注册号 |
| `pricelist_date` | string | 药价基准表收录时间 |
| `marketing_date` | string | 上市日期 |
| `inn` | string | 通用名 |
| `contraindications` | array | 禁忌症 |
| `indication` | array | 适应症 |
| `package` | string | 包装 |
| `manufacturer_standard[].manufacturer_type` | string | 厂商类型 |
| `manufacturer_standard[].manufacturer_type_cn` | string | 厂商名称（中） |
| `manufacturer_standard[].manufacturer` | string | 厂商名称 |
| `company_1` | array | 公司 |
| `legal_category` | string | 药物类型/处方类型 |
| `legal_category_cn` | string | 药物类型 |
| `warning` | string | 警告 |
| `active_ingredient` | string | 活性成分 |
| `active_ingredient_en` | string | 活性成分（英） |
| `active_ingredient_cn` | string | 活性成分（中） |
| `active_ingredient_standard[].active` | string | 活性成分 |
| `active_ingredient_standard[].en` | string | 英文 |
| `active_ingredient_standard[].cn` | string | 中文 |
| `active_ingredient_map[].jp` | string | 日文 |
| `active_ingredient_map[].cn` | string | 中文 |
| `active_ingredient_map[].quantity` | string | 数量 |
| `inactive_ingredient` | string | 辅料 |
| `inactive_ingredient_cn` | string | 辅料 (中) |
| `inactive_ingredient_map[].jp` | string | 日文 |
| `inactive_ingredient_map[].cn` | string | 中文 |
| `inactive_ingredient_map[].quantity` | string | 数量 |
| `price` | string | 价格 |
| `atc_shaixuan` | array | ATC 分类 |
| `bool_price` | string | 有无价格 |
| `bool_inactive_ingredient` | string | 有无辅料 |
| `drug_tag` | array | 药物标签（药融云） |
| `drug_tag_code` | string | 药物标签（药融云） |
| `bool_generic` | string | 是否为仿制药 |
| `rxhtml_relative_path` | string | PMDA 药物详情页 |
| `bool_if` | string | 是否有 IF 文件 |
| `instruction_route[].date` | string | 日期 |
| `instruction_route[].name` | string | 名称 |
| `instruction_route[].source` | string | 来源 |
| `instruction_route[].type` | string | 类型 |
| `instruction_route[].update` | string | 更新信息 |
| `instruction_route[].url` | string | URL |
| `if_relative_path` | string | IF 文件 |
| `related_documents[].name` | string | 文档名称 |
| `related_documents[].data[].name` | string | 文档名称 |
| `related_documents[].data[].url` | string | 文档 URL |
| `bool_instruction` | string | 是否有说明书 |
| `review_report_route[].date` | string | 日期 |
| `review_report_route[].name` | string | 名称 |
| `review_report_route[].source` | string | 来源 |
| `review_report_route[].type` | string | 类型 |
| `review_report_route[].update` | string | 更新信息 |
| `review_report_route[].url` | string | URL |
| `bool_review_report` | string | 是否有审评文件 |
| `review_report_type` | array | 审评文件 |
| `source_url` | string | 官网 |
| `dosage_form_code_content` | array | 剂型 (摩熵) |
| `dosage_form` | string | 剂型 |
| `delivery_route_code[].code` | array | code |
| `delivery_route_code[].content` | string | 名称 |
| `delivery_route_code[].path` | array | 路径 |

---

## EnListedScreenList

**Path:** `POST /pharma/general/v1/en_listed_screen/list`

**Description:** 全球上市筛选-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.company` | string | no | 公司名称 |
| `search.approval_number` | string | no | 申请号/批准号 |
| `search.approval_date.max` | string | no |  |
| `search.approval_date.min` | string | no |  |
| `search.marketing_date.max` | string | no |  |
| `search.marketing_date.min` | string | no |  |
| `search.strength` | string | no | 规格 |
| `search.bool_instruction` | boolean | no | 是否有说明书 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].keyid` | string | 唯一标识 |
| `list[].drug_name` | string | 药品名称 |
| `list[].drug_tag` | array | 药品标签 |
| `list[].company_1` | array | 公司名称 |
| `list[].approval_number` | string | 申请号/批准号 |
| `list[].strength` | string | 规格 |
| `list[].active_ingredient` | string | 活性成分（英） |
| `list[].active_ingredient_cn` | string | 活性成分（中） |
| `list[].dosage_form` | string | 剂型 |
| `list[].route` | string | 给药途径 |
| `list[].dosage_form_code_content` | array | 剂型（摩熵） |
| `list[].delivery_route_code_content` | array | 给药途径（摩熵） |
| `list[].country` | string | 上市国家/地区 |
| `list[].marketing_status` | array | 市场状态 |
| `list[].status` | array | 状态 |
| `list[].approval_date` | string | 批准日期 |
| `list[].marketing_date` | string | 上市日期 |
| `list[].inactive_ingredient` | string | 辅料 |
| `list[].legal_category` | string | 处方类型 |
| `list[].legal_category_cn` | string | 处方类型（摩熵） |
| `list[].type` | string | 药品类型（摩熵） |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].review_report_route[].date` | string |  |
| `list[].review_report_route[].name` | string |  |
| `list[].review_report_route[].source` | string |  |
| `list[].review_report_route[].type` | string |  |
| `list[].review_report_route[].update` | string |  |
| `list[].review_report_route[].url` | string |  |
| `list[].instruction_route[].date` | string |  |
| `list[].instruction_route[].name` | string |  |
| `list[].instruction_route[].source` | string |  |
| `list[].instruction_route[].type` | string |  |
| `list[].instruction_route[].update` | string |  |
| `list[].instruction_route[].url` | string |  |
| `list[].source_url` | string | 官网 |
| `total` | integer |  |

---

## EnMarketedDrugPatentDetail

**Path:** `POST /pharma/general/v1/en_marketed_drug_patent/detail`

**Description:** 全球上市药品专利-专利基本信息详情接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id_1` | string | no | 药物品种id |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `drug_name` | array | 药品名称 |
| `data_source` | string | 数据源 |
| `trade_name` | array | 商品名 |
| `active_ingredient` | array | 活性成分 |
| `alias` | array | 别名 |
| `drug_type` | string | 药品类型 |
| `dosage_form` | string | 剂型 |
| `specification` | array | 规格 |
| `licensor` | array | 持证商 |
| `target` | array | 靶点 |
| `indication` | array | 适应症 |
| `atc_shaixuan` | array | ATC分类 |
| `patent_information[].publication_number` | string | 公开（公告）号 |
| `patent_information[].patent_name` | string | 名称 |
| `patent_information[].grant_date` | string | 授权日 |
| `patent_information[].expiry_date` | string | 预估到期日 |
| `patent_information[].simple_legal_status` | string | 法律状态 |
| `patent_information[].current_patentee` | array | 当前专利权人 |
| `patent_information[].patent_licensee` | array | 专利被许可人 |
| `patent_information[].relation_type` | string | 上市许可持有人与专利权人的关系 |
| `patent_information[].patent_type` | array | 专利类型 |
| `patent_information[].simple_family_publication_number` | array | 简单同族公开号 |
| `patent_information[].extend_family_publication_number` | array | 扩展同族公开号 |

---

## EnMarketedPatentBasicList

**Path:** `POST /pharma/general/v1/en_marketed_drug_patent/list`

**Description:** 全球上市药品专利-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.licensor` | string | no | 持证商 |
| `search.data_source` | string | no | 数据源 |
| `search.patent_name` | string | no | 专利名称 |
| `search.publication_number` | string | no | 专利文献号 |
| `search.current_patentee` | string | no | 当前专利权人 |
| `search.grant_date.max` | string | no |  |
| `search.grant_date.min` | string | no |  |
| `search.expiry_date.max` | string | no |  |
| `search.expiry_date.min` | string | no |  |
| `search.patent_type` | string | no | 专利类型 |
| `search.simple_legal_status` | string | no | 法律状态 |
| `search.patent_declaration_type` | string | no | 专利声明类型(中国) |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name` | string | 药品名称 |
| `list[].data_source` | string | 数据源 |
| `list[].alias` | string | 别名 |
| `list[].licensor` | string | 持证商 |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].publication_number` | string | 专利公开（公告）号 |
| `list[].patent_name` | string | 专利名称 |
| `list[].current_patentee` | string | 当前专利权人 |
| `list[].grant_date` | string | 专利授权日 |
| `list[].expiry_date` | string | 预估到期日 |
| `list[].simple_legal_status` | string | 法律状态 |
| `list[].id_1` | string | 药物品种id |
| `total` | integer |  |

---

## EnMarketedPatentSubCnList

**Path:** `POST /pharma/general/v1/en_marketed_drug_patent/sub_cn`

**Description:** 全球上市药品专利-中国专利链接详情接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id_1` | string | no | 药物品种id |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].company` | string | 上市许可持有人 |
| `list[].bidder_contact` | string | 境内联系人 |
| `list[].contact_tel` | string | 境内联系电话 |
| `list[].e_mail` | string | 电子邮箱 |
| `list[].postal_address` | string | 境内通讯地址 |
| `list[].registration_detail[].approval_number` | string | 批准文号/注册证号 |
| `list[].registration_detail[].specification` | string | 规格 |
| `list[].registration_detail[].registration_type` | string | 登记表类型 |
| `list[].registration_detail[].registration_status` | string | 登记状态 |
| `list[].registration_detail[].registration_public_date` | string | 登记公开时间 |
| `list[].registration_detail[].registration_created_date` | string | 登记创建时间 |
| `list[].generic_drug_detail[].applicant_name` | string | 仿制药申请人名称 |
| `list[].generic_drug_detail[].acceptance_number` | string | 受理号 |
| `list[].generic_drug_detail[].drug_registrate_classification` | string | 注册分类 |
| `list[].generic_drug_detail[].approval_number` | string | 被仿制药批准文号 |
| `list[].generic_drug_detail[].acceptance_date` | string | 受理日期 |
| `list[].generic_drug_detail[].declaration_publication_date` | string | 公开日期 |
| `list[].generic_drug_detail[].applicant_contact` | string | 联系人 |
| `list[].generic_drug_detail[].applicant_contact_tel` | string | 联系电话 |
| `list[].generic_drug_detail[].applicant_e_mail` | string | 电子邮箱 |
| `list[].generic_drug_detail[].applicant_address` | string | 通讯地址 |
| `total` | integer |  |

---

## EnMarketedPatentSubEuSpcList

**Path:** `POST /pharma/general/v1/en_marketed_drug_patent/sub_eu_spc`

**Description:** 全球上市药品专利-补充保护证书信息详情接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id_1` | string | no | 药物品种id |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].spc_number` | string | SPC号 |
| `list[].filing_date` | string | SPC提交日 |
| `list[].spc_country` | string | SPC国家 |
| `list[].first_marketing_authorization_date` | string | 国家上市许可编号及日期 |
| `list[].spc_expiry_date` | string | SPC到期日 |
| `list[].eu_marketing_authorization_date` | string | EEC/EU上市许可编号及日期 |
| `list[].spc_status` | string | SPC授权状态 |
| `list[].pediatric_exclusivity` | string | 儿科用药状态 |
| `total` | integer |  |

---

## EnMarketedPatentSubUsaList

**Path:** `POST /pharma/general/v1/en_marketed_drug_patent/sub_usa`

**Description:** 全球上市药品专利-美国专利链接详情接口

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id_1` | string | no | 药物品种id |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].approval_number_1` | string | 药品申请号 |
| `list[].rld` | string | 参比制剂（RLD） |
| `list[].rs` | string | 对照标准制剂（RS） |
| `list[].te_code` | string | 治疗等效代码 |
| `list[].market_status` | array | 产品编号-市场状态 |
| `list[].drug_approval_date` | string | 药品批准日 |
| `list[].patent_details[].publication_number` | string | 专利公开(公告)号 |
| `list[].patent_details[].drug_product_flag` | string | 产品专利 |
| `list[].patent_details[].drug_substance_flag` | string | 物质专利 |
| `list[].patent_details[].patent_use_code` | string | 专利用途码 |
| `list[].patent_details[].definition` | string | 专利用途码释义 |
| `list[].patent_details[].pdf_path` | string | 专利原文 |
| `list[].patent_exclusivity[].appl_product_no` | string | 标识 |
| `list[].patent_exclusivity[].exclusive_code` | string | 独占权代码 |
| `list[].patent_exclusivity[].exclusive_date` | string | 失效日期 |
| `list[].pareiv_detail[].specification` | string | 规格 |
| `list[].pareiv_detail[].dosage_form` | string | 剂型 |
| `list[].pareiv_detail[].date_of_submission` | string | 提交日 |
| `list[].pareiv_detail[].number_of_andas_submitted` | string | ANDA申请数量 |
| `list[].pareiv_detail[].day_status` | string | 180天独占期决定状态 |
| `list[].pareiv_detail[].day_decision_posting_date` | string | 180天独占期决定发布日 |
| `list[].pareiv_detail[].date_of_first_applicant_approval` | string | 首个申请批准时间 |
| `list[].pareiv_detail[].date_of_first_commercial_marketing_by_ftf` | string | 第一个申请人首次上市时间 |
| `list[].pareiv_detail[].expiration_date_of_last_qualifying_patent` | string | 最后一个专利到期时间 |
| `total` | integer |  |

---

## GlobalDrugDevAllTimeline

**Path:** `POST /pharma/general/v1/global_drug_dev/all/timeline`

**Description:** 全球药物研发库-全部上市事件

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].date` | string | 上市时间 |
| `list[].country` | string | 上市国家 |
| `list[].tag` | string | 首次上市标记 |
| `list[].indication` | array | 适应症 |
| `list[].company` | array | 公司名称 |
| `total` | integer |  |

---

## GlobalDrugDevBaseInfo

**Path:** `POST /pharma/general/v1/global_drug_dev/baseinfo`

**Description:** 全球药物研发库-基础信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `drug_name` | string | 药品名称 |
| `drug_name_cn` | string | 药品名称(中文) |
| `code_name` | array | 研发代码 |
| `trade_name` | array | 商品名 |
| `trade_name_cn` | array | 商品名(中文) |
| `active_ingredient` | array | 别名 |
| `drug_type` | string | 创新类型 |
| `type_code[].content` | string |  |
| `type_code[].code` | array |  |
| `highest_status_cn` | string | 全球最高研发阶段 |
| `highest_status_china_cn` | string | 中国最高研发阶段 |
| `target_json[].name_full` | string | 全称 |
| `target_json[].name_short` | string | 简称 |
| `target_json[].name_cn` | string | 中文 |
| `target_json[].alias` | array | 别名 |
| `target_action` | array | 作用机制 |
| `target_action_cn` | array | 作用机制(中文) |
| `active_indication[].cn` | string | 中文名称 |
| `inactive_indication[].cn` | string | 中文名称 |
| `therapy_area` | array | 治疗领域 |
| `therapy_area_cn` | array | 治疗领域(中文) |
| `technologies` | array | 工艺技术 |
| `technologies_cn` | array | 工艺技术(中文) |
| `dosage_form` | array | 剂型 |
| `delivery_route` | array | 给药途径 |
| `atc_shaixuan` | array | ATC分类 |
| `patent` | array | 专利号 |
| `ephmra_codes` | array | EphMRA分类号 |
| `ephmra_codes_cn` | array | EphMRA分类号(中文) |

---

## GlobalDrugDevBioSequence

**Path:** `POST /pharma/general/v1/global_drug_dev/bio/sequence/info`

**Description:** 全球药物研发库-生物序列信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `inn` | string | INN |
| `molecular_formula` | string | 分子式 |
| `cas_number` | string | CAS号 |
| `imgt_definition` | array | 定义 |
| `chains[].chain_id` | string | 序列链id |
| `chains[].chain_length` | string | 序列链长度 |
| `chains[].chain_sequence` | string | 生物序列 |

---

## GlobalDrugDevChemical

**Path:** `POST /pharma/general/v1/global_drug_dev/chemical/info`

**Description:** 全球药物研发库-化学结构信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `chemical_name` | string | 化学名称 |
| `molecular_formula` | string | 分子式 |
| `molecular_weight` | string | 分子量 |
| `cas_number` | string | CAS号 |
| `picture_number_link` | string | 结构图 |

---

## GlobalDrugDevClinicalResult

**Path:** `POST /pharma/general/v1/global_drug_dev/clinical/result`

**Description:** 全球药物研发库-临床试验结果

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name` | array | 药品名称 |
| `list[].registration_number` | string | 试验登记号 |
| `list[].phase` | string | 试验阶段 |
| `list[].indication` | array | 适应症 |
| `list[].intervention_info` | array | 干预信息 |
| `list[].representative_data` | string | 代表数据 |
| `list[].abstract` | array | 结果摘要 |
| `list[].result_tendency` | string | 结果倾向 |
| `list[].conclusion` | array | 结论 |
| `list[].reference` | string | 来源 |
| `list[].title` | string | 标题 |
| `list[].doi_url` | string | 文献链接 |
| `list[].other_url` | string | 相关链接 |
| `list[].date` | string | 结果发布时间 |
| `total` | integer |  |

---

## GlobalDrugDevCompany

**Path:** `POST /pharma/general/v1/global_drug_dev/company/info`

**Description:** 全球药物研发库-研发企业

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `originator_company.cn` | string |  |
| `originator_company.en` | string |  |
| `originator_company.code` | array |  |
| `active_companies[].cn` | string |  |
| `active_companies[].en` | string |  |
| `active_companies[].code` | array |  |

---

## GlobalDrugDevImportantTimeline

**Path:** `POST /pharma/general/v1/global_drug_dev/important/timeline`

**Description:** 全球药物研发库-重要上市事件

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].date` | string | 上市时间 |
| `list[].country` | string | 上市国家 |
| `list[].tag` | string | 首次上市标记 |
| `list[].indication` | array | 适应症 |
| `list[].company` | array | 公司名称 |
| `total` | integer |  |

---

## GlobalDrugDevIndicationCurrent

**Path:** `POST /pharma/general/v1/global_drug_dev/indication/current/status`

**Description:** 全球药物研发库-适应症研发现状

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].company.cn` | string |  |
| `list[].company.en` | string |  |
| `list[].country.cn` | string |  |
| `list[].country.en` | string |  |
| `list[].date` | string | 研发日期 |
| `list[].indication.cn` | string |  |
| `list[].indication.en` | string |  |
| `list[].status.cn` | string |  |
| `list[].status.en` | string |  |
| `total` | integer |  |

---

## GlobalDrugDevIndicationHistory

**Path:** `POST /pharma/general/v1/global_drug_dev/indication/history/status`

**Description:** 全球药物研发库-适应症研发历史

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].company.cn` | string |  |
| `list[].company.en` | string |  |
| `list[].country.cn` | string |  |
| `list[].country.en` | string |  |
| `list[].date` | string | 研发日期 |
| `list[].indication.cn` | string |  |
| `list[].indication.en` | string |  |
| `list[].status.cn` | string |  |
| `list[].status.en` | string |  |
| `total` | integer |  |

---

## GlobalDrugDevList

**Path:** `POST /pharma/general/v1/global_drug_dev/list`

**Description:** 全球药物研发库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.target` | string | no | 靶点,比如：GNRHR |
| `search.company` | string | no | 研发企业（含首家） |
| `search.indication` | string | no | 适应症,比如：高血压 |
| `search.highest_status_cn` | string | no | 全球最高研发阶段，可取值：批准上市、申请上市、Ⅲ期临床、Ⅱ期临床、Ⅰ期临床、临床、申报临床、临床前、药物发现、对外授权、撤市、拒绝上市申请、无后续进展报道、研究暂停、研究终止 |
| `search.highest_status_china_cn` | string | no | 中国最高研发阶段，可取值：批准上市、申请上市、Ⅲ期临床、Ⅱ期临床、Ⅰ期临床、临床、申报临床、临床前、药物发现、对外授权、撤市、拒绝上市申请、无后续进展报道、研究暂停、研究终止、国内未研发 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].keyid` | string | keyid |
| `list[].drug_name` | string | 药品名称 |
| `list[].drug_name_cn` | string | 药品名称中文 |
| `list[].originator_company` | string | 首家研发企业 |
| `list[].originator_company_cn` | string | 首家研发企业（中文） |
| `list[].active_companies` | array | 研发企业 |
| `list[].active_companies_cn` | array | 研发企业中文 |
| `list[].indication` | array | 适应症 |
| `list[].target_short` | array | 靶点 |
| `list[].highest_status_cn` | string | 全球最高研发阶段 |
| `list[].highest_status_china_cn` | string | 中国最高研发阶段 |
| `total` | integer |  |

---

## GlobalDrugDevSales

**Path:** `POST /pharma/general/v1/global_drug_dev/sales/info`

**Description:** 全球药物研发库-全球销售额

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].company` | string | 企业名称 |
| `list[].year` | string | 年份 |
| `list[].sales` | string | 销售额 |
| `list[].is_estimate` | string | 是否为推测值 |
| `total` | integer |  |

---

## GlobalDrugDevSpecApprovals

**Path:** `POST /pharma/general/v1/global_drug_dev/special_approvals/info`

**Description:** 全球药物研发库-特殊审批

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyid` | string | no | keyid(必传)，必须从‘全球药物研发库-列表信息’接口获取 *** 必须从GeneralV1_GlobalDrugDevList中获取 *** |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].regulatory_designations_cn` | string | 特殊审批 |
| `list[].country_cn` | string | 获得国家/地区 |
| `list[].indication.cn` | string |  |
| `list[].indication.en` | string |  |
| `list[].company.cn` | string |  |
| `list[].company.en` | string |  |
| `list[].date` | string | 日期 |
| `total` | integer |  |

---

## GlobalPharmaceuticalPatentList

**Path:** `POST /pharma/general/v1/global_pharmaceutical_patent/list`

**Description:** 全球医药专利-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.patent_number` | string | no | 专利文献号 |
| `search.title` | string | no | 题目 |
| `search.patent_family` | string | no | 同族专利 |
| `search.inventor_abstract` | string | no | 技术关键词 |
| `search.owner_companies` | string | no | 专利权人 |
| `search.inventors` | string | no | 发明人 |
| `search.drug_name` | string | no | 药品名称 |
| `search.indication` | string | no | 适应症 |
| `search.target` | string | no | 靶点 |
| `search.application_date.max` | string | no |  |
| `search.application_date.min` | string | no |  |
| `search.first_publication_date.max` | string | no |  |
| `search.first_publication_date.min` | string | no |  |
| `search.first_priority_date.max` | string | no |  |
| `search.first_priority_date.min` | string | no |  |
| `search.first_priority_number` | string | no | 最早优先权号 |
| `search.patent_type_cn` | array | no | 专利类型，可取值：产品、产品（高分子）、产品衍生、配方、工艺流程、联合用药、生物疗法、药物发现与筛选、基因筛选与组合、诊断、分析和测定、新用途、给药装置、非药物疗法、数字健康、使能技术、多肽技术、核苷酸和基因技术 |
| `search.organization` | array | no | 专利公开号所属地，可取值：中国、世界知识产权组织、日本、美国、韩国、欧洲、印度、俄罗斯、德国、中国台湾、英国、澳大利亚、西班牙、法国、前苏联、巴西、乌克兰、加拿大、墨西哥、波兰、意大利、捷克和斯洛伐克共和国、东德、阿根廷、罗马尼亚、菲律宾、南非、匈牙利、欧洲专利局、印度尼西亚、捷克、荷兰、土耳其、越南、中国香港、保加利亚、白俄罗斯、以色列、瑞士、哈萨克斯坦、瑞典、奥地利、马来西亚、摩尔多瓦、泰国、新加坡、比利时、卢森堡、丹麦、哥伦比亚、南斯拉夫、乌兹别克斯坦、希腊、葡萄牙、厄瓜多尔、新西兰、芬兰、乌拉圭、爱尔兰、欧亚专利局、斯洛伐克、古巴、克罗地亚、格鲁吉亚、挪威、海湾地区阿拉伯国家合作委员会专利局、秘鲁、塞尔维亚共和国、摩洛哥、多米尼加共和国、拉脱维亚、埃及、斯洛文尼亚、立陶宛、智利、吉尔吉斯斯坦、突尼斯、哥斯达黎加、亚美尼亚、约旦、危地马拉、蒙古、非洲知识产权组织、塔吉克斯坦、摩纳哥、海湾阿拉伯国家合作委员会专利局、赞比亚、洪都拉斯、巴拿马、非洲地区工业产权组织、塞浦路斯、塞尔维亚、阿尔及利亚、津巴布韦、萨尔瓦多、马拉维、非洲地区知识产权组织、爱沙尼亚、沙特阿拉伯、尼加拉瓜、圣马力诺、冰岛、前南斯拉夫、肯尼亚、马其他、黑山共和国、波斯尼亚和黑塞哥维那 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].patent_number` | string | 公开号 |
| `list[].title` | string | 题目 |
| `list[].owner_companies` | string | 专利权人 |
| `list[].indication_cn` | string | 适应症 |
| `list[].application_date` | string | 申请日 |
| `list[].first_publication_date` | string | 首次公开日期 |
| `list[].patent_type_cn` | string | 专利类型 |
| `total` | integer |  |

---

## HospitalSalesList

**Path:** `POST /pharma/general/v1/hospital_sales/list`

**Description:** 医院销售数据-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.keyword` | string | no | 通用名 |
| `search.active_ingredient` | string | no | 活性成分 |
| `search.manufacturer` | string | no | 企业名称 |
| `search.target` | string | no | 靶点 |
| `search.specification` | string | no | 规格 |
| `search.dosage_form` | string | no | 剂型 |
| `search.delivery_route` | string | no | 给药途径 |
| `search.indication` | string | no | 品种获批适应症 |
| `search.drug_type` | string | no | 药品类型 |
| `search.therapy_area` | string | no | 治疗领域 |
| `search.year` | string | no | 年份 |
| `search.quarter` | string | no | 季度 |
| `search.yizhixing_tongguo` | string | no | 是否通过一致性评价 |
| `search.number_of_manufacturers` | string | no | 品种过评厂家数 |
| `search.bool_exclusivity` | string | no | 是否独家 |
| `search.formulation_type` | string | no | 单方/复方 |
| `search.level` | string | no | 集采批次 |
| `search.drug_jicai` | string | no | 国家集采品种 |
| `search.medical_insurance_type` | string | no | 医保分类 |
| `search.essential_yes_no` | string | no | 2018版基药 |
| `search.traditional_yes_no` | string | no | 中药保护品种 |
| `search.varieties_289` | string | no | 289品种 |
| `search.otc_type` | string | no | OTC/处方药 |
| `search.double_span_yes_no` | string | no | 是否双跨 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].keyid` | string | 唯一标识 |
| `list[].year` | string | 年份 |
| `list[].quarter` | string | 季度 |
| `list[].drug_name` | string | 药品名称 |
| `list[].keyword` | string | 通用名 |
| `list[].specification` | string | 规格 |
| `list[].dosage_form` | string | 剂型 |
| `list[].active_ingredient_cn` | string | 活性成分 |
| `list[].manufacturer` | string | MAH/生产企业 |
| `list[].money` | string | 销售额（元） |
| `list[].number` | string | 销售量 |
| `list[].int_pack_size` | string | 转换系数 |
| `list[].corporation` | string | 集团/公司 |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `list[].indication` | string | 品种获批适应症 |
| `list[].target` | string | 靶点 |
| `list[].drug_type` | string | 药品类型 |
| `list[].type_shaixuan` | array | 药物类型 |
| `list[].atc1` | array | ATC大类 |
| `list[].atc2` | array | ATC亚类 |
| `list[].atc3` | array | ATC子类 |
| `list[].atc4` | array | ATC小类 |
| `list[].delivery_route` | string | 给药途径 |
| `list[].yizhixing_tongguo` | string | 是否通过一致性评价 |
| `list[].number_of_manufacturers` | string | 品种过评厂家数 |
| `list[].bool_exclusivity` | string | 是否独家 |
| `list[].formulation_type` | string | 单方/复方 |
| `list[].level` | array | 集采批次 |
| `list[].drug_jicai` | array | 国家集采品种 |
| `list[].medical_insurance_type` | array | 医保分类 |
| `list[].essential_yes_no` | string | 2018版基药 |
| `list[].traditional_yes_no` | string | 中药保护品种 |
| `list[].varieties_289` | string | 289品种 |
| `list[].otc_type` | string | OTC/处方药 |
| `list[].double_span_yes_no` | string | 是否双跨 |
| `list[].manufacturer_location_code` | array | 企业所在地 |
| `total` | integer |  |

---

## MedicalInsuranceList

**Path:** `POST /pharma/general/v1/medical_insurance/list`

**Description:** 医保目录库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.number` | string | no | 医保编号 |
| `search.drug_classification` | string | no | 药品分类（功能） |
| `search.medical_insurance_type` | array | no | 医保类别，可取值：甲类，乙类，民族药 |
| `search.area` | array | no | 医保地区，可取值：国家医保、安徽省、北京市、福建省、甘肃省、广东省、广西省、贵州省、海南省、河北省、河南省、黑龙江省、湖北省、湖南省、吉林省、江苏省、江西省、辽宁省、内蒙古、宁夏、青海省、山东省、山西省、陕西省、上海市、四川省、天津市、西藏、新疆、云南省、浙江省、重庆市 |
| `search.year` | array | no | 年份，可取值：2024年、2023年、2022年、2021年、2020年、2019年、2017年、2009年 |
| `search.additions` | array | no | 增补情况，可取值：国家医保品种、地方增补品种、谈判品种、谈判品种-竞价、国家医保调出品种、地方调出品种 |
| `search.status` | string | no | 执行状态，可取值：待执行、执行中、已废止 |
| `search.type` | array | no | 药品类型，可取值：化学药、生物制品、中成药、中药饮片 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name` | string | 药品名称 |
| `list[].drug_name_standard` | string | 规范名称 |
| `list[].type` | string | 药品类型 |
| `list[].inn` | string | 通用名 |
| `list[].dosage_form` | string | 医保目录剂型 |
| `list[].registered_dosage_form` | string | 注册剂型 |
| `list[].medical_insurance_type` | string | 医保类别 |
| `list[].number` | string | 医保编号 |
| `list[].drug_classification` | string | 药品类型（功能） |
| `list[].area` | string | 区域 |
| `list[].additions` | string | 增补情况 |
| `list[].edition` | string | 医保版本 |
| `list[].execution_date` | string | 执行时间 |
| `list[].expiry_date` | string | 到期时间 |
| `list[].status` | string | 执行状态 |
| `list[].year` | string | 年份 |
| `list[].limit` | string | 限制使用范围 |
| `list[].adjusted_payment` | string | 调整后限定支付范围 |
| `list[].original_payment` | string | 原限定支付标准 |
| `list[].source` | string | 文件 |
| `total` | integer |  |

---

## MedicalInsuranceNumberList

**Path:** `POST /pharma/general/v1/medical_insurance_number/list`

**Description:** 医保药品分类和代码库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 注册名称 |
| `search.drug_name_1` | string | no | 药品名称 |
| `search.trade_name` | string | no | 商品名 |
| `search.approval_number` | string | no | 批准文号 |
| `search.manufacturer` | string | no | 药品企业 |
| `search.native_code` | string | no | 药品本位码 |
| `search.drug_code` | string | no | 药品代码 |
| `search.registration_specifications_1` | string | no | 包装材质 |
| `search.type` | string | no | 医保类型，可取值：甲类、乙类 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_code` | string | 药品代码 |
| `list[].drug_name` | string | 注册名称 |
| `list[].drug_name_1` | string | 药品名称 |
| `list[].drug_classification` | string | 药品分类（功能） |
| `list[].native_code` | string | 药品本位码 |
| `list[].manufacturer` | string | 药品企业 |
| `list[].trade_name` | string | 商品名 |
| `list[].registered_dosage_form` | string | 注册剂型 |
| `list[].dosage_form_standard` | string | 剂型（标准） |
| `list[].registration_specifications` | string | 注册规格 |
| `list[].specifications` | string | 规格（标准） |
| `list[].registration_specifications_1` | string | 包装材质 |
| `list[].minimum_package_quantity` | string | 最小包装数量 |
| `list[].minimum_preparation_unit` | string | 最小制剂单位 |
| `list[].minimum_packing_unit` | string | 最小包装单位 |
| `list[].approval_number` | string | 批准文号 |
| `list[].approval_number_old` | string | 批准文号（原） |
| `list[].type` | string | 医保类型 |
| `list[].dosage_form` | string | 剂型 |
| `list[].number` | string | 编号 |
| `list[].note` | string | 备注 |
| `total` | integer |  |

---

## NewsInformationList

**Path:** `POST /pharma/general/v1/news_information/list`

**Description:** 新闻资讯-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.title` | string | no | 标题 |
| `search.drug_name` | string | no | 药品名称 |
| `search.target` | string | no | 靶点 |
| `search.company` | string | no | 企业名称 |
| `search.indication` | string | no | 适应症 |
| `search.news_type` | string | no | 资讯类型 |
| `search.date.max` | string | no |  |
| `search.date.min` | string | no |  |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].title_ori` | string | 原始标题 |
| `list[].news_type` | array | 类型 |
| `list[].published_date` | string | 报道日期 |
| `list[].source.source` | string | 数据源 |
| `list[].source.url` | string | 链接 |
| `list[].title` | string | AI标题 |
| `list[].abstract` | string | AI摘要 |
| `list[].drug_name[].drug_name` | string | 药品名称 |
| `list[].drug_name[].drug_ori` | string | 药品原文 |
| `list[].company[].company_name` | string | 企业名称 |
| `list[].company[].company_ori` | string | 企业原文 |
| `list[].indication[].indication_name` | string | 适应症名称 |
| `list[].indication[].indication_ori` | string | 适应症原文 |
| `list[].target[].target_name` | string | 靶点名称 |
| `list[].target[].target_ori` | string | 靶点原文 |
| `list[].content` | string | 正文 |
| `total` | integer |  |

---

## OnlineDrugstoreSalesFastList

**Path:** `POST /pharma/general/v1/online_drugstore_sales/list`

**Description:** 网上药店销售数据-列表

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称 |
| `search.keyword` | string | no | 通用名 |
| `search.active_ingredient` | string | no | 活性成分 |
| `search.manufacturer` | string | no | 企业名称 |
| `search.target` | string | no | 靶点 |
| `search.dosage_form` | string | no | 剂型 |
| `search.delivery_route` | string | no | 给药途径 |
| `search.indication` | string | no | 品种获批适应症 |
| `search.drug_type` | string | no | 药品类型 |
| `search.therapy_area_cn` | string | no | 治疗领域 |
| `search.year` | string | no | 年份 |
| `search.quarter` | string | no | 季度 |
| `search.number_of_manufacturers` | string | no | 品种过评厂家数 |
| `search.bool_exclusivity` | string | no | 是否独家 |
| `search.formulation_type` | string | no | 单方/复方 |
| `search.drug_jicai` | string | no | 国家集采品种 |
| `search.medical_insurance_type` | string | no | 医保分类 |
| `search.essential_yes_no` | string | no | 2018版基药 |
| `search.traditional_yes_no` | string | no | 中药保护品种 |
| `search.varieties_289` | string | no | 289品种 |
| `search.otc_type` | string | no | OTC/处方药 |
| `search.double_span_yes_no` | string | no | 是否双跨 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].year` | string | 年份 |
| `list[].quarter` | string | 季度 |
| `list[].drug_name` | string | 药品名称 |
| `list[].keyword` | string | 通用名 |
| `list[].dosage_form` | string | 剂型 |
| `list[].active_ingredient_cn` | string | 活性成分 |
| `list[].manufacturer` | string | MAH/生产企业 |
| `list[].money` | string | 销售额（元） |
| `list[].corporation` | string | 集团/公司 |
| `list[].atc_shaixuan` | array | ATC分类 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `list[].indication` | string | 品种获批适应症 |
| `list[].target` | string | 靶点 |
| `list[].drug_type` | string | 药品类型 |
| `list[].type_shaixuan` | array | 药物类型 |
| `list[].delivery_route` | string | 给药途径 |
| `list[].number_of_manufacturers` | string | 品种过评厂家数 |
| `list[].bool_exclusivity` | string | 是否独家 |
| `list[].formulation_type` | string | 单方/复方 |
| `list[].drug_jicai` | array | 国家集采品种 |
| `list[].medical_insurance_type` | array | 医保分类 |
| `list[].essential_yes_no` | string | 2018版基药 |
| `list[].traditional_yes_no` | string | 中药保护品种 |
| `list[].varieties_289` | string | 289品种 |
| `list[].otc_type` | string | OTC/处方药 |
| `list[].double_span_yes_no` | string | 是否双跨 |
| `list[].manufacturer_location_code` | array | 企业所在地 |
| `list[].key_id` | string | keyid |
| `total` | integer |  |

---

## PoliciesRegulations

**Path:** `POST /pharma/general/v1/policies_regulations/list`

**Description:** 政策法规库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.title` | string | no | 法规标题 |
| `search.release_department` | string | no | 颁发部门 |
| `search.release_date.max` | string | no |  |
| `search.release_date.min` | string | no |  |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].title` | string | 法规标题 |
| `list[].number` | string | 发文字号 |
| `list[].release_date` | string | 发布日期 |
| `list[].start_date` | string | 实施日期 |
| `list[].release_department` | array | 颁发部门 |
| `list[].type` | string | 信息分类 |
| `list[].validity_period` | string | 时效性 |
| `list[].zone` | string | 有效地区 |
| `list[].abstract` | string | 全文 |
| `list[].enclosure[].name` | string |  |
| `list[].enclosure[].path` | string |  |
| `total` | integer |  |

---

## TcmRecipeDetail

**Path:** `POST /pharma/general/v1/tcm_recipe/detail`

**Description:** 方药成分药理-方剂详情信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | string | no | id(必传)，必须从‘方药成分药理-方剂列表信息’接口获取 *** 必须从GeneralV1_TcmRecipeList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `recipe_name` | string | 方剂名称 |
| `classical_recipe` | string | 经典名方 |
| `recipe_type` | string | 处方类型 |
| `recipe_name_1` | string | 异名 |
| `recipe_reference` | string | 出处 |
| `recipe_class` | string | 功效分类 |
| `indications_class` | string | 主治病证分类 |
| `recipe_composition` | string | 处方组成 |
| `recipe_preparation` | string | 制法 |
| `usage_dosage` | string | 用法 |
| `function` | string | 功用 |
| `indications` | string | 主治 |
| `cautions` | string | 宜忌 |
| `add_subtract` | string | 加减 |
| `resolve` | string | 方解 |
| `appendices_recipe` | string | 附方 |
| `selection_of_theories` | string | 方论选录 |
| `clinical_example` | string | 临证举例 |
| `modern_research` | string | 现代研究 |
| `note` | string | 备考 |
| `remarks` | string | 备注 |

---

## TcmRecipeList

**Path:** `POST /pharma/general/v1/tcm_recipe/list`

**Description:** 方药成分药理-方剂列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.recipe_name` | string | no | 方剂名称 |
| `search.recipe_reference` | string | no | 出处 |
| `search.organisms_number.max` | integer | no |  |
| `search.organisms_number.min` | integer | no |  |
| `search.recipe_composition` | string | no | 处方组成 |
| `search.function` | string | no | 功用主治 |
| `search.recipe_class` | array | no | 功效分类，可取值：解表方、泻下方、和解方、清热方、祛暑方、温里方、补益方、固涩方、安神方、开窍方、理气方、理血方、治风方、治燥方、祛湿方、祛痰方、消食方、驱虫方、涌吐方、痈疡方 |
| `search.indications` | array | no | 主治病证，可取值：内科病证、妇科病证、儿科病证、眼科病证、耳鼻喉科、口腔科病证、外科病证、皮肤科病证、伤科病证 |
| `search.classical_recipe` | string | no | 经典名方，可取值：是、否 |
| `search.recipe_type` | string | no | 处方类型，可取值：古代方剂、近现代处方 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].id` | string | id |
| `list[].recipe_name` | string | 方名 |
| `list[].recipe_reference` | string | 出处 |
| `list[].recipe_class` | string | 功效分类 |
| `list[].recipe_composition` | string | 处方组成 |
| `list[].recipe_preparation` | string | 制法 |
| `list[].function` | string | 功用 |
| `list[].indications` | string | 主治 |
| `list[].related_organisms_count` | integer | 组成药味 |
| `list[].classical_recipe` | string | 经典名方 |
| `list[].recipe_type` | string | 方剂类型 |
| `total` | integer |  |

---

## TcmResourceInfoDetail

**Path:** `POST /pharma/general/v1/tcm_resource_info/detail`

**Description:** 中药材资源信息-详情信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `id` | string | no | id(必传)，必须从‘中药材资源信息-列表信息’接口获取 *** 必须从GeneralV1_TcmResourceInfoList中获取 *** |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `chinese_name` | string | 中药材名称 |
| `chinese_name_alia` | string | 中药别名 |
| `medicine_suorces` | string | 中药来源 |
| `organisms_class` | string | 药材分类 |
| `properties_meridians` | string | 性味归经 |
| `function` | string | 功能主治 |
| `bool_multisources` | string | 是否为多基原药材 |
| `sources_organisms_latin` | string | 来源生物拉丁名 |
| `plant_picture[].content` | string |  |
| `plant_picture[].title` | string |  |
| `sources_morphology[].content` | array |  |
| `sources_morphology[].title` | string |  |
| `sources_resource[].content` | array |  |
| `sources_resource[].title` | string |  |
| `origin_textual_research` | array | 品种考证 |
| `locality_textual_research` | array | 产地考证 |
| `quality_textual_research` | array | 品质考证 |
| `collection_time` | string | 采收加工 |
| `medicine_processing` | string | 炮制加工 |
| `planting_breed` | string | 人工栽培（养殖）品种 |
| `locality_growth` | string | 产地分布 |
| `genuine_producing_area` | string | 道地产区 |
| `growth_cycle` | string | 生长周期 |
| `demand` | string | 年需求量 |
| `growth_habit` | string | 生物学特性 |
| `planting_technology` | string | 种植技术 |
| `production_specification[].name` | string |  |
| `production_specification[].url` | string |  |
| `gap_base[].approve_date` | string |  |
| `gap_base[].company` | string |  |
| `gap_base[].plant_area` | string |  |
| `gap_base[].plant_species` | string |  |
| `gap_base[].region` | string |  |
| `appearance` | string | 药材性状 |
| `specifications` | array | 其他鉴定方法 |
| `adulterant` | string | 易混淆品种 |
| `goods_specification[].content` | string |  |
| `goods_specification[].name` | string |  |
| `pictures[].legend` | string |  |
| `pictures[].url` | string |  |
| `terminology[].cn` | string |  |
| `terminology[].content` | string |  |
| `terminology[].en` | string |  |
| `terminology[].number` | string |  |
| `endangered_category` | string | 野生动植物濒危等级 |
| `special_value[].content` | array |  |
| `special_value[].title` | string |  |
| `toxicology` | string | 药材毒性 |
| `homologous` | string | 药食同源情况 |
| `storage` | string | 贮藏 |

---

## TcmResourceInfoList

**Path:** `POST /pharma/general/v1/tcm_resource_info/list`

**Description:** 中药材资源信息-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.all` | string | no | 综合检索 |
| `search.chinese_name` | string | no | 中药材名称 |
| `search.medicine_suorces` | string | no | 中药来源 |
| `search.sources_organisms_latin` | string | no | 来源生物拉丁名 |
| `search.function` | string | no | 功能主治 |
| `search.organisms_class` | array | no | 药材分类，可取值：全草类、根及根茎类、果实及种子类、动物类、茎木类、花类、叶类、矿物类、皮类、其他类、菌藻类、树脂类 |
| `search.toxicology_1` | array | no | 药材毒性，可取值：无、有毒、有小毒、有大毒 |
| `search.bool_multisources` | string | no | 是否为多基原药材，可取值：是、否 |
| `search.bool_planting` | string | no | 是否为人工栽培（养殖）品种，可取值：是、否 |
| `search.bool_gap` | string | no | 是否有GAP基地，可取值：是、否 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].chinese_name` | string | 中药材名称 |
| `list[].medicine_suorces` | string | 中药来源 |
| `list[].organisms_class` | string | 药材分类 |
| `list[].properties_meridians` | string | 性味归经 |
| `list[].function` | string | 功能主治 |
| `list[].id` | string | id |
| `total` | integer |  |

---

## TradeBarCodeList

**Path:** `POST /pharma/general/v1/trade_bar_code/list`

**Description:** 商品条码-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.approval_number` | string | no | 批准文号 |
| `search.company` | string | no | 企业名称 |
| `search.drug_name` | string | no | 药品名称 |
| `search.specification` | string | no | 规格 |
| `search.trade_code` | string | no | 商品条码（69码） |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].bar_code` | string | 条码图片 |
| `list[].package_pic` | array | 药品图片 |
| `list[].marketing_date` | string | 上市日期 |
| `list[].content` | string | 净含量 |
| `list[].specification` | string | 规格 |
| `list[].class` | string | 产品分类 |
| `list[].status` | string | 条码状态 |
| `list[].trade` | string | 品牌名称 |
| `list[].drug_name` | string | 药品名称 |
| `list[].company` | string | 企业名称 |
| `list[].approval_number` | array | 批准文号 |
| `list[].trade_code` | string | 商品条码（69码） |
| `total` | integer |  |

---

## VarietyPatternList

**Path:** `POST /pharma/general/v1/variety_pattern/list`

**Description:** 品种格局-项目进度

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name` | string | no | 药品名称/成分词 |
| `search.company` | string | no | 企业名称 |
| `search.project_status_date.max` | string | no |  |
| `search.project_status_date.min` | string | no |  |
| `search.therapy_area_cn` | string | no | 治疗领域。可选值：呼吸系统、神经系统、免疫调节、感染、心血管系统、炎症、血液系统、皮肤病、泌尿生殖系统、内分泌与代谢、眼科、中毒/药物成瘾、肌肉骨骼系统、诊断、耳科、消化系统、杂类、未知 |
| `search.drug_type` | string | no | 药品类型。可选值：治疗用生物制品、预防用生物制品、中成药、体外诊断试剂、中药提取物、原料药、药用辅料、药械组合、药包材、医疗器械 |
| `search.project_status` | string | no | 项目进度。可选值：已获文号、申请上市、Ⅲ期临床、Ⅱ期临床、Ⅰ期临床、BE试验、批准临床、申报临床、未被批准 |
| `search.yizhixing_status` | string | no | 一致性评价状态。可选值：通过(含视同通过)、提交申请、未通过一致性评价 |
| `search.level` | string | no | 国家集采批次。可选值：4+7试点、4+7扩围、第二批集采、第三批集采、第四批集采、第五批集采、第六批集采（胰岛素专项）、第七批集采、第八批集采、第九批集采、第十批集采 |
| `page` | integer | no | 页码 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].drug_name_standard` | string | 药品名称 |
| `list[].active_ingredient` | string | 成分 |
| `list[].dosage_form_1` | string | 剂型 |
| `list[].project_company` | array | 企业名称 |
| `list[].project_status` | string | 项目进度 |
| `list[].project_status_date` | string | 当前项目进度日期 |
| `list[].indication` | array | 适应症 |
| `list[].therapy_area_cn` | array | 治疗领域 |
| `list[].drug_type_guifan` | string | 药品类型 |
| `list[].type_shaixuan` | array | 药物类型 |
| `list[].target_short` | array | 靶点 |
| `list[].formulation_type_single` | string | 单方/复方 |
| `list[].piwen_type` | string | 进口/国产 |
| `list[].acceptances_number_linchuang` | array | 申请临床（受理号） |
| `list[].undertake_date` | string | 首次临床申请时间 |
| `list[].registration_number` | array | 临床试验公示号（登记号） |
| `list[].first_public_date` | string | 首次临床公示时间 |
| `list[].acceptances_number_shangshi` | array | 申请上市（受理号） |
| `list[].approval_date` | string | 首次上市时间 |
| `list[].approval_number` | string | 已上市批准文号 |
| `list[].active_ingredient_status_china` | string | 成分中国最高进展 |
| `list[].active_ingredient_status` | string | 成分全球最高进展 |
| `list[].atc_1_cn` | string | ATC大类 |
| `list[].atc_2_cn` | string | ATC亚类 |
| `list[].manufacturer_number_china` | string | 同成分国内已上市厂家数量 |
| `total` | integer |  |

---

