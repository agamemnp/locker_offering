# Pilot Proposal: Athens Hub Injection to Athens Lockers

## 1. Overview

Based on the provided pricing structures and service components, we propose a pilot project to route parcels from the Athens hub (hub injection) directly to Athens lockers. This initiative will help us validate both the operational efficiency and technical integration of locker-based delivery while ensuring cost-effectiveness and a seamless customer experience.

---

## 2. Service Components & Pricing Tables

### Component Table

| Component Code | Component Name                      | Dependency         | Description                                                                                                                                                       | Pricing   | Offer                                          |
|----------------|-------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|------------------------------------------------|
| PC             | Pickup Cost                         | Pickup Density     | Charge per voucher per order based on pickup effort                                                                                                               | Table 1   | N/A                                            |
| LHWC           | Network Cost                        | Origin-Destination | Cost based on the route between origin and destination zones                                                                                                      | Table 2   | 40% Discount for hub injection               |
| LHWH           | Local Hub-to-Hub Delivery           | Athens-to-Athens   | Cost based on the route between local hubs within Athens. A 40% discount is applied for Athens-to-Athens deliveries.                                                  | Table 2   | ✔️ (40% Discount for Athens-to-Athens)         |
| SLC            | Locker Standard Service             | –                  | Locker delivery with a standard SLA of **1–5 days** from dispatch, with a **guaranteed 1-day** delivery after pickup from the warehouse                          | €0.90     | ✔️                                             |
| ELC            | Locker Express Service              | –                  | Locker delivery with an express SLA (1 day)                                                                                                                       | €1.80     | ✔️                                             |
| LSC            | Locker Slot Size Charge             | –                  | Extra cost for the smallest available locker slot                                                                                                                 | Table 3   | ✔️                                             |
| EHC            | Express Home Delivery               | –                  | Express home delivery service                                                                                                                                       | €2.70     | N/A                                            |
| SHC            | Standard Home Delivery Service      | –                  | Standard home delivery service                                                                                                                                      | €1.20     | N/A                                            |
| HSC            | Home Parcel Size Charge             | –                  | 0€ up to 3kg; €0.80 per extra kg beyond 3kg                                                                                                                         | €0.80 per extra Kg | N/A                                   |
| RC             | Remote Charge                       | –                  | Extra charge for remote delivery                                                                                                                                    | €2.00     | N/A                                            |
| CC             | COD Charge                          | –                  | Extra charge for Cash on Delivery (COD)                                                                                                                             | €1.00     | N/A                                            |
| SC             | Customer Support & Messaging Charge | –                  | Charge for phone support and transactional SMS                                                                                                                    | €0.10     | N/A                                            |

---

### Table 1: Pickup Cost & Locker Drop-off Charges

| Charge Description       | Charge in EUR |
|--------------------------|---------------|
| Locker Drop-off          | €0.10         |
| Hub Injection            | €0.00         |
| > 25 pickups/Stop        | €0.00         |
| >= 10 pickups/Stop       | €0.30         |
| >= 5 pickups/Stop        | €0.60         |
| <= 4 pickups/Stop        | €1.30         |

---

### Table 2: Network Cost by Zone

|           | Zone_0 | Zone_1 | Zone_2 |
|-----------|--------|--------|--------|
| **Zone_0**| €0.45  | €0.75  | €1.25  |
| **Zone_1**| €0.75  | €0.45  | €1.25  |
| **Zone_2**| €1.25  | €1.25  | €1.55  |

---

### Table 3: Locker Slot Size Charge

| Slot Size | Charge in EUR |
|-----------|---------------|
| S         | €0.00         |
| M         | €0.20         |
| L         | €0.40         |

---

## 3. Pilot Proposal Details

### Service Flow

- **Hub Injection to Locker Delivery:**  
  The pilot will implement a service flow where parcels are routed from the Athens hub through a hub injection process to designated Athens lockers. Both the standard and express locker services (SLC and ELC) will be available to cater to different delivery urgency levels.

- **Pricing Application:**  
  - **Locker Delivery:**  
    - **Standard Service (SLC):** Priced at €0.90, with a Service Level Agreement (SLA) of **1–5 days** from dispatch and a **guaranteed 1-day** delivery after pickup from the warehouse.  
    - **Express Service (ELC):** Priced at €1.80 with a 1-day SLA.
  - **Additional Charges:**  
    - Pickup costs, network costs, and locker slot size charges are applied as per the relevant tables.
  - **Discounts:**  
    - A 40% discount is applied on both the LHWC component (for hub injection) and the LHWH component (for Athens-to-Athens local hub deliveries).

---

## 4. Technical Issues

- **API Requirements:**  
  - The API must capture either a **Locker ID** or a complete **address string** when initiating a delivery request.
  - It should include an option to specify whether the delivery service is **express** or **standard**.

- **Barcode and Voucher Specifications:**  
  - Further discussion is required on the specifics regarding the **barcode number** and **voucher specifications**.
  - The customer’s voucher will serve as a unique identifier for tracking purposes.

- **Tracking & Integration:**  
  - Real-time tracking will be facilitated via API calls and web hook notifications.
  - Current locker availability and an interactive locker map can be accessed via the provided link.

---

## 5. Invoicing and Pricing Calculation

- **Monthly Invoicing:**  
  - Invoices will be generated at the end of each month, covering all usage to date.
  
- **Post-Factum Pricing Calculation:**  
  - Final pricing will be calculated after a comprehensive review of the monthly usage data.
  - Detailed invoices with a breakdown of charges will be available through the designated link.

---

## 6. Next Steps

- **Technical Discussion:**  
  - Schedule a meeting to discuss API requirements, particularly regarding locker IDs/address strings, barcode numbers, and voucher specifications.
  
- **Pilot Setup:**  
  - Finalize the operational framework and logistics for the Athens hub injection to Athens lockers.
  - Provide stakeholders with access to the locker availability map and API documentation.

- **Monitoring & Reporting:**  
  - Implement real-time tracking via API and web hooks.
  - Prepare monthly usage reports to ensure transparent invoicing and ongoing process improvements.

---

## 7. Example Pricing Calculation (Using Offered Components)

For illustration, the following example pricing calculation combines the LHWH, SLC, and LSC components:

- **Local Hub-to-Hub Delivery (LHWH):**  
  - For an Athens-to-Athens route (e.g., from Zone_0 to Zone_0), the standard cost is **€0.45** (from Table 2).  
  - **Discount Application:** With a 40% discount, the cost becomes:  
    \[
    €0.45 \times 0.60 = €0.27
    \]

- **Locker Standard Service (SLC):**  
  - Base Price: **€0.90**

- **Locker Slot Size Charge (LSC):**  
  - Assuming a medium slot is used: **€0.20**

- **Total Price Calculation:**  
  \[
  LHWH + SLC + LSC = €0.27 + €0.90 + €0.20 = €1.37
  \]

Thus, the combined cost for a delivery using LHWH, SLC, and LSC is **€1.37**.

---
