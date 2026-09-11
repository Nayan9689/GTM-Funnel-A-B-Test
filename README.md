

Project: GTM Funnel A/B Test and Segment Analysis  
Author: Nayan  
Date: September 2026  

---

**Overview**  
This project simulates a realistic Go-To-Market (GTM) experiment for a B2B SaaS sales funnel. The goal is to determine whether a new outreach campaign (Variant B) improves the Lead → Meeting conversion rate compared to the existing campaign (Variant A), while ensuring downstream deal quality is not degraded.  

Unlike generic A/B testing projects (checkout UI, pricing page), this project is directly aligned with GTM-focused Data Analyst and Data Scientist roles. It demonstrates statistical rigor, funnel analysis, and business storytelling — all critical skills for analytics in sales and marketing contexts.

---

**Business Problem**  
Sales teams often experiment with new outreach sequences, landing pages, or campaigns. The risk is that a campaign may increase top-of-funnel activity (more meetings booked) but fail to produce quality leads that progress to pilots or customers.  

This project asks:  
- Does Variant B increase Lead → Meeting conversion?  
- Does the lift survive into Meeting → Pilot conversion (guardrail metric)?  
- Is the effect uniform across segments (SMB vs Enterprise) and channels (Outbound, Paid, Organic, Referral)?  

---

**Methodology**  
1. **Synthetic Dataset Generation**  
   - 5,000 simulated leads with attributes: variant, channel, segment, funnel outcomes.  
   - Encoded realistic effects: Variant B lifts SMB meeting-booked rate by +3pp, flat for Enterprise.  
   - Natural imbalance in variant split (55/45) to mimic real-world messy experiments.  

2. **Power Analysis**  
   - Calculated required sample size using statsmodels.  
   - Baseline meeting-booked rate: 20%.  
   - Minimum detectable effect: +3pp.  
   - Required ~783 leads per variant for 80% power at 5% significance.  

3. **Primary Test**  
   - Two-proportion z-test on Lead → Meeting conversion.  
   - Reported p-value, effect size, and confidence intervals.  

4. **Guardrail Test**  
   - Two-proportion z-test on Meeting → Pilot conversion.  
   - Ensured Variant B’s lift did not degrade downstream quality.  

5. **Segment Analysis**  
   - Cut results by channel and segment.  
   - Found Variant B’s lift concentrated in SMB outbound leads.  
   - Enterprise and Paid channels showed no significant effect.  

6. **Business Recommendation**  
   - Roll out Variant B to SMB outbound campaigns only.  
   - Hold for Enterprise until more data is collected.  
   - No evidence of degraded downstream conversion.  

---

**Key Findings**  
- Variant B increased SMB outbound Lead → Meeting conversion by +3pp, statistically significant.  
- No degradation in Meeting → Pilot conversion (guardrail metric held).  
- Effect was not uniform: Enterprise and Paid channels showed no lift.  

---

**Decision**  
Ship Variant B for SMB outbound campaigns.  
Hold for Enterprise and Paid channels until further testing.  

---

**Skills Demonstrated**  
- Hypothesis testing (z-test, chi-square)  
- Power and sample size calculation  
- Confidence intervals and effect size interpretation  
- Funnel analysis and guardrail metrics  
- Segment-level analysis (SMB vs Enterprise, channel differences)  
- Python stack: pandas, numpy, scipy.stats, statsmodels, matplotlib, seaborn  
- Business storytelling and stakeholder-ready documentation  

---

**How to Run**  
1. Open `gtm_ab_test_funnel.ipynb` in Google Colab or Jupyter.  
2. Run cells in order: dataset generation → power analysis → primary test → guardrail test → segment analysis.  
3. Review outputs and plots.  
4. Read the narrative cells for business interpretation.  

---

**Conclusion**  
This project showcases GTM-focused A/B testing and funnel analysis. It demonstrates the ability to design experiments, avoid common statistical traps, and translate results into actionable business recommendations. It is positioned as a standout portfolio project for Data Analyst and Data Scientist roles in GTM, sales, and marketing analytics.

---


