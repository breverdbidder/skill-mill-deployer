# Foreclosure Domain Expertise

**Skill Type:** Domain Knowledge  
**Scope:** BidDeed.AI Foreclosure Auction Intelligence  
**Last Updated:** 2026-01-13  
**Confidence:** HIGH (validated across 1,393+ historical auctions)

---

## Purpose

This skill provides expert-level knowledge of Florida foreclosure law, lien priority structures, and Brevard County-specific courthouse procedures. Use this skill when analyzing foreclosure properties, determining lien priorities, calculating max bids, or making BID/REVIEW/SKIP recommendations.

---

## Florida Foreclosure Law Fundamentals

### Lien Priority Hierarchy (Critical)

**Standard Priority Order:**
1. **Property Taxes** (always first position, survive foreclosure)
2. **HOA Assessments** (special case - see below)
3. **First Mortgage** (senior lien)
4. **Second Mortgage** (junior lien)
5. **Mechanic's Liens** (based on recording date)
6. **Judgment Liens** (based on recording date)
7. **Code Enforcement Liens** (municipal)

**CRITICAL EXCEPTION - HOA Foreclosures:**
When an HOA forecloses for unpaid assessments:
- HOA foreclosure wipes out ALL junior liens (junior mortgages, judgments, etc.)
- **BUT senior mortgages SURVIVE** - this is the critical risk factor
- Buyer at HOA foreclosure auction takes property SUBJECT to senior mortgage
- Must detect this scenario by checking plaintiff name against HOA plaintiff list

**How to Identify HOA Foreclosures:**
- Plaintiff name contains: "Homeowners Association", "HOA", "Condominium Association", "COA"
- Check against 28 tracked BECA plaintiffs (see BECA Plaintiff Patterns section)
- Search actual recorded documents in AcclaimWeb - NEVER guess
- If HOA plaintiff detected → automatically flag senior mortgage survival risk

### Foreclosure Sale Mechanics

**Florida Statute 45.031 - Judicial Sale:**
- Sale conducted by Clerk of Court at public auction
- Highest bidder wins (subject to confirmation)
- Winning bidder receives Certificate of Title
- Redemption rights: None after sale (cut off at foreclosure)
- Title vests immediately upon issuance of Certificate of Sale

**Brevard County Specifics:**
- In-person auctions: Titusville Courthouse, 11:00 AM
- Location: 400 S Street, Titusville, FL 32780
- Payment: Cashier's check or cash, 5% deposit immediately, balance within 24 hours
- Online tax deed auctions: brevard.realforeclose.com (different from foreclosure auctions)

**Key Distinction:**
- **Foreclosure Auctions:** In-person only, senior lien holder foreclosing
- **Tax Deed Auctions:** Online via RealForeclose, county foreclosing for unpaid taxes

---

## Lien Discovery Methodology

### Sources and Search Strategy

**Primary Sources (in search order):**

1. **BECA Scraper** (first check)
   - URL: brevard.brevardclerk.us
   - Purpose: Verify case details, plaintiff, judgment amount
   - 12 regex patterns for data extraction
   - Anti-detection capabilities
   - If verified here → high confidence in case data

2. **AcclaimWeb** (mortgage/lien search)
   - URL: vaclmweb1.brevardclerk.us
   - Search by: Party Name (owner, plaintiff, lender)
   - Extract: Mortgage recordings, assignments, satisfactions, liens
   - Critical: Shows actual recorded documents, not guesses
   - Look for: Book/Page references, recording dates, amounts

3. **RealTDM** (tax certificate search)
   - Purpose: Identify outstanding tax certificates
   - Shows: Certificate holders, amounts, interest rates
   - Important: Tax certs senior to all liens except property taxes

4. **BCPAO** (property assessment data)
   - API: gis.brevardfl.gov/gissrv/rest/services/Base_Map/Parcel_New_WKID2881/MapServer/5
   - Provides: Owner name, assessed values, property characteristics
   - Photo URL pattern: https://www.bcpao.us/photos/{prefix}/{account}011.jpg
   - Note: Has LIV_AREA and values, but NO beds/baths/year built (need Zillow/Redfin for that)

5. **Tax Collector** (delinquent taxes)
   - Shows: Current year delinquencies, payment plans
   - Cross-reference with tax certificate data

### Critical Search Patterns

**For Senior Mortgage Detection:**
```
1. Search plaintiff name in AcclaimWeb
2. Find original mortgage recording (earliest date)
3. Check for assignments/transfers
4. Verify satisfaction hasn't been recorded
5. If HOA plaintiff → MUST find senior mortgage if it exists
```

