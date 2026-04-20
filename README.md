# Pharmaceutical-Payments-Analysis
Pharmaceutical Payments and Physician Prescribing Behavior in the United States

The United States healthcare system is characterized by expenditures that significantly exceed those of other
developed nations. In 2023, healthcare spending accounted for 17.6% of the US GDP1, a proportion that is
almost double that of the OECD countries’ average of around 9.2%. A notable component of this spending is
attributed to prescription drugs, which represent a growing share of national health expenditures. Within
this context, the financial relationships between pharmaceutical manufacturers and physicians have earned
substantial attention. These relationships, which often involve payments for activities such as consulting,
speaking engagements, and meals, are documented in the Centers for Medicare & Medicaid Services (CMS)
Open Payments database.


A prevailing hypothesis is that such financial transfers may influence physicians’ prescribing behavior, potentially favoring more expensive brand-name drugs and thereby contributing to increased healthcare costs, particularly within public insurance programs like Medicare. Prior studies have documented associations between industry payments and physician behavior, but the strength and nature of these relationships remain debated. Some research suggests that even small-value items, such as meals, may affect prescribing decisions,
while other studies emphasize the impact of larger payments such as consulting fees or honoraria.


Understanding the dynamics of these interactions is particularly important for Medicare Part D, which
provides prescription drug coverage to over 46 million beneficiaries. Since Part D represents one of the
largest components of federal healthcare spending, any systematic influence of pharmaceutical payments on
prescribing behavior has implications not only for cost efficiency but also for equity and patient welfare.
Against this backdrop, this project seeks to empirically examine two central questions:
(1) What is the relationship between the total monetary value of pharmaceutical payments physicians receive
and the total cost of prescriptions they write?
(2) How do different categories of payments—such as consulting fees, honoraria, or food and beverage—
respectively affect prescribing behavior at the physician level?


By linking physician-level Open Payments data with prescription activity under Medicare Part D, this study
aims to shed light on the mechanisms through which financial incentives shape medical decision-making and,
in turn, to inform ongoing policy debates on cost containment and ethical standards in healthcare. In this
study, we specifically focus on how the pharmaceutical payments physicians receive affect the total cost of
prescriptions they write, while including the number of unique patients attributed to the physician as a
control variable to account for differences in patient load. We will also provide intuitive visualizations to
facilitate understanding of the payments and prescriptions.


Primary Dataset
Source: CMS Open Payments (https://openpaymentsdata.cms.gov/)
The data originates from the CMS Open Payments program, a national transparency initiative mandated
by the Affordable Care Act. It requires drug and medical device companies to systematically report all
financial payments made to physicians and teaching hospitals. This information is collected directly from
these companies, reviewed by the recipients, and then published publicly by CMS.
Content: The dataset contains detailed records of financial transactions from pharmaceutical and medical
device manufacturers to individual physicians and other entities. Each record documents the payment
amount, payment type, date, and other contextual information such as the reporting company and the
purpose of the payment.
Key variables:
• Total Payment Amount (numeric): Dollar value of individual or aggregated transfers.
• Recipient Type (categorical): Indicates whether the payment recipient is an individual physician, hospital, or other entity. Only records with physicians are retained for analysis.
• Payment Type (categorical): Classification of transfer (e.g. consulting fees, food & beverage, travel,
speaking honoraria).
• Physician Identifier (NPI): Unique identifier for each physician, enabling linkage with prescribing data.
• Primary Specialty (categorical): The main clinical specialty of the physician. This variable allows
controlling for inherent differences in prescribing patterns across specialties.


Secondary Dataset: Medicare Part D Prescribers by Provider 2023
Source: CMS Medicare Part D Prescriber Public Use File (https://data.cms.gov/provider-summary-bytype-of-service/medicare-part-d-prescribers/medicare-part-d-prescribers-by-provider)
Content: The dataset provides physician-level summaries of prescribing activity under Medicare Part D,
which covers outpatient prescription drugs. It includes both the volume and the cost of prescriptions attributed to each physician.
Key variables:
• Prescription Count (numeric): Total number of prescriptions filled under Part D.
• Total Drug Cost (numeric): Aggregate spending on prescribed medications.
• Number of Beneficiaries (numeric): Count of unique patients receiving prescriptions from the physician.
• Physician Identifier (NPI): Unique identifier for each physician; used to merge with the primary
dataset.
