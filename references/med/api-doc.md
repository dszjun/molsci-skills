# med — API Reference

1 endpoints.

---

## DrugInteractionList

**Path:** `POST /med/general/v1/drug_interaction/list`

**Description:** 药物相互作用库-列表信息

### Request Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `search.drug_name_1` | string | no | 药物名称1 |
| `search.drug_name_2` | string | no | 药物名称2 |
| `page` | integer | no | 页码 默认每页10条 (必传) |

### Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `list[].type` | integer | 类别:1=药物-保健品,2=药物-食物,3=药物-药物 |
| `list[].sub_type` | integer | 子类别:1=不推荐合用,2=谨慎合用,3=禁忌合用,4=关注 |
| `list[].information` | array | 相互作用组合 |
| `list[].action_type` | string | 作用类型 |
| `list[].result` | string | 作用结果 |
| `list[].mechanism` | string | 作用机制 |
| `list[].deal_with` | string | 用药方案 |
| `list[].content` | string | 相互作用内容 |
| `list[].reference` | array | 参考文献 |
| `total` | integer |  |

---

