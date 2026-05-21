# Module Routing

Determine which module's directory to load based on the user's query intent. Each directory contains `api-list.md` (RPC names) and `api.swagger.json` (request parameters).

| Module | Domain | Trigger (EN) | Trigger (中文) | API List |
|---|---|---|---|---|
| pharma | Drug R&D, clinical trials, approvals, patents, insurance, sales, TCM, hospitals, pharmacies, bidding, FDA/EMA | drug, clinical trial, patent, FDA, EMA, insurance, hospital, pharmacy, TCM, approval | 药物、临床、专利、医保、医院、药店、中药、审批、招标 | [pharma/api-list.md](pharma/api-list.md) |
| tqsk | Chemical properties, spectra, crystal, synthesis, ADMET, SDS, literature, structure recognition | chemical, spectra, crystal, synthesis, ADMET, SDS, literature, SMILES | 化学、谱图、晶体、合成、反应、结构 | [tqsk/api-list.md](tqsk/api-list.md) |
| med | Drug interactions | drug interaction, DDI | 药物相互作用、配伍 | [med/api-list.md](med/api-list.md) |
| ebm | Disease knowledge | disease, condition | 疾病、病症 | [ebm/api-list.md](ebm/api-list.md) |
| instrument | Medical devices | medical device, instrument | 医疗器械、器械 | [instrument/api-list.md](instrument/api-list.md) |