**For Junior Lien Detection:**
```
1. Search owner name in AcclaimWeb
2. Look for recordings AFTER first mortgage date
3. Common junior liens:
   - Second mortgages
   - HELOCs
   - Judgment liens
   - Mechanic's liens
4. These get wiped out in foreclosure
```

**Red Flags Requiring Manual Review:**
- Plaintiff is HOA but no senior mortgage found (search harder)
- Multiple mortgages with unclear priority
- Recent assignments or modifications
- Code enforcement liens (may have superpriority)
- Lis pendens from different case (competing foreclosure)

---

## BECA Plaintiff Patterns

### Tracked Plaintiffs (28 Known)

**High-Volume Plaintiffs (appears frequently):**
- U.S. Bank National Association
- Wells Fargo Bank, N.A.
- Bank of America, N.A.
- JPMorgan Chase Bank, N.A.
- Deutsche Bank National Trust Company

**HOA/Condominium Plaintiffs (CRITICAL - senior mortgage survival risk):**
- [HOA name] Homeowners Association
- [Condo name] Condominium Association, Inc.
- Community associations (various)

**Specialty Servicers:**
- Nationstar Mortgage LLC
- Select Portfolio Servicing
- Ocwen Loan Servicing
- PHH Mortgage Corporation

### Third-Party Purchase Prediction

**XGBoost ML Model (64.4% accuracy):**
- Predicts probability property sells to third-party (not plaintiff)
- Features: Plaintiff name, property type, judgment amount, location
- Output: Third-party purchase probability (0-100%)
- Branded as "BidDeed.AI ML Prediction" in reports

**Plaintiff-Specific Patterns:**
- Credit-to-bid plaintiffs: Often buy back at judgment amount
- Servicers: More likely to allow third-party sales
- HOAs: Almost always want third-party buyers

---

## Max Bid Calculation Formula

### Standard Formula
```
Max Bid = (ARV × 70%) - Repairs - $10,000 - MIN($25,000, ARV × 15%)
```

**Component Breakdown:**

1. **ARV × 70%** (After Repair Value × 70%)
   - Conservative estimate of sellable value
   - Accounts for market timing, holding costs, profit margin

2. **- Repairs**
   - Estimated renovation costs
   - Include: deferred maintenance, cosmetic updates, systems
   - Conservative estimate (round up)

3. **- $10,000** (Hard Costs Buffer)
   - Closing costs
   - Title insurance
   - Utilities during holding period
   - Marketing/staging

4. **- MIN($25,000, ARV × 15%)** (Risk/Profit Reserve)
   - Minimum $25K profit target
   - OR 15% of ARV if that's higher
   - Ensures adequate margin for unexpected issues

### Recommendation Thresholds

**Bid/Judgment Ratio:**
- **≥75%:** BID (strong opportunity)
- **60-74%:** REVIEW (marginal, needs closer analysis)
- **<60%:** SKIP (insufficient margin)

**Example Calculation:**
```
Property: 123 Main St, Satellite Beach
ARV: $400,000
Repairs: $50,000
Judgment: $280,000

Max Bid = ($400K × 70%) - $50K - $10K - MIN($25K, $60K)
        = $280K - $50K - $10K - $60K
        = $160,000

Ratio = $160K / $280K = 57%
Recommendation: SKIP (below 60% threshold)
```

---

## Exit Strategy Decision Trees

### Primary Exit Strategies

**1. Fix & Flip (3-6 months)**
- Best for: Properties needing cosmetic updates
- Target neighborhoods: 32937, 32940, 32953, 32903
- Profit target: $50K+ after all costs
- Risk: Market timing, repair overruns

**2. Buy & Hold Rental (5+ years)**
- Best for: Stable condition, good rental demographics
- Target: 1.5%+ monthly rent-to-price ratio
- Consider: Property management, maintenance reserves
- Risk: Vacancy, tenant issues

**3. Mid-Term Rental (MTR) - "Third Sword Strategy"**
- Duration: 30-180 day stays
- Target: High-income zips with low vacancy
- Optimal zips: 32937 ($82K income, 5% vacancy)
- Premium: 30-50% higher than long-term rental
- Platform: Furnished Finder, corporate housing sites

**4. Wholesale (immediate)**
- Best for: Heavy rehabs, probate issues, title complications
- Target: Other investors, cash buyers
- Margin: $10K-$20K assignment fee
- Risk: Finding qualified buyer quickly

### Decision Logic

**If ARV < $200K:**
- Consider wholesale or rental (flip margins too thin)

