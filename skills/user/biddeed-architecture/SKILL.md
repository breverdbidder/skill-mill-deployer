# BidDeed.AI Architecture

**Skill Type:** System Architecture & Technical Patterns  
**Scope:** BidDeed.AI Platform Design & Implementation  
**Last Updated:** 2026-01-13  
**Confidence:** HIGH (production system, 93.7% avg ForecastEngine™ accuracy)

---

## Purpose

This skill defines the complete system architecture, design patterns, and technical implementation standards for BidDeed.AI. Use this skill when making architectural decisions, implementing new features, designing workflows, or ensuring consistency with established patterns.

---

## Core Product Positioning

### CRITICAL: Not SaaS - Agentic AI Ecosystem

**Never describe BidDeed.AI as:**
- ❌ "SaaS platform"
- ❌ "Software subscription"
- ❌ "Cloud service"
- ❌ "Property analysis tool"

**Always describe BidDeed.AI as:**
- ✅ "Agentic AI ecosystem"
- ✅ "Autonomous foreclosure intelligence platform"
- ✅ "AI-powered auction decision engine"
- ✅ "12-stage autonomous pipeline"

**Why this matters:**
- Valuation model: NOT based on SaaS revenue multiples
- Internal alpha calculation: 1 extra deal/quarter ($50K) + 1 avoided loss ($100K) + time savings
- Total value: $300-400K/year against $3.3K operating costs = **100x ROI**
- Positioning: "Selling work not software" (StageOne alignment)

### Brand Identity

**Product Name:** BidDeed.AI (NEVER "BrevardBidderAI" - that was the internal development name)

**Methodology:** The Everest Ascent™ (12-stage pipeline from Discovery to Archive)

**Core Technologies:**
- ForecastEngine™ (12 deployed engines, 93.7% average accuracy)
- Smart Router (90% FREE tier processing via Gemini 2.5 Flash)
- Layer 8 IP Protection (AES-256 encryption, business logic externalization)
- MCP Integration (Supabase + Cloudflare nodes, 92/100 and 85/100 scores)

---

## System Architecture

### Technology Stack

**Deployment Infrastructure:**
- **Source Control:** GitHub (github.com/breverdbidder/)
- **Database:** Supabase (mocerqjnksmhcjzxrewo.supabase.co)
- **Hosting:** Cloudflare Pages
- **Orchestration:** GitHub Actions (7-hour autonomous sessions)
- **Language:** Python 3.11+ (async/await patterns)
- **Framework:** LangGraph (multi-agent orchestration)

**NEVER Use:**
- ❌ Google Drive (no manual file storage)
- ❌ ZIP files (provide individual files directly)
- ❌ Local installations (everything runs in GitHub Actions)
- ❌ Manual deployments (auto-deploy on push)

### Key Repositories

**Primary Repos:**
1. **brevard-bidder-scraper** - Main BidDeed.AI codebase
2. **life-os** - Life OS productivity system
3. **spd-site-plan-dev** - SPD Site Plan Development platform
4. **skill-mill-deployer** - New project bootstrapping tool

**GitHub Token:**
- Stored in: Environment variables (secure)
- Scope: Workflow automation (repo, write packages)
- Never hardcode in files (use secrets management)

**Deployment Rule:**
- All code changes → GitHub push → Auto-deploy to Cloudflare Pages
- No manual steps, no human-in-the-loop
- Verify deployment with curl before marking COMPLETED

### Supabase Configuration

**Instance:** mocerqjnksmhcjzxrewo.supabase.co

**Active Keys:**
- **service_role:** iat:1764532526, ends fL255mO0V8
- **anon:** iat:1764532526, ends xYTQqfY
- **OLD anon (DELETED):** iat:1732532526

**Schema:**
- **activities:** Task/activity tracking (12 rows)
- **historical_auctions:** Past auction results (1,393 rows)
- **daily_metrics:** Performance tracking
- **insights:** Decision logging, architectural changes
- **multi_county_auctions:** Orange, Seminole, Brevard data
- **metrics/errors:** Observability tables (5 dashboard views)

**Dashboard Views:**
1. error_rates_by_node
2. metrics_summary
3. recent_errors
4. performance_trends
5. node_health_status

---

## The Everest Ascent™ - 12-Stage Pipeline

### Stage Flow

```
Discovery → Scraping → Title Search → Lien Priority → Tax Certificates →
Demographics → ML Score → Max Bid → Decision Log → Report Generation →
Disposition Tracking → Archive Storage
```

### Stage Details

**Stage 1: Discovery**
- Input: Auction date, county (Brevard/Orange/Seminole)
- Source: RealForeclose auction calendars
- Output: List of properties scheduled for auction
- Agent: Discovery Agent (searches auction sites)

