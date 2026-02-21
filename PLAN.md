This is where we talk about our plan for this and what we want to implement.




TODOs:

- [ ] In main.py, find the prioritize_variant() function and change the line score += 1000 under the ClinVar pathogenic block to score += 400, then do the same pattern for each scoring block — create a dict called score_breakdown that stores what each component added (e.g. {"clinvar": 400, "consequence": 100, "frequency": 30}) and print it alongside the total score on each variant card
- [ ] In main.py, find the render_variant_card() function and add one line of plain-English guidance below the scoring reasons based on the tier — if Critical say "Consider discussing this finding with a genetic counselor", if High say "Worth reviewing with your healthcare provider", if Medium say "Monitor and mention at your next checkup", if Low say "No action needed based on current evidence"
- [ ] In main.py, replace the for loop in run_vep_api() that sends one variant at a time to Ensembl with a single POST request that sends all variants at once using the same endpoint — the Ensembl VEP API accepts a list under the key "variants" in the request body, so batch them in groups of 200 instead of one by one
- [ ] In main.py, find the sidebar filter checkboxes for Pharmacogenomics and ACMG 81 Genes — check whether the files they reference (pharma_rsids.txt, acmg81_rsids.txt) actually exist in the data/ folder, and if not, create placeholder files with 5 real example rsIDs each from a quick Google search so the filters actually work
