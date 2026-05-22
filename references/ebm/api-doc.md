# ebm — API Reference

1 endpoints.

---

## Diseases

**Path:** `POST /ebm/general/v1/disease/list`

**Description:** 疾病知识专题库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.disease_name_cn` | string | no | 疾病中文名称 |
| `search.disease_name` | string | no | 疾病英文名称 |
| `search.aliases` | array | no | 疾病英文名称别名 |
| `search.aliases_cn` | array | no | 疾病中文名称别名 |
| `search.omim_code` | string | no | omim_code编码 |
| `search.mesh_code` | string | no | mesh编码 |
| `search.do_code` | string | no | DO编码 |
| `search.icd11_code` | string | no | ICD-11编码 |
| `search.icd10_code` | string | no | ICD-10编码 |
| `search.icd9cm_code` | string | no | ICD-9编码 |
| `search.umls_code` | string | no | UMLS编码 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].object_id` | string |  |
| `list[].key_id` | string |  |
| `list[].disease_name` | string | 疾病中文名称 |
| `list[].disease_name_cn` | string | 疾病英文名称 |
| `list[].aliases` | array | 疾病英文别名 |
| `list[].aliases_cn` | array | 疾病中文别名 |
| `list[].disease_categories_global[].en` | string |  |
| `list[].disease_categories_global[].cn` | string |  |
| `list[].disease_categories_anatomical[].en` | string |  |
| `list[].disease_categories_anatomical[].cn` | string |  |
| `list[].omim_code` | string | omim编码 |
| `list[].mesh_code` | string |  |
| `list[].do_code` | array | DO编码 |
| `list[].icd11_code` | array | ICD-11编码 |
| `list[].icd10_code` | array | ICD-10编码 |
| `list[].icd9cm_code` | string | ICD-9编码 |
| `list[].snomed_ct_code` | array | SNOMED-CT编码 |
| `list[].umls_code` | array | UMLS编码 |
| `list[].summary_omim.en` | string | 英文 |
| `list[].summary_omim.cn` | string | 中文 |
| `list[].summary_gard.en` | string | 英文 |
| `list[].summary_gard.cn` | string | 中文 |
| `list[].summary_do.en` | string | 英文 |
| `list[].summary_do.cn` | string | 中文 |
| `list[].summary_uniprot.en` | string | 英文 |
| `list[].summary_uniprot.cn` | string | 中文 |
| `list[].summary_malacards.en` | string | 英文 |
| `list[].summary_malacards.cn` | string | 中文 |
| `list[].summary_medlineplus.en` | string | 英文 |
| `list[].summary_medlineplus.cn` | string | 中文 |
| `list[].related_genes_or_enhancers[].symbol` | string | 基因名称 |
| `list[].related_genes_or_enhancers[].description` | string | string	描述 |
| `list[].related_genes_or_enhancers[].category` | string | 分类 |
| `list[].genecards_pathways[].super_pathways` | string | 超级通路 |
| `list[].genecards_pathways[].top_affiliating_genes` | array | 顶级亲缘基因 |
| `list[].related_symptoms[].symptoms` | string |  |
| `list[].related_symptoms[].frequency` | string |  |
| `list[].related_symptoms[].hpo_code` | string |  |
| `list[].summary_table_incidence[].table_name` | string | 表名 |
| `list[].summary_table_prevalence[].table_name` | string |  |
| `list[].summary_table_other[].table_name` | string |  |
| `list[].pubmed_treatment` | string | pubmed治疗概述 |
| `list[].pubmed_treatment_cn` | string | pubmed治疗概述中文翻译 |
| `list[].cancer_treatment[].biomarker` | string |  |
| `list[].cancer_treatment[].alteration` | string |  |
| `list[].cancer_treatment[].cancer_type` | string |  |
| `list[].cancer_treatment[].therapy` | array |  |
| `list[].cancer_treatment[].evidence` | array |  |
| `list[].cancer_treatment[].comments` | string |  |
| `list[].drugs[].name` | string | 药物名称 |
| `list[].drugs[].name_cn` | string | 药物中文名 |
| `list[].drugs[].category` | array | 药理分类 |
| `list[].drugs[].indications` | string | 药物适应症 |
| `list[].ddx[].ddx` | array | 鉴别诊断 |
| `list[].ddx[].exhaustive_ddx` | array | 勿漏诊断 |
| `list[].ddx[].related_ddx` | array | 关联待查 |
| `total` | integer |  |

---

