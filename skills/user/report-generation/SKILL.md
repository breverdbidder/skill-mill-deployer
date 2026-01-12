# BidDeed.AI Report Generation

**Skill Type:** Output Formatting & Branding Standards  
**Scope:** Professional Report Creation for Foreclosure Auction Analysis  
**Last Updated:** 2026-01-13  
**Confidence:** HIGH (validated across 100+ generated reports)

---

## Purpose

This skill defines the complete standards for generating professional, branded foreclosure auction analysis reports. Use this skill when creating DOCX reports, formatting auction summaries, or ensuring consistency with BidDeed.AI brand identity.

---

## Critical Branding Rules

### NEVER Include

**Absolutely forbidden in BidDeed.AI reports:**
- ❌ Property360 (Mariam's real estate business)
- ❌ Protection Partners (Mariam's insurance business)
- ❌ Allstate Insurance
- ❌ Everest Capital of Brevard LLC (old business name)
- ❌ Mariam Shapira's name
- ❌ Any reference to insurance services
- ❌ Any reference to real estate brokerage services

**Why:** BidDeed.AI is Ariel's autonomous AI platform, completely separate from Mariam's businesses. Mixing brands dilutes positioning and creates confusion.

### ALWAYS Include

**Required BidDeed.AI branding:**
- ✅ BidDeed.AI (product name)
- ✅ Powered by The Everest Ascent™ (methodology)
- ✅ ForecastEngine™ predictions (when applicable)
- ✅ BidDeed.AI ML Prediction (XGBoost model outputs)
- ✅ Everest Capital USA (if company attribution needed)
- ✅ Ariel Shapira, Managing Member (if personal attribution needed)

---

## Report Format Specifications

### One-Page DOCX Standard

**Critical Constraint:** All auction analysis reports MUST fit on a single page.

**Why:** 
- Quick decision-making at auction
- Print-friendly for courthouse bidding
- Forces concise, high-value information only
- Professional presentation

**Page Setup:**
- Paper: Letter (8.5" × 11")
- Margins: 0.5" all sides (narrow)
- Orientation: Portrait
- Font: Arial (body), Arial Bold (headers)
- Line spacing: Single (1.0)

### Visual Hierarchy

**Header Section (Top):**
- Property address (16pt, Bold, Navy #1E3A5F)
- Auction date and case number (10pt, Regular, Gray #666666)
- BidDeed.AI logo/text (right-aligned, 12pt, Navy #1E3A5F)

**Recommendation Badge:**
- Position: Top-right, below BidDeed.AI branding
- Size: 40pt font for recommendation word
- Colors: BID=#E8F5E9 (green), REVIEW=#FFF3E0 (orange), SKIP=#FFEBEE (red)
- Border: 2pt solid, same color family as background

**Body Sections:**
- Property Details (compact table)
- Financial Analysis (max bid calculation shown)
- Lien Priority Summary (critical findings only)
- ForecastEngine™ Predictions (if applicable)
- Recommendation Justification (2-3 sentences max)

**Footer:**
- Disclaimer (8pt, Gray #999999)
- "Powered by The Everest Ascent™" (8pt, Navy #1E3A5F)
- Report generation date/time (8pt, Gray #999999)

---

## Color Palette (DOCX Theme)

### Primary Colors

**Navy (Header/Branding):** #1E3A5F
- Use: Headers, BidDeed.AI text, section dividers
- Font: White on navy background, or navy on white background

**Gray (Supporting Text):** #666666
- Use: Subheadings, metadata (case #, auction date)
- Font: Gray text on white background

**Light Gray (Borders/Lines):** #CCCCCC
- Use: Table borders, section separators
- Weight: 1pt for tables, 2pt for major dividers

### Recommendation Colors

**BID (Green Palette):**
- Background: #E8F5E9 (very light green)
- Text: #2E7D32 (dark green)
- Border: #4CAF50 (medium green)
- Meaning: Strong opportunity, recommend bidding

**REVIEW (Orange Palette):**
- Background: #FFF3E0 (very light orange)
- Text: #E65100 (dark orange)
- Border: #FF9800 (medium orange)
- Meaning: Marginal opportunity, requires closer analysis

**SKIP (Red Palette):**
- Background: #FFEBEE (very light red)
- Text: #C62828 (dark red)
- Border: #F44336 (medium red)
- Meaning: Insufficient margin, do not bid

### Special Context Colors (Optional)

**Shabbat Observance (Light Orange):** #FFF3E0
- Use: When auction falls on Shabbat, note in header
- Text: "Shabbat Conflict - Cannot Attend" in orange
- Important: Ariel cannot attend Friday sunset through Saturday evening auctions

**Ubrzati (Light Blue):** #E3F2FD
- Use: If property tagged for urgent action
- Rare, only for time-sensitive opportunities

**Gleason (Light Purple):** #F3E5F5
- Use: If property near Gleason Park (Michael's swim location)
- Personal interest tag for properties near 1233 Yacht Club Blvd

---

## Report Content Structure

### Section 1: Property Header

**Format:**
```
[Property Address]
123 Main Street, Satellite Beach, FL 32937

Case #: 2024CA012345 | Auction: December 3, 2025 | Judgment: $280,000
Plaintiff: U.S. Bank National Association
```

**Elements:**
- Address: 16pt Bold Navy
- Case/Auction/Judgment: 10pt Regular Gray, pipe-separated
- Plaintiff: 10pt Regular Gray, italics

### Section 2: Recommendation Badge

**Visual:**
```
┌─────────────────┐
│      BID        │ ← 40pt Bold
│   Max: $160K    │ ← 14pt Regular
│   Ratio: 75%    │ ← 12pt Regular
└─────────────────┘
```

**Colors:** Based on recommendation (green/orange/red)

**Content:**
- Recommendation word (BID/REVIEW/SKIP)
- Maximum bid amount
- Bid/judgment ratio percentage

### Section 3: Property Details (Table)

**Format: 2-column table, compact**

| Attribute | Value |
|-----------|-------|
| **Parcel ID** | 12-34-56-78-9000.0 |
| **Bedrooms** | 3 |
| **Bathrooms** | 2 |
| **Sq Ft** | 1,800 |
| **Year Built** | 1995 |
| **Assessed Value** | $350,000 |
| **ARV (Estimated)** | $400,000 |
| **Repairs (Est)** | $50,000 |

**Table Styling:**
- Font: 9pt Arial
- Header row: Bold, navy background, white text
- Borders: 1pt light gray
- Alternating row colors: White and very light gray (#F5F5F5)

**Photo Integration (if available):**
- BCPAO photo URL: https://www.bcpao.us/photos/{prefix}/{account}011.jpg
- Insert: Right-aligned, 2" wide, next to property details table
- Caption: "BCPAO Property Photo" (8pt gray)

### Section 4: Financial Analysis

**Max Bid Formula (displayed):**
```
Max Bid Calculation:
ARV ($400,000) × 70% = $280,000
Less: Repairs          -$50,000
Less: Hard Costs       -$10,000
Less: Risk Reserve     -$60,000  [MIN($25K, ARV×15%)]
─────────────────────────────────
Maximum Safe Bid:      $160,000

Judgment Amount:       $280,000
Bid/Judgment Ratio:    57%
```

**Formatting:**
- Monospace font (Courier New, 9pt) for alignment
- Bold for final max bid and ratio
- Color-code ratio: Green ≥75%, Orange 60-74%, Red <60%

**Threshold Reference:**
- ≥75%: BID (strong margin)
- 60-74%: REVIEW (marginal)
- <60%: SKIP (insufficient margin)

### Section 5: Lien Priority Summary

**Format: Bulleted list, critical findings only**

**Example:**
```
• Senior Lien: First Mortgage to U.S. Bank ($250,000)
• Junior Liens: Second Mortgage ($30,000) - WIPED OUT
• Tax Certificates: None outstanding (RealTDM verified)
• HOA Status: Not an HOA foreclosure
• Title Concerns: None identified
```

**Key Points to Include:**
- Senior lien(s) that survive foreclosure
- Junior lien(s) that get wiped out
- Tax certificate status (critical - senior to almost everything)
- HOA foreclosure risk (if applicable)
- Any title red flags

**Color Coding:**
- Green bullet: Good news (liens wiped out, clear title)
- Red bullet: Risk factor (senior mortgage survives HOA, title clouds)
- Orange bullet: Neutral or needs investigation

### Section 6: ForecastEngine™ Predictions

**When to Include:**
- If BidDeed.AI ML model has prediction
- If ForecastEngine™ accuracy ≥85% for this property type
- If prediction adds value to decision

**Format:**
```
ForecastEngine™ Analysis:
• Third-Party Purchase Probability: 68% (BidDeed.AI ML)
• Lien Priority Score: 97/100 (High Confidence)
• Exit Strategy Recommendation: Fix & Flip
```

**Branding:**
- ALWAYS say "BidDeed.AI ML" not "XGBoost" or technical model names
- Include accuracy score if ≥85%
- Show confidence level: High (≥90%), Medium (70-89%), Low (<70%)

### Section 7: Recommendation Justification

**Length:** 2-3 sentences maximum

**BID Example:**
```
RECOMMENDATION: BID
Strong opportunity with 75% bid/judgment ratio providing adequate margin.
Clean title with junior liens wiped out in foreclosure. Optimal location
(32937 Satellite Beach) supports Fix & Flip exit strategy with $50K+ profit potential.
```

**REVIEW Example:**
```
RECOMMENDATION: REVIEW
Marginal opportunity at 62% bid/judgment ratio. Requires closer due diligence
on repair estimates and ARV validation. Consider if competition is light.
```

**SKIP Example:**
```
RECOMMENDATION: SKIP
Insufficient margin at 57% bid/judgment ratio. High repair costs ($50K) and
uncertain ARV make this too risky. Multiple better opportunities in this auction.
```

**Tone:**
- Decisive and confident
- Data-driven (cite specific numbers)
- Risk-aware (acknowledge concerns)
- Action-oriented (clear next steps)

### Section 8: Footer

**Standard Footer:**
```
─────────────────────────────────────────────────────────────────
This analysis is provided for informational purposes only and does not constitute
legal, financial, or investment advice. Conduct independent due diligence before bidding.

Powered by The Everest Ascent™ | BidDeed.AI
Report generated: January 13, 2026 at 2:45 PM EST
```

**Font:** 8pt Arial
**Colors:** Gray #999999 for disclaimer, Navy #1E3A5F for BidDeed.AI
**Alignment:** Center-aligned

---

## Data Source Requirements

### Must Have Before Generating Report

**Property Data:**
- ✅ Address (verified in BECA or RealForeclose)
- ✅ Parcel ID (from BCPAO)
- ✅ Case number (from BECA)
- ✅ Judgment amount (from BECA)
- ✅ Auction date (from RealForeclose)
- ✅ Plaintiff name (from BECA)

**Financial Data:**
- ✅ ARV (After Repair Value - validated with comps)
- ✅ Repair estimate (itemized or conservative guess)
- ✅ Max bid calculation (formula applied)
- ✅ Bid/judgment ratio (calculated)

**Lien Data:**
- ✅ Lien priority analysis (from AcclaimWeb search)
- ✅ Tax certificate status (from RealTDM)
- ✅ HOA foreclosure check (plaintiff name analysis)

### Can Proceed Without (Mark as "Not Available")

**Optional Data:**
- Bedrooms/bathrooms (if not in BCPAO, note "Not available - commercial property")
- Year built (if missing, say "Not available")
- BCPAO photo (some properties don't have photos)
- ForecastEngine™ predictions (may not apply to all property types)

**How to Handle Missing Data:**
```
Bedrooms/Bathrooms: Not available (commercial property)
BCPAO Photo: Not available
```

**Never:**
- ❌ Guess at critical data (ARV, repairs, liens)
- ❌ Omit important disclaimers about missing data
- ❌ Generate report if ARV or lien priority unknown (too risky)

---

## Report Generation Workflow

### Step-by-Step Process

**1. Data Gathering (Stages 1-7 of Pipeline)**
- Collect all required data from sources
- Validate data completeness
- Flag any missing critical fields

**2. Data Validation**
- ARV supported by recent comps? (within 6 months, same zip)
- Repairs estimate reasonable? (not too optimistic)
- Lien search completed? (not guessed)
- All calculations correct? (double-check max bid formula)

**3. Template Selection**
- One-page DOCX (standard)
- Shabbat variant (if auction on Shabbat)
- Special context variant (if Ubrzati/Gleason tagged)

**4. Content Assembly**
- Populate all sections with validated data
- Apply appropriate color scheme (BID/REVIEW/SKIP)
- Insert BCPAO photo if available
- Format tables and calculations

**5. Quality Check**
- Fits on one page? (critical requirement)
- No Property360/Mariam references? (critical branding check)
- All numbers accurate? (verify calculations)
- Professional appearance? (no formatting errors)
- Proper color scheme? (matches recommendation)

**6. File Naming Convention**
```
Format: {address}_{case_number}_{date}.docx
Example: 123_Main_St_2024CA012345_2025-12-03.docx

Multi-property batch:
Format: {auction_date}_auction_reports.zip
Example: dec3_2025_auction_reports.zip
```

**7. Output Delivery**
- Save to: /mnt/user-data/outputs/
- NEVER create ZIP files - provide individual DOCX files
- Generate clickable download links
- Log to Supabase disposition tracking

---

## File Generation Implementation

### Primary Method: generate_brevard_reports.js

**Location:** Root of brevard-bidder-scraper repo

**Usage:**
```bash
node generate_brevard_reports.js --auction-date 2025-12-03
```

**Inputs:**
- Auction date (YYYY-MM-DD)
- Data source: Supabase multi_county_auctions table
- Filters: Only properties with complete data

**Outputs:**
- Individual DOCX files per property
- Saved to: reports/{auction_date}/
- Automatically uploaded to GitHub repo

**Features:**
- BCPAO photo integration (downloads and embeds)
- Automatic color scheme application
- One-page constraint enforcement (adjusts font sizes if needed)
- BidDeed.AI branding (no Property360 references)

### Alternative: Python-DOCX Library

**For programmatic generation:**
```python
from docx import Document
from docx.shared import Pt, RGBColor, Inches

def generate_report(property_data: dict) -> str:
    doc = Document()
    
    # Set margins
    sections = doc.sections
    for section in sections:
        section.top_margin = Inches(0.5)
        section.bottom_margin = Inches(0.5)
        section.left_margin = Inches(0.5)
        section.right_margin = Inches(0.5)
    
    # Add header
    header = doc.add_heading(property_data['address'], level=1)
    header.runs[0].font.color.rgb = RGBColor(30, 58, 95)  # Navy
    
    # ... rest of report generation
    
    doc.save(f"/mnt/user-data/outputs/{property_data['filename']}")
    return f"Report generated: {property_data['filename']}"
```

---

## Multi-Property Batch Reports

### When Creating Multiple Reports

**Scenario:** Auction with 10+ properties analyzed

**Process:**
1. Generate individual DOCX for each property
2. **NEVER create ZIP archives** - this violates zero user actions rule
3. Upload each DOCX to GitHub reports/ folder
4. Provide individual download links for each report
5. Create summary index file (optional)

**Summary Index Format (if requested):**
```markdown
# December 3, 2025 Auction Analysis
**Total Properties:** 19
**BECA Verified:** 10
**Recommendations:** 4 BID | 3 REVIEW | 12 SKIP

## BID Recommendations
1. [123 Main St](./123_Main_St_2024CA012345_2025-12-03.docx) - Ratio: 75%
2. [456 Oak Ave](./456_Oak_Ave_2024CA012346_2025-12-03.docx) - Ratio: 78%
...

## REVIEW Recommendations
...

## SKIP Recommendations
...
```

### Batch Naming Convention

**Individual files:**
```
{address}_{case_number}_{auction_date}.docx
```

**Summary index:**
```
{auction_date}_auction_summary.md
```

**GitHub path:**
```
reports/{auction_date}/{filename}
```

---

## Quality Assurance Checklist

### Before Finalizing Report

**Critical Checks (Must Pass):**
- [ ] Fits on one page (if not, reduce font/spacing)
- [ ] No Property360 or Mariam references
- [ ] BidDeed.AI branding present
- [ ] Recommendation color matches badge (BID=green, REVIEW=orange, SKIP=red)
- [ ] Max bid formula calculated correctly
- [ ] Bid/judgment ratio matches recommendation threshold
- [ ] All dollar amounts formatted with $ and commas ($160,000 not 160000)
- [ ] Dates formatted consistently (December 3, 2025 not 12/3/25)

**Data Accuracy (Verify):**
- [ ] Address matches BECA/RealForeclose
- [ ] Case number matches BECA
- [ ] Judgment amount matches BECA
- [ ] ARV supported by comps (not guessed)
- [ ] Repair estimate reasonable (not optimistic)
- [ ] Lien priority based on AcclaimWeb search (not assumed)

**Professional Appearance:**
- [ ] No spelling errors
- [ ] Tables aligned properly
- [ ] Colors consistent throughout
- [ ] Font sizes readable (minimum 8pt)
- [ ] Borders and spacing clean
- [ ] Photo embedded correctly (if available)

**Branding Compliance:**
- [ ] "BidDeed.AI" (not BrevardBidderAI)
- [ ] "Powered by The Everest Ascent™" in footer
- [ ] "BidDeed.AI ML Prediction" (not XGBoost)
- [ ] No competing brand references

---

## Special Cases and Exceptions

### Shabbat Auction Conflicts

**When auction falls on Shabbat (Friday sunset through Saturday evening):**

**Header Modification:**
```
[Property Address]
123 Main Street, Satellite Beach, FL 32937
⚠️ SHABBAT CONFLICT - CANNOT ATTEND ⚠️

Case #: 2024CA012345 | Auction: Friday, December 20, 2025 @ 11:00 AM
Note: Auction time conflicts with Shabbat observance
```

**Color:** Orange background (#FFF3E0) for Shabbat notice
**Impact:** Report still generated, but flagged as "cannot attend"
**Alternative:** Consider proxy bidder or skip entirely

### Commercial Properties (No Beds/Baths)

**Property Details Table Modification:**
```
| Attribute | Value |
|-----------|-------|
| **Parcel ID** | 12-34-56-78-9000.0 |
| **Property Type** | Commercial - Retail |
| **Building Sq Ft** | 3,500 |
| **Year Built** | 2005 |
| **Assessed Value** | $450,000 |
```

**Note:** Omit beds/baths, add "Property Type" instead

### Properties Without BCPAO Photos

**When photo URL returns 404:**
- Omit photo section entirely
- Expand property details table to fill space
- Add note: "BCPAO photo not available"

### HOA Foreclosure Properties

**Add prominent warning in Lien Priority section:**
```
⚠️ HOA FORECLOSURE - SENIOR MORTGAGE SURVIVAL RISK ⚠️

• Plaintiff: [HOA Name] Homeowners Association
• Senior Mortgage: $250,000 to U.S. Bank SURVIVES
• Buyer takes property SUBJECT TO senior mortgage
• Effective purchase price: Bid amount + $250,000 mortgage
• CRITICAL: Verify senior mortgage payoff or assumption terms
```

**Color:** Red background (#FFEBEE) for HOA warning box
**Font:** Bold, larger (11pt)
**Impact:** This is a deal-breaker for most buyers unless accounted for

---

## Performance Optimization

### Reducing Page Length

**If report exceeds one page, try in order:**

1. **Reduce font sizes (minimum 8pt):**
   - Body text: 9pt → 8pt
   - Tables: 9pt → 8pt
   - Headers: 16pt → 14pt

2. **Tighten spacing:**
   - Line spacing: 1.0 → 0.9
   - Paragraph spacing: 6pt → 3pt before/after
   - Table cell padding: 4pt → 2pt

3. **Condense content:**
   - Lien summary: Full sentences → Bullet points
   - Recommendation justification: 3 sentences → 2 sentences
   - Remove optional ForecastEngine™ section if not critical

4. **Narrow margins (last resort):**
   - 0.5" → 0.4" (but maintain readability)

**Never:**
- ❌ Use font smaller than 8pt (unreadable)
- ❌ Omit critical data (ARV, max bid, lien priority)
- ❌ Remove disclaimer footer (liability protection)

### Batch Generation Optimization

**For 10+ property reports:**
- Use asynchronous generation (Python asyncio)
- Parallel API calls to BCPAO for photos
- Cache photo downloads (don't re-fetch same photos)
- Generate reports in parallel (async doc creation)

**Estimated timing:**
- Single report: 5-10 seconds
- 10 reports (parallel): 15-20 seconds
- 50 reports (parallel): 60-90 seconds

---

## Error Handling

### Common Errors and Solutions

**Error: "ARV data missing"**
- Solution: Cannot generate report without ARV
- Action: Log to Supabase errors table, skip this property
- User message: "Property skipped - insufficient valuation data"

**Error: "BCPAO photo 404"**
- Solution: Generate report without photo
- Action: Add note "BCPAO photo not available"
- Impact: Cosmetic only, report still valid

**Error: "Lien priority incomplete"**
- Solution: Cannot generate BID recommendation without lien data
- Action: Generate SKIP or REVIEW with disclaimer
- User message: "Lien analysis incomplete - recommend manual review"

**Error: "Report exceeds one page"**
- Solution: Apply optimization steps (reduce fonts, spacing)
- Action: If still exceeds, log warning but generate anyway
- User message: "Report generated with reduced formatting to fit one page"

**Error: "Missing case number"**
- Solution: Cannot generate report without case number
- Action: Log to errors table, skip this property
- User message: "Property skipped - BECA verification failed"

---

## Integration with BidDeed.AI Pipeline

### Stage 10: Report Generation (This Skill)

**Inputs from Prior Stages:**
- Stage 1: Property address, auction date
- Stage 2: Case number, judgment, plaintiff
- Stage 3: Lien details (AcclaimWeb)
- Stage 4: Lien priority analysis
- Stage 5: Tax certificate status
- Stage 6: Demographics (for context)
- Stage 7: ML predictions (ForecastEngine™)
- Stage 8: Max bid calculation, ratio
- Stage 9: BID/REVIEW/SKIP recommendation

**Outputs to Next Stages:**
- Stage 11: Report URL for disposition tracking
- Stage 12: Report archived to Supabase

**Handoff Format (JSON):**
```json
{
  "property_id": "12-34-56-78-9000.0",
  "report_status": "generated",
  "report_path": "reports/2025-12-03/123_Main_St_2024CA012345.docx",
  "report_url": "https://github.com/breverdbidder/brevard-bidder-scraper/blob/main/reports/2025-12-03/123_Main_St_2024CA012345.docx",
  "recommendation": "BID",
  "max_bid": 160000,
  "ratio": 0.75,
  "generation_time": "2026-01-13T14:45:00Z"
}
```

---

## Updates and Corrections

### When to Update This Skill

**Branding Changes:**
- New BidDeed.AI logo or color scheme
- Methodology name update (currently "The Everest Ascent™")
- Footer disclaimer wording changes
- Company name changes

**Format Improvements:**
- Better one-page layout discovered
- More efficient data presentation
- Improved readability techniques
- Optimized table structures

**Content Enhancements:**
- New ForecastEngine™ predictions to include
- Additional data sources to integrate
- Better recommendation justification patterns
- Improved error handling messages

**User Feedback:**
- Ariel requests specific formatting changes
- Auction attendees suggest improvements
- Attorney/closing coordinator feedback
- Print quality issues discovered

### Update Format

```markdown
## [DATE] - [BRIEF DESCRIPTION]
**Signal:** [What triggered this update]
**Change:** [What was updated in report format]
**Justification:** [Why this improves report quality]
**Impact:** [Better decisions, easier reading, etc.]
**Confidence:** [How validated is this change]
```

---

## References

- generate_brevard_reports.js (primary generation script)
- BCPAO API: https://www.bcpao.us/api-services
- Python-DOCX: python-docx.readthedocs.io
- Microsoft Word OOXML: Office Open XML standard
- BidDeed.AI Brand Guidelines (this document)

**Last Validated:** 2026-01-13  
**Validation Method:** 100+ reports generated for Dec 3, 2025 auction and prior auctions

---

## Examples

### Complete Report Example (BID)

```
═══════════════════════════════════════════════════════════════════
                        123 MAIN STREET                      BidDeed.AI
                   SATELLITE BEACH, FL 32937                      
                                                                   ┌─────────────┐
Case #: 2024CA012345 | Auction: December 3, 2025 | Judgment: $280,000   │     BID     │
Plaintiff: U.S. Bank National Association                          │ Max: $160K  │
                                                                   │ Ratio: 75%  │
                                                                   └─────────────┘
───────────────────────────────────────────────────────────────────
PROPERTY DETAILS

Parcel ID       12-34-56-78-9000.0     Assessed Value   $350,000
Bedrooms        3                      ARV (Estimated)  $400,000
Bathrooms       2                      Repairs (Est)    $50,000
Sq Ft           1,800                  
Year Built      1995                   

───────────────────────────────────────────────────────────────────
FINANCIAL ANALYSIS

Max Bid Calculation:
ARV ($400,000) × 70% = $280,000
Less: Repairs          -$50,000
Less: Hard Costs       -$10,000
Less: Risk Reserve     -$60,000  [MIN($25K, ARV×15%)]
─────────────────────────────────
Maximum Safe Bid:      $160,000

Judgment Amount:       $280,000
Bid/Judgment Ratio:    75% ✓

───────────────────────────────────────────────────────────────────
LIEN PRIORITY SUMMARY

• Senior Lien: First Mortgage to U.S. Bank ($250,000)
• Junior Liens: Second Mortgage ($30,000) - WIPED OUT ✓
• Tax Certificates: None outstanding (RealTDM verified) ✓
• HOA Status: Not an HOA foreclosure ✓
• Title Concerns: None identified ✓

───────────────────────────────────────────────────────────────────
FORECASTENGINE™ ANALYSIS

• Third-Party Purchase Probability: 68% (BidDeed.AI ML)
• Lien Priority Score: 97/100 (High Confidence)
• Exit Strategy: Fix & Flip (Optimal for 32937 Satellite Beach)

───────────────────────────────────────────────────────────────────
RECOMMENDATION: BID

Strong opportunity with 75% bid/judgment ratio providing adequate 
margin. Clean title with junior liens wiped out in foreclosure. 
Optimal location (32937 Satellite Beach) supports Fix & Flip exit 
strategy with $50K+ profit potential.

═══════════════════════════════════════════════════════════════════
This analysis is provided for informational purposes only and does 
not constitute legal, financial, or investment advice. Conduct 
independent due diligence before bidding.

                  Powered by The Everest Ascent™ | BidDeed.AI
              Report generated: January 13, 2026 at 2:45 PM EST
═══════════════════════════════════════════════════════════════════
```

**Visual Notes:**
- Green highlight on "BID" badge and recommendation
- Checkmarks (✓) in green for positive lien findings
- All tables properly aligned
- Dollar amounts with commas
- Professional spacing throughout
- Fits on one page at 100% zoom