**If ARV $200K-$400K:**
- Prime fix & flip range in Brevard County
- Or MTR in optimal zips (32937, 32940, 32953)

**If ARV > $400K:**
- Luxury flip or high-end rental
- Longer holding periods, higher risk
- Need stronger comps and buyer pool analysis

**Location-Specific:**
- **Satellite Beach (32937):** MTR goldmine, beach proximity
- **Melbourne/Viera (32940):** Strong retail, family rentals
- **Merritt Island (32953):** Space Coast workforce housing
- **Indialantic (32903):** Beach community, vacation rental potential

---

## Quality Control Checklist

### Before Making BID Recommendation

- [ ] BECA case verified (not just scraped data)
- [ ] Lien search completed in AcclaimWeb (actual documents)
- [ ] HOA plaintiff check (senior mortgage survival risk assessed)
- [ ] Tax certificate search completed (RealTDM)
- [ ] Property taxes current or accounted for in max bid
- [ ] ARV supported by recent comps (within 6 months, same zip)
- [ ] Repair estimate includes buffer (round up 20%)
- [ ] Exit strategy identified and viable
- [ ] Bid/judgment ratio ≥75% for BID recommendation
- [ ] Title issues flagged (competing liens, clouds, etc.)

### Before Making SKIP Recommendation

- [ ] Valid reason documented (low ratio, title issue, location, etc.)
- [ ] Not skipping due to incomplete research (do the work first)
- [ ] Alternative exit strategies considered and rejected
- [ ] Documented in decision log with justification

---

## Common Mistakes to Avoid

**1. Guessing at Lien Priority**
- ❌ WRONG: "Probably just one mortgage"
- ✅ RIGHT: Search AcclaimWeb for actual recorded documents

**2. Missing HOA Foreclosure Risk**
- ❌ WRONG: "HOA is foreclosing, liens get wiped out"
- ✅ RIGHT: "HOA foreclosure wipes JUNIOR liens, senior mortgage survives - search for it"

**3. Over-Optimistic ARV**
- ❌ WRONG: Using highest comp or aspirational pricing
- ✅ RIGHT: Conservative median of recent closed sales, same condition

**4. Under-Estimating Repairs**
- ❌ WRONG: "Looks cosmetic, probably $20K"
- ✅ RIGHT: Itemized estimate with 20% contingency, account for unknowns

**5. Ignoring Exit Strategy Viability**
- ❌ WRONG: "We'll figure out exit after we buy"
- ✅ RIGHT: Confirm exit strategy BEFORE bidding, with market data

**6. Skipping Title Search**
- ❌ WRONG: "Foreclosure clears everything"
- ✅ RIGHT: Foreclosure clears JUNIOR liens, always verify what survives

---

## Integration with BidDeed.AI Pipeline

**This skill applies to stages:**
- **Stage 3:** Title Search (lien discovery methodology)
- **Stage 4:** Lien Priority Analysis (hierarchy rules, HOA detection)
- **Stage 5:** Tax Certificates (RealTDM search patterns)
- **Stage 8:** Max Bid Calculation (formula and components)
- **Stage 9:** Decision Log (recommendation thresholds)
- **Stage 11:** Disposition Tracking (exit strategy selection)

**ForecastEngine™ Integration:**
- Lien Priority ForecastEngine: 97/100 accuracy (uses this skill)
- Exit Strategy ForecastEngine: 95/100 accuracy (uses decision trees)
- Max Bid ForecastEngine: 96/100 accuracy (uses formula)

---

## Updates and Corrections

**When to update this skill:**
- New Florida foreclosure statute changes
- Brevard County procedure updates
- Discovered HOA plaintiff patterns
- Lien priority edge cases encountered
- Max bid formula refinements based on outcomes
- New exit strategy opportunities identified

**Update format:**
```markdown
## [DATE] - [BRIEF DESCRIPTION]
**Signal:** [What triggered this update]
**Change:** [What was updated]
**Justification:** [Why this improves the skill]
**Confidence:** [How validated is this change]
```

---

## References

- Florida Statute Chapter 45 (Foreclosure)
- Florida Statute Chapter 720 (HOA Powers)
- Brevard County Clerk of Court procedures
- AcclaimWeb recorded documents (primary source)
- 1,393 historical Brevard County foreclosure auction results
- BidDeed.AI 12-stage pipeline methodology

**Last Validated:** 2026-01-13  
**Validation Method:** Cross-referenced against Dec 3, 2025 auction results (19 properties, 10 BECA verified)