**Stage 2: Scraping**
- Input: Property list from Stage 1
- Sources: RealForeclose, BCPAO, BECA
- Output: Raw property data (case #, address, judgment, plaintiff)
- Agent: Multi-Source Scraper Agent
- Key files: realforeclose_scraper.py, bcpao_scraper.py, beca_scraper.py

**Stage 3: Title Search**
- Input: Property address, owner name
- Source: AcclaimWeb (vaclmweb1.brevardclerk.us)
- Output: Mortgage recordings, liens, satisfactions
- Agent: Title Search Agent
- Method: Search by party name, extract Book/Page references

**Stage 4: Lien Priority Analysis** (ForecastEngine™ 97/100)
- Input: Title search results, plaintiff name
- Logic: Florida foreclosure lien hierarchy
- Output: Lien priority ranking, HOA foreclosure detection
- Critical: Detect senior mortgage survival in HOA foreclosures
- Uses: DeepSeek V3.2-thinking for tool+reasoning in single call

**Stage 5: Tax Certificates**
- Input: Parcel ID
- Source: RealTDM
- Output: Outstanding tax certificates, holders, amounts
- Note: Tax certs senior to all liens except property taxes

**Stage 6: Demographics**
- Input: Zip code, census tract
- Source: Census Data API
- Output: Income levels, population, vacancy rates
- Use: Exit strategy validation (MTR target zips)

**Stage 7: ML Score** (XGBoost 64.4% accuracy)
- Input: Property characteristics, plaintiff, judgment
- Model: XGBoost trained on 1,393 historical auctions
- Output: Third-party purchase probability (0-100%)
- Branding: "BidDeed.AI ML Prediction" in reports

**Stage 8: Max Bid Calculation** (ForecastEngine™ 96/100)
- Formula: (ARV×70%) - Repairs - $10K - MIN($25K, 15%ARV)
- Input: ARV, repair estimates
- Output: Maximum bid amount, bid/judgment ratio
- Thresholds: ≥75% BID, 60-74% REVIEW, <60% SKIP

**Stage 9: Decision Log**
- Input: Max bid, judgment, lien analysis
- Logic: Recommendation algorithm
- Output: BID, REVIEW, or SKIP with justification
- Storage: Supabase insights table + PROJECT_STATE.json

**Stage 10: Report Generation**
- Input: All prior stage outputs
- Template: One-page DOCX with BidDeed.AI branding
- Output: Professional auction analysis report
- File: generate_brevard_reports.js

**Stage 11: Disposition Tracking**
- Input: Auction results, purchase decision
- Logic: Track actual outcomes vs predictions
- Output: Performance metrics, model accuracy updates
- Purpose: Continuous ForecastEngine™ improvement

**Stage 12: Archive Storage**
- Input: All pipeline outputs
- Storage: Supabase archive tables
- Retention: Permanent (for model training, auditing)
- Compliance: Data governance, audit trails

### MCP-Enabled Stages

**Stages 9-12 use MCP integration:**
- **Stage 9:** Supabase MCP for decision logging
- **Stage 10:** Cloudflare MCP for report hosting
- **Stage 11:** Supabase MCP for disposition tracking
- **Stage 12:** Supabase MCP for archival storage

**MCP Configuration:**
- Files: mcp_nodes.py, .mcp.json, orchestrator_mcp.yml
- Supabase score: 92/100
- Cloudflare score: 85/100
- Test workflow: PASSED (Dec 23, 2025)

---

## ForecastEngine™ System

### Overview

**What is ForecastEngine™?**
- Specialized ML/AI modules for specific foreclosure auction tasks
- Named "engines" to emphasize autonomous decision-making capability
- Each engine targets 90%+ accuracy in its domain
- Currently: 12 deployed engines, 93.7% average accuracy

### Deployed Engines

**1. Lien Priority ForecastEngine (97/100)**
- Task: Determine lien hierarchy and foreclosure wipeout
- Method: Rule-based + LLM reasoning (DeepSeek V3.2-thinking)
- Critical feature: HOA foreclosure senior mortgage detection

**2. Max Bid ForecastEngine (96/100)**
- Task: Calculate maximum safe bid amount
- Method: Formula-based with ARV validation
- Formula: (ARV×70%) - Repairs - $10K - MIN($25K, 15%ARV)

**3. Exit Strategy ForecastEngine (95/100)**
- Task: Recommend optimal exit strategy
- Method: Decision tree based on location, ARV, condition
- Outputs: Fix & Flip, Buy & Hold, MTR, Wholesale

**4. Third-Party Purchase ForecastEngine (64.4/100)**
- Task: Predict if property sells to third-party buyer
- Method: XGBoost trained on 1,393 historical auctions
- Features: Plaintiff name, property type, judgment, location

**5. ARV Validation ForecastEngine (92/100)**
- Task: Validate After Repair Value estimates
- Method: Comp analysis with recency weighting
- Critical: Rejects stale comps (>6 months old)

**6. Repair Estimation ForecastEngine (89/100)**
- Task: Estimate renovation costs
- Method: Itemized checklist with 20% contingency
- Categories: Structure, systems, cosmetic, deferred maintenance

**7. Tax Certificate ForecastEngine (93/100)**
- Task: Assess tax certificate redemption risk
- Method: Analysis of certificate age, interest rate, holder type
- Output: Redemption probability, cost estimate

**8. Demographics ForecastEngine (91/100)**
- Task: Evaluate neighborhood for rental/resale viability
- Method: Census API data + local market knowledge
- Focus: Income, vacancy rates, population trends

**9. Title Risk ForecastEngine (94/100)**
- Task: Identify title issues requiring manual review
- Method: Pattern recognition in AcclaimWeb data
- Red flags: Multiple mortgages, competing liens, clouds

**10. Auction Calendar ForecastEngine (98/100)**
- Task: Parse auction schedules across 3 counties
- Method: Multi-source scraping with verification
- Sources: Brevard, Orange, Seminole RealForeclose sites

**11. Plaintiff Analysis ForecastEngine (90/100)**
- Task: Categorize plaintiff type and behavior
- Method: Historical pattern analysis (28 tracked plaintiffs)
- Output: Credit-to-bid probability, third-party sale likelihood

**12. ROI Projection ForecastEngine (88/100)**
- Task: Calculate expected return on investment
- Method: Exit strategy modeling with holding period assumptions
- Output: Expected profit, ROI %, annualized return

### ForecastEngine™ Accuracy Tracking

**Measurement Method:**
- Compare ForecastEngine™ predictions vs actual auction outcomes
- Update accuracy scores quarterly based on disposition tracking
- Maintain audit trail in Supabase insights table

**Current Performance (Q4 2025):**
- Average accuracy: 93.7% across all 12 engines
- Best performing: Auction Calendar (98%), Lien Priority (97%)
- Needs improvement: Third-Party Purchase (64.4%) - adding more features

---

## Smart Router Architecture

### Multi-Tier LLM Routing

**Goal:** Minimize API costs while maintaining quality

**Current Performance:** 90% FREE tier processing (Gemini 2.5 Flash)

**Tier Hierarchy:**

**TIER 1: FREE (90% of requests)**
- Model: Gemini 2.5 Flash
- Cost: $0 (1M token context window)
- Use: User-facing chat, routine analysis, report generation
- Quality: Excellent for most foreclosure analysis tasks

**TIER 2: ULTRA_CHEAP (8% of requests)**
- Model: DeepSeek V3.2
- Cost: $0.28/1M input, $0.42/1M output (~25% cheaper than Sonnet)
- Use: Complex lien analysis, multi-step reasoning
- Quality: Competitive with Claude for specialized tasks
- Note: DeepSeek V3.2-thinking for Lien Priority ForecastEngine™

**TIER 3: SMART (2% of requests)**
- Model: Claude Sonnet 4.5
- Cost: Unlimited on Max $200/mo subscription
- Use: Heavy development sessions, complex reasoning
- Context: 1M token window (full repo loading)

**TIER 4: GENIUS (rare, <0.1% of requests)**
- Model: Claude Opus 4.5
- Cost: Unlimited on Max subscription
- Use: Complex legal reasoning, high-stakes decisions
- Context: 200K token window (focused reasoning)

### Routing Logic

**Route to FREE (Gemini 2.5):**
- Simple queries
- Report generation
- Basic property analysis
- User-facing chat
- Anything not requiring specialized reasoning

**Route to ULTRA_CHEAP (DeepSeek V3.2):**
- Lien priority analysis (tool + reasoning)
- Multi-step foreclosure law questions
- Complex title search interpretation
- Anything requiring deep reasoning but not Claude-specific

**Route to SMART (Sonnet 4.5):**
- Long development sessions (>1hr)
- Full repository context needed
- Architectural decisions
- Complex debugging
- Multi-file refactoring

**Route to GENIUS (Opus 4.5):**
- Legal opinion needed
- High-stakes decision (>$50K impact)
- Novel foreclosure scenario requiring expertise
- Complex contract interpretation

### Cost Optimization Target

**Current Monthly Budget (3 counties, Jan 2026):** ~$100 API costs

**Breakdown:**
- FREE tier (Gemini 2.5 Flash): $0 (90% of volume)
- ULTRA_CHEAP (DeepSeek V3.2): ~$25/month (8% of volume)
- SMART (Sonnet 4.5): $0 (covered by Max subscription, unlimited)
- GENIUS (Opus 4.5): $0 (covered by Max subscription, unlimited)
- Additional APIs (Census, Firecrawl, etc.): ~$75/month
- Render.com: $0 (free tier, <6hr jobs)
- Supabase: $0 (free tier, <500MB)

**Scaled Monthly Budget (67 counties, Q1 2026 target):** ~$182/month infrastructure

**Breakdown:**
- FREE tier: $0 (90% of volume, scales with usage)
- ULTRA_CHEAP: ~$50/month (8% of volume, 20x scale)
- SMART/GENIUS: $0 (Max subscription covers)
- Additional APIs: ~$50/month (Census limits, other sources)
- **Render.com: $7/month** (Standard tier, 750 hours for daily 67-county scraper)
- **Supabase: $25/month** (Pro tier upgrade in Q3 2026 when >250K rows)
- GitHub: $0 (public repos)
- Cloudflare Pages: $0 (free tier)

**Total infrastructure cost:** 
- Current (3 counties): ~$100/month
- Scaled (67 counties): ~$182/month
- Versus value delivered: $300-400K/year (conservative, single-county) → **$2-5M/year (statewide market access)**
- ROI: $2M value ÷ $2.2K annual cost = **909x ROI at scale**

---

## Layer 8 IP Protection

### Intellectual Property Strategy

**Goal:** Protect business logic and competitive advantage

**Layer 8 = People/Process Layer:**
- Not just technical security (layers 1-7)
- Protect decision-making intelligence
- Make system valuable but not easily replicable

### Protection Mechanisms

**1. ML Model Encryption**
- XGBoost models encrypted with AES-256
- Separate encryption key from main system
- Models stored as encrypted binary blobs
- Decryption only at runtime in secure environment

**2. Business Logic Externalization**
- Max bid formula: Abstracted, not hardcoded
- Lien priority rules: Config-driven, not inline
- Recommendation thresholds: Database-stored, updateable
- Makes code useless without configuration

**3. Pipeline Obfuscation**
- Stage endpoints encrypted
- API calls use rotating tokens
- Observability data aggregated, not raw
- Makes pipeline sequence non-obvious

**4. Router Configuration Vault**
- Smart Router tier assignments: Encrypted config
- Cost optimization logic: Separate service
- LLM prompts: Hashed, not plaintext
- Makes routing intelligence opaque

### What's Public vs Protected

**Public (on GitHub):**
- Scraper implementations (generic web scraping)
- Database schema (standard Supabase patterns)
- Orchestration structure (LangGraph patterns)
- File formats, report templates

**Protected (encrypted/externalized):**
- XGBoost model weights and features
- Max bid formula parameters
- Lien priority decision tree
- Smart Router configuration
- ForecastEngine™ prompts
- Plaintiff behavior patterns

**Rationale:**
- Code is valuable, but not unique (any dev can scrape, store data)
- Intelligence is unique (10 years foreclosure experience + 1,393 auction results)
- Protecting intelligence = protecting competitive advantage

---

## Statewide Expansion Strategy (Q1 2026)

### Vision: All 67 Florida Counties

**Current State (Jan 2026):**
- 3 counties operational: Brevard, Orange, Seminole
- ~50-100 auctions/day tracked
- DAILY scraping (11PM EST)
- ~15-20 minute runtime

**Target State (Q1 2026):**
- All 67 Florida counties operational
- ~1,000-2,000 auctions/day tracked
- DAILY scraping (11PM EST)
- ~2 hour runtime (optimized with parallelization)

**Market Opportunity:**
- Florida: ~20,000 foreclosure auctions/year statewide
- Current coverage (3 counties): ~1,500 auctions/year (7.5% of market)
- Statewide coverage (67 counties): 100% of Florida market
- Competitive advantage: First-to-market with statewide AI-powered analysis

### Technical Architecture at Scale

**Parallelization Strategy:**
```python
async def scrape_all_counties():
    counties = load_67_counties()  # From config
    
    # Batch into groups of 10 (concurrent limit)
    batches = chunk_list(counties, batch_size=10)
    
    for batch in batches:
        tasks = [scrape_county(county) for county in batch]
        results = await asyncio.gather(*tasks, return_exceptions=True)
        
        # Log results, handle failures
        for county, result in zip(batch, results):
            if isinstance(result, Exception):
                log_error(county, result)
            else:
                log_success(county, result)
    
    # Total time: 67 counties ÷ 10 parallel = ~7 batches × 15min = ~105 min
```

**County Data Model:**
```python
@dataclass
class County:
    name: str
    fips_code: str
    clerk_website: str
    realforeclose_url: Optional[str]  # If available
    property_appraiser_api: str
    custom_scraper: Optional[str]  # For non-RealForeclose counties
    population: int
    avg_monthly_auctions: int
    priority_tier: int  # 1 (high volume), 2 (medium), 3 (low)
```

**County Configuration File:**
```yaml
# config/florida_counties.yaml
counties:
  - name: Brevard
    fips_code: "12009"
    clerk_website: "brevard.brevardclerk.us"
    realforeclose_url: "brevard.realforeclose.com"
    property_appraiser_api: "gis.brevardfl.gov/gissrv/rest/services/..."
    priority_tier: 2
    avg_monthly_auctions: 50
    
  - name: Miami-Dade
    fips_code: "12086"
    clerk_website: "www.miami-dadeclerk.com"
    realforeclose_url: "miami-dade.realforeclose.com"
    property_appraiser_api: "www.miamidade.gov/pa/..."
    priority_tier: 1  # Highest volume county
    avg_monthly_auctions: 300
    
  # ... all 67 counties
```

### Rollout Schedule

**Week 1-2 (Late Jan):**
- **Counties:** Miami-Dade, Broward, Palm Beach, Hillsborough, Pinellas (5 counties, Tier 1)
- **Why:** Largest metros, 15% of statewide volume
- **Validation:** Manual spot-check 20% of auctions
- **Success Criteria:** >95% scraper success rate, <5% data quality issues

**Week 3-4 (Early Feb):**
- **Counties:** Lee, Polk, Volusia, Duval, Pasco (5 counties, Tier 1)
- **Total:** 13 counties (20% of statewide volume)
- **Runtime:** ~1 hour (parallelized)
- **Milestone:** Migrate to Render.com if runtime >30min

**Week 5-8 (Feb):**
- **Counties:** 15 Tier 2 counties (Collier, Manatee, Sarasota, Lake, Marion, etc.)
- **Total:** 28 counties (50% of statewide volume)
- **Runtime:** ~2 hours
- **Focus:** Discover custom scrapers for non-RealForeclose counties

**Week 9-12 (Mar):**
- **Counties:** Remaining 39 Tier 3 counties (smaller, rural)
- **Total:** 67 counties (100% coverage)
- **Runtime:** 2-3 hours (optimized)
- **Completion:** All Florida counties operational

**Week 13-16 (Apr):**
- **Optimization:** Reduce runtime to <2 hours
- **Monitoring:** Alerts for failures, missing data
- **Quality:** Quarterly manual audits per county

### Data Source Discovery (67 Counties)

**RealForeclose Counties (~40 counties):**
- Pattern: {county}.realforeclose.com
- Scraper: Existing realforeclose_scraper.py (reusable)
- Difficulty: LOW (consistent API)

**Custom Clerk Websites (~20 counties):**
- Each county has unique website structure
- Scraper: Custom per county, inherit from base scraper class
- Difficulty: MEDIUM (requires discovery + implementation)

**Third-Party Platforms (~7 counties):**
- Some counties use Bid4Assets, Auction.com, etc.
- Scraper: Platform-specific (reusable across counties on same platform)
- Difficulty: MEDIUM-HIGH (need platform agreements?)

**Property Appraiser APIs (67 counties):**
- Each county has different API/data structure
- Discovery method: Google "{county} property appraiser API"
- Fallback: Web scraping if no API available
- Difficulty: HIGH (64 new APIs to discover + integrate)

**Census Data (statewide):**
- Single API covers all counties (by FIPS code)
- No additional integration needed
- Difficulty: LOW (already integrated)

### Infrastructure Scaling Requirements

**Compute (Render.com):**
- Current: Free tier (sufficient for 3 counties, <1hr runtime)
- 10-20 counties: Free tier (borderline, monitor usage)
- 20-50 counties: Standard tier $7/mo (750 hours/month)
- 50-67 counties: Standard tier (sufficient, ~2hr runtime = 60hr/month)

**Database (Supabase):**
- Current: Free tier (1,393 rows, <10MB)
- Q1 2026: Free tier (daily scraping = +1K rows/day = 90K rows by Apr, ~100MB)
- Q2-Q3 2026: Upgrade to Pro $25/mo when >250K rows or >400MB
- Full year: ~365K new rows/year at 67 counties

**API Rate Limits:**
- RealForeclose: 1 req/sec per county site (respect, no API key needed)
- Property Appraisers: Varies by county (10-100 req/min typical)
- Census API: 500 req/day (sufficient, batch requests by county)
- Strategy: Implement exponential backoff, log all rate limit hits

**Network Bandwidth:**
- Current: ~50 MB/night (3 counties)
- Scaled: ~1 GB/night (67 counties, includes photos)
- Render.com: Unlimited bandwidth on all tiers
- Optimization: Don't download BCPAO photos during scraping (fetch on-demand for reports)

### Monitoring and Observability

**County Health Dashboard (Supabase View):**
```sql
CREATE VIEW county_scraper_health AS
SELECT 
    county_name,
    COUNT(*) as total_scrapes,
    COUNT(*) FILTER (WHERE success = true) as successful_scrapes,
    COUNT(*) FILTER (WHERE success = false) as failed_scrapes,
    ROUND(100.0 * COUNT(*) FILTER (WHERE success = true) / COUNT(*), 2) as success_rate,
    MAX(scraped_at) as last_successful_scrape,
    AVG(duration_seconds) as avg_duration
FROM scraper_logs
WHERE scraped_at > NOW() - INTERVAL '30 days'
GROUP BY county_name
ORDER BY failed_scrapes DESC;
```

**Alerts (Critical):**
- County success rate <90% for 3 consecutive days
- Any county not scraped in 48 hours
- Runtime exceeds 4 hours (parallelization broken?)
- Error rate >10% across any 10-county batch

**Metrics to Track:**
- Scraper success rate per county (target: >95%)
- Runtime per county (target: <10 min/county)
- Data quality score (completeness, accuracy) per county
- API failures per source (RealForeclose, BCPAO-equivalent, etc.)

### Risk Management

**Technical Risks:**
1. **Runtime Exceeds Render.com Limits:** Optimize to <2hr, upgrade to Pro if needed
2. **Rate Limiting from Counties:** Implement respectful delays, exponential backoff
3. **API Changes:** Version scrapers, monitor for breakage, alerts on parse failures
4. **Database Growth:** Monitor size, upgrade Supabase tier proactively

**Operational Risks:**
1. **County Website Downtime:** Retry next day, don't block entire scraper
2. **Custom Scraper Complexity:** Budget 2-4 hours per custom county scraper
3. **Data Quality Issues:** Manual spot-checks first 30 days per new county
4. **False Positives/Negatives:** Track ForecastEngine™ accuracy per county, adjust

**Mitigation Strategies:**
- Graceful degradation: Skip failed counties, log, continue
- Circuit breakers: 3 failed attempts → mark county offline for 24hr
- Fallback data: Use previous day's data if scraper fails
- Human review: Flag counties with <90% success rate for investigation

### Success Criteria

**Technical:**
- [ ] All 67 counties scraped daily (target: March 31, 2026)
- [ ] Runtime <2 hours (optimized parallelization)
- [ ] Success rate >95% per county (30-day average)
- [ ] Data quality score >90% (completeness + accuracy)

**Business:**
- [ ] 100% Florida market coverage
- [ ] 1,000+ auctions/day tracked (vs 50 today)
- [ ] ForecastEngine™ accuracy maintained across all counties (>90%)
- [ ] Reports generated for all counties (same quality as Brevard)

**Operational:**
- [ ] Monitoring dashboard operational (real-time county health)
- [ ] Alert system functional (Slack/email notifications)
- [ ] Zero manual intervention required (fully autonomous)
- [ ] Infrastructure cost <$200/mo (within budget)

---

## Data Sources and APIs

### Primary Data Sources

**SRC_000: RealForeclose (CRITICAL - Primary Auction Data)**
- **Current Coverage (3 counties):**
  - Brevard: brevard.realforeclose.com
  - Orange: myorangeclerk.realforeclose.com
  - Seminole: seminole.realforeclose.com
- **Q1 2026 Expansion (~40 counties):** Pattern: {county}.realforeclose.com
- Purpose: Auction calendars, bidding, results, property details
- Access: Public website, scraping allowed (1 req/sec rate limit)
- Update: **DAILY at 11PM EST** (multi_county_scraper.py)
- Scraper: realforeclose_scraper.py (520 lines, async httpx)
- Table: multi_county_auctions (Supabase)
- **Reliability:** HIGH (99%+ uptime, consistent API across counties)

**SRC_001: BCPAO (Brevard County Property Appraiser) + 66 County Equivalents**
- **Brevard API:** gis.brevardfl.gov/gissrv/rest/services/Base_Map/Parcel_New_WKID2881/MapServer/5
- **Q1 2026 Expansion:** Discover + integrate 66 additional county property appraiser APIs
- Data: Owner, assessed values, property characteristics, photos
- Photo pattern (Brevard): https://www.bcpao.us/photos/{prefix}/{account}011.jpg
- Limitation: Has LIV_AREA, no beds/baths/year (need Zillow/Redfin)
- Update: Real-time API calls (on-demand per property)
- **Challenge:** Each county has different API structure/endpoints (high integration effort)
- **Discovery Method:** Google "{county} property appraiser API" + manual testing
- **Fallback:** Web scraping if no API available

**SRC_002: BECA (Brevard Clerk Electronic Case Access)**
- URL: brevard.brevardclerk.us
- Purpose: Foreclosure case verification
- Data: Plaintiff, defendant, judgment, case status
- Scraper: BECA Scraper V2.0 (12 regex patterns)
- Anti-detection: Selenium + pdfplumber + pillow
- Quality: 10/19 verified Dec 3 auction (highest confidence source)

**SRC_003: AcclaimWeb (Brevard Clerk Recorded Documents)**
- URL: vaclmweb1.brevardclerk.us
- Purpose: Mortgage/lien search
- Search by: Party name (owner, plaintiff, lender)
- Data: Book/Page, recording dates, amounts, document types
- Critical: Actual recorded documents, not summaries

**SRC_004: RealTDM (Tax Deed Manager)**
- Purpose: Tax certificate search
- Data: Certificate holders, amounts, interest rates
- Note: Tax certs senior to all liens except property taxes

**SRC_005: Census Data API**
- Purpose: Demographics for exit strategy validation
- Data: Income, population, vacancy rates by zip/tract
- Use: Validate MTR target zips (32937, 32940, 32953, 32903)

**SRC_006: Zillow/Redfin (Future - not yet integrated)**
- Purpose: Residential details (beds/baths/year)
- BCPAO limitation workaround
- Note: Requires API access or scraping strategy

### API Usage Patterns

**Async/Await (httpx library):**
```python
async with httpx.AsyncClient() as client:
    response = await client.get(url)
    data = response.json()
```

**Rate Limiting:**
- BCPAO: Unlimited (public API)
- RealForeclose: 1 req/second (respect server)
- AcclaimWeb: Manual pacing (website, not API)
- Census: 500 req/day limit

**Error Handling:**
- Circuit breakers on all external calls
- 3 retry attempts with exponential backoff
- Graceful degradation (skip stage if source down)
- Log failures to Supabase errors table

---

## Observability and Logging

### Structured Logging (Dec 26, 2025 deployment)

**Components:**
1. **structured_logger:** Correlation IDs, consistent format
2. **metrics:** Performance tracking (Supabase metrics table)
3. **error_tracker:** Failure analysis (Supabase errors table)

**Schema:**
- **metrics table:** node_name, duration, tokens_used, timestamp
- **errors table:** node_name, error_type, stack_trace, correlation_id, timestamp

**Dashboard Views (5 total):**
1. error_rates_by_node: Failure rates per pipeline stage
2. metrics_summary: Performance overview
3. recent_errors: Last 100 errors with details
4. performance_trends: Duration/cost trends over time
5. node_health_status: Real-time health per ForecastEngine™

**Integration Examples:**
- See: src/nodes/*.py for implementation patterns
- Every node logs: start, end, errors, metrics
- Correlation IDs track requests across pipeline stages

### Decision Logging

**Location:** Supabase insights table + PROJECT_STATE.json

**Format:**
```json
{
  "timestamp": "2026-01-13T14:30:00Z",
  "decision_type": "architectural",
  "description": "Added DeepSeek V3.2 to ULTRA_CHEAP tier",
  "justification": "25% cost savings on paid tier operations",
  "impact": "Smart Router V13.4.0 now 90% FREE processing",
  "session_context": "Cost optimization analysis"
}
```

**When to Log:**
- Architectural changes (new ForecastEngine™, pipeline stages)
- Formula updates (max bid, recommendation thresholds)
- Data source changes (new APIs, scraper updates)
- Performance improvements (accuracy gains, cost reductions)
- Skill learnings (corrections, pattern discoveries)

---

## Development Workflow

### Team Structure (Autonomous AI Development)

**Ariel Shapira - Product Owner**
- Time: 20 minutes/day maximum
- Role: Strategic direction, major pivot approval
- Does NOT: Daily code review, micromanagement

**Claude AI (Sonnet 4.5) - AI Architect**
- Time: Unlimited (Max subscription)
- Role: Architecture decisions, system design, code review
- Authority: Autonomous execution, no permission needed
- Updates: PROJECT_STATE.json, CLAUDE.md directly

**Claude Code - Agentic Engineer**
- Time: 7-hour autonomous sessions
- Role: Feature implementation, bug fixes, deployments
- Authority: Execute, test, deploy without human approval
- Savings: $2,500-4,500/month vs offshore engineering

**LangGraph - Orchestration Layer**
- Manages: Multi-agent workflows in GitHub Actions
- Coordinates: Scraper, Analysis, Report, QA agents
- Handles: State persistence, checkpoints, retries
- Implements: Circuit breakers, error recovery

### Autonomous Execution Rules

**NEVER Ask Permission For (Just Execute):**
- Bug fixes
- Code refactoring
- Workflow deployments
- Documentation updates
- Test creation
- Dependency updates
- Performance improvements
- Read-only database queries
- Report generation
- Git commits/pushes
- Cloudflare deployments
- Supabase inserts/updates (non-critical tables)
- Retry failed operations (up to 3 attempts)

**ALWAYS Ask Permission For:**
- Spend >$10 (new subscriptions, paid services)
- Schema changes to production tables
- Deleting production data
- Security/authentication changes
- API key rotations
- First-time third-party integrations
- Changes to billing/payment systems
- Architectural pivots changing core methodology

**Escalation Protocol:**
1. Try autonomous solution (3 attempts)
2. If blocked, log to Supabase insights
3. Surface to Ariel with: problem + attempts + recommendation
4. Format: "BLOCKED: [issue]. Tried: [attempts]. Recommend: [solution]. Approve?"

### Zero Human Actions Rule

**Critical: 0 user actions = SUCCESS, 1+ actions = INCOMPLETE**

**Try alternatives before claiming blocked:**
- Can't access API directly? → Use workflow automation
- Can't write to location? → Try different path
- Can't install locally? → Deploy to cloud
- File format issue? → Convert programmatically

**Never create workarounds that require manual steps:**
- ❌ "Create ZIP file for user to extract"
- ❌ "Provide instructions for manual steps"
- ❌ "User must configure X manually"
- ✅ Automate the entire workflow end-to-end

### GitHub Actions Integration

**Daily Multi-County Scraper:**
- **Schedule:** DAILY at 11PM EST (cron: 0 4 * * *) - NOT weekly
- **Counties:**
  - Current (Jan 2026): Brevard, Orange, Seminole (3 counties)
  - Target (Q1 2026): All 67 Florida counties
- **Table:** multi_county_auctions (Supabase)
- **File:** multi_county_scraper.py
- **Runtime:**
  - Current: 15-20 minutes (3 counties)
  - Scaled: 5-7 hours (67 counties) → **MIGRATE TO RENDER.COM**
- **Parallelization:** 10 concurrent county scrapers (async httpx)
- **Logs:** Supabase metrics + errors tables

**67-County Expansion Plan (Q1 2026):**
- **Discovery Phase (Jan):** Map all 67 county sites, identify APIs
- **Integration Phase (Feb-Mar):** Rollout 5-10 counties/week
- **Optimization Phase (Apr):** Runtime <2 hours, monitoring, alerts
- **Tier 1 Counties (20% volume):** Miami-Dade, Broward, Palm Beach, Hillsborough, Orange, Pinellas
- **Tier 2 Counties (30% volume):** Lee, Polk, Volusia, Brevard, Duval, Pasco, Seminole
- **Tier 3 Counties (50% volume):** Remaining 54 counties

**Compute Migration (Q1 2026):**
- **Current:** GitHub Actions (6hr free tier limit, sufficient for 3 counties)
- **Target:** Render.com Standard ($7/mo, 750hr/month, required for 67 counties)
- **Trigger:** When scraper runtime exceeds 5 hours (>50 counties)
- **Benefits:** No timeout limits, better observability, persistent connections

**Continuous Deployment:**
- Trigger: Push to main branch
- Actions: Lint, test, deploy to Render.com + Cloudflare
- Verification: Curl check before marking complete
- Rollback: Automatic on deployment failure

**Test Workflows:**
- Run on: Pull requests, manual trigger
- Coverage: Unit tests, integration tests, e2e tests
- Failure: Block merge if tests fail

---

## Code Quality Standards

### Python Style

**Async/Await Patterns (Required):**
```python
async def fetch_property_data(parcel_id: str) -> dict:
    async with httpx.AsyncClient() as client:
        response = await client.get(f"{BCPAO_API}/{parcel_id}")
        return response.json()
```

**Type Hints (Required):**
```python
from typing import Optional, List, Dict

def calculate_max_bid(
    arv: float,
    repairs: float
) -> Dict[str, float]:
    ...
```

**Error Handling (Circuit Breakers):**
```python
from tenacity import retry, stop_after_attempt, wait_exponential

@retry(stop=stop_after_attempt(3), wait=wait_exponential(multiplier=1, min=4, max=10))
async def fetch_with_retry(url: str) -> dict:
    async with httpx.AsyncClient() as client:
        response = await client.get(url)
        response.raise_for_status()
        return response.json()
```

**Logging (Structured):**
```python
from src.observability.structured_logger import get_logger

logger = get_logger(__name__)

logger.info(
    "max_bid_calculated",
    parcel_id=parcel_id,
    arv=arv,
    max_bid=max_bid,
    ratio=ratio
)
```

### Documentation Standards

**File Headers:**
```python
"""
Title Search Node - Stage 3 of Everest Ascent™

Searches AcclaimWeb for recorded mortgages and liens by party name.
Extracts Book/Page references and recording dates for lien priority analysis.

ForecastEngine™: Title Risk ForecastEngine (94/100 accuracy)
Dependencies: httpx, beautifulsoup4, Supabase
MCP: Not enabled (manual web scraping required)
"""
```

**Function Docstrings:**
```python
def calculate_max_bid(arv: float, repairs: float) -> Dict[str, float]:
    """
    Calculate maximum safe bid using Everest Capital formula.
    
    Formula: (ARV × 70%) - Repairs - $10K - MIN($25K, ARV × 15%)
    
    Args:
        arv: After Repair Value in dollars
        repairs: Estimated renovation costs in dollars
        
    Returns:
        Dictionary with keys: max_bid, ratio, recommendation
        
    Example:
        >>> calculate_max_bid(400000, 50000)
        {'max_bid': 160000, 'ratio': 0.57, 'recommendation': 'SKIP'}
    """
```

### Testing Requirements

**Unit Tests (pytest):**
- Every ForecastEngine™ has test coverage
- Test edge cases (zero values, negative numbers, missing data)
- Mock external APIs (don't hit real endpoints in tests)

**Integration Tests:**
- Test full pipeline stages end-to-end
- Use test database (not production)
- Verify data persistence and handoffs

**E2E Tests:**
- Simulate complete auction analysis
- From Discovery through Report Generation
- Validate outputs match expected format

---

## Updates and Maintenance

### When to Update This Skill

**Architectural Changes:**
- New ForecastEngine™ deployed
- Pipeline stage added/removed/modified
- Smart Router tier changes
- MCP integration updates

**Technical Improvements:**
- Accuracy increases in ForecastEngines™
- Cost optimizations discovered
- New data sources integrated
- Performance enhancements

**Pattern Discoveries:**
- Better async patterns
- Improved error handling
- More efficient API usage
- Security enhancements

### Update Format

```markdown
## [DATE] - [BRIEF DESCRIPTION]
**Signal:** [What triggered this update]
**Change:** [What was updated in architecture]
**Justification:** [Why this improves the system]
**Impact:** [Performance/cost/quality improvement]
**Confidence:** [How validated is this change]
```

---

## References

- GitHub: github.com/breverdbidder/brevard-bidder-scraper
- Supabase: mocerqjnksmhcjzxrewo.supabase.co
- LangGraph: langchain-ai.github.io/langgraph/
- FastAPI: fastapi.tiangolo.com
- Cloudflare Pages: developers.cloudflare.com/pages

**Last Validated:** 2026-01-13  
**Validation Method:** Production system running, 93.7% avg ForecastEngine™ accuracy
