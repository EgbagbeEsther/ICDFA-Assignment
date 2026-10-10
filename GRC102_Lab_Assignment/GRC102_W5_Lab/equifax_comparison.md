# Comparison of the Simulated Environment to the Equifax Data Breach

## Overview
This report compares the governance failures I found in my simulated environment with those behind the 2017 Equifax breach. That breach exposed the personal data of about 147 million people.

## Key Governance Failures at Equifax
1. **Patch management:** The Apache Struts flaw (CVE-2017-5638) was disclosed in March 2017 and a patch was available. Equifax did not apply it for months. It relied on one person to patch manually and had no full asset inventory.
2. **Security monitoring:** The breach went undetected for 76 days. An expired certificate stopped the team from inspecting network traffic.
3. **Leadership and accountability:** Security duties were delegated without enough oversight, and the board did not challenge the risks enough.
4. **Policy implementation:** Equifax did not follow its own security policies.

## Comparison with My Environment
| Governance failure | Equifax | My simulated environment | Similarity |
|---|---|---|---|
| Patch management | Struts patch not applied for months | My scan flagged the Struts 2.3.30 container as Critical | High |
| Security monitoring | Breach undetected for 76 days | My simulated attack succeeded and nothing raised an alert | High |
| Policy implementation | Policies not enforced | Patch and vulnerability policies exist in my tracker, but the flaws remained | High |
| Authentication | Weak access controls | MySQL accepted the default root password (High finding) | Medium |
| Network segmentation | Attackers moved sideways inside the network | 
| Metrics | Ineffective security measures | Patch compliance was 85% against a 95% target, and remediation took 12 days against a 7-day target | Medium |

## Lessons Learned
The biggest lesson for me is that a policy on paper does not protect anything. Equifax had a patch policy, and so did my lab, but the Struts flaw stayed open in both. My tracker listed a Patch Management Policy, yet my scan still found a Critical flaw and my attack simulation succeeded.

The Struts flaw was only the way in. What turned it into a breach was everything around it: no one checking that the patch was applied, no monitoring to catch the attack, and weak access controls on the database. My analysis found 8 governance failures, and only 2 were filed under patch management. If I were fixing this lab, I would start by patching the Struts flaw and changing the default database password, because those are the easiest weaknesses to exploit. Then I would add monitoring and give each control a clear owner.

## Limitations
My environment is a simulation. The attack script only prints simulated steps, and the analysis script uses fixed rules, so some failures were assumed and not tested. I checked network segmentation by hand because the scanner's check crashed. The dashboard also marks remediation time and incident count as Green even though both miss their targets.

## Reference
U.S. House of Representatives Committee on Oversight and Government Reform. (2018). *The Equifax Data Breach.* https://republicans-oversight.house.gov/wp-content/uploads/2018/12/Equifax-Report.pdf
EOF
