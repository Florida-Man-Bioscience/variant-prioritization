# AI Implementation Log - Variant Prioritization System

## Plan for Task: Scoring Update, Batch VEP, and Placeholder Data

### 1. Refactor Scoring Logic (`main.py`)
*   **Goal:** Update `prioritize_variant()` to use a 400-point scale for ClinVar pathogenic and include a detailed `score_breakdown`.
*   **Action:** 
    *   Modify `prioritize_variant` to initialize and populate a `score_breakdown` dict.
    *   Adjust all scoring increments (e.g., 1000 -> 400, 500 -> 200, 100 -> 40, etc.).
    *   Update tier thresholds accordingly.
    *   Pass `score_breakdown` to `_build_result`.

### 2. Update UI with Guidance and Breakdown (`main.py`)
*   **Goal:** Show the score breakdown and plain-English guidance in `render_variant_card()`.
*   **Action:**
    *   Update the card label or body to display the breakdown.
    *   Implement conditional logic to show guidance text based on `variant["tier"]`.

### 3. Batch VEP API Calls (`main.py`)
*   **Goal:** Improve performance by batching VEP requests in groups of 200.
*   **Action:**
    *   Refactor `run_vep_api` to loop through variants in slices of 200.
    *   Format the batch request body according to Ensembl VEP API specs.
    *   Handle results and progress updates correctly for batches.

### 4. Setup Data Directory and Placeholder Files
*   **Goal:** Ensure filtering works by providing placeholder `pharma_rsids.txt` and `acmg81_rsids.txt`.
*   **Action:**
    *   Create `data/` directory if missing.
    *   Search for 5 relevant rsIDs for each category (e.g., ACMG 81, Pharmacogenomics).
    *   Write these rsIDs to their respective files.

---

## Progress Tracking
- [x] Task 1: Refactor Scoring Logic
- [x] Task 2: Update UI
- [x] Task 3: Batch VEP API Calls
- [x] Task 4: Setup Placeholder Data
