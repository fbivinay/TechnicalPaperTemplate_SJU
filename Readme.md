<div align="center">

  <img src="https://www.sju.edu.in/assets/img/st-joseph-university-logo.png"
       height="80"
       style="background:white; padding:8px; margin:0 16px;" />

  <img src="https://www.erafoundationindia.org/images/logo.svg"
       height="80"
       style="background:white; padding:8px; margin:0 16px;" />

  <img src="https://comedkares.org/wp-content/uploads/2023/04/Comedkares-Logo-EPS.png"
       height="80"
       style="background:white; padding:8px; margin:0 16px;" />

</div>

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/en/thumb/7/7c/St._Joseph%27s_University%2C_Bengaluru_logo.png/200px-St._Joseph%27s_University%2C_Bengaluru_logo.png"
       height="80"/>
</p>

<h1 align="center">Smart RFID Inventory Intelligence System</h1

<p align="center">
  <b>Vinay</b>, BDA &nbsp;·&nbsp;
  <b>Keerthi</b>, BDA &nbsp;·&nbsp;
  <b>Divya</b>, MCA &nbsp;·&nbsp;
  <b>Devika</b>, MCA &nbsp;·&nbsp;
  <b>Jerusha</b>, MCA
</p>

---

## Abstract

Retail inventory management is one of the most persistent and financially damaging operational challenges faced by apparel stores in India today. Texs Mart, a growing apparel retail store located at Gopalan Mall, Sirsi Circle, Bengaluru, loses over 1000 items every single month — and has no mechanism to determine whether those items were stolen, misplaced by customers, or simply unaccounted for in their manual inventory system. This situation, known in retail research as Phantom Inventory, occurs when the store management system records an item as available in stock while the item is physically missing from the shelf or the store entirely. The consequences are severe: incorrect reorder decisions, customer dissatisfaction, and direct revenue losses estimated at ₹3,00,000 per month based on an average item value of ₹300.

The store currently relies entirely on manual barcode scanning for stock counts — a process conducted once at the end of each day by floor staff. This approach is slow, error-prone, and fundamentally reactive: by the time the count reveals a discrepancy, the loss has already occurred hours earlier. The only real-time security tool in use is the Electronic Article Surveillance (EAS) tag — a passive security device attached to every garment that triggers a generic alarm at the exit gate if not removed or deactivated at billing. While this tag is present on every item in the store, it provides no item-level information whatsoever. It cannot identify which item triggered the alarm, from which rack the item came, how long ago it was removed from its location, or whether it was billed before exiting.

This project proposes a practical, low-cost solution: upgrading the existing EAS security tag with a passive RFID chip — at an additional cost of only ₹10 to ₹15 per item — to transform it into an intelligent inventory tracking device. Since the EAS tag already exists on every garment, no new hardware infrastructure is required in the store. RFID readers mounted on clothing racks continuously detect tagged items and report their location to a central software system in real time. The system tracks every item across three critical situations: when it is on its correct rack, when it has been moved to the wrong rack by a customer (misplacement), and when it passes through the exit gate without being billed (theft). A live web-based dashboard built on Firebase Realtime Database visualises all of this activity in real time, with automatic alerts for misplacement and theft. A virtual store simulation engine running alongside the dashboard demonstrates all inventory scenarios automatically — simulating customer behaviour, staff actions, and theft events every few seconds — making the system demonstrable without requiring physical RFID hardware during the internship presentation.

The total one-time upgrade cost for 10,000 items is between ₹1,00,000 and ₹1,50,000. Given that the store currently loses ₹3,00,000 every month, the return on investment is achieved in under one month — making this one of the most cost-effective retail technology proposals possible. This project is supported by five peer-reviewed and published academic research papers from 2015 to 2025, all of which confirm the validity of the problem, the limitations of existing solutions, and the effectiveness of RFID in fashion retail environments specifically.

---

## Keywords

RFID, Inventory Management, Retail Shrinkage, Phantom Inventory, On-Shelf Availability, EAS Tag Upgrade, Real-Time Tracking, Apparel Retail, Misplacement Detection, Theft Alert, Firebase, Smart Retail, Out-of-Stock, Fashion Retail Automation

---

## Introduction

### Background

The Indian retail industry is one of the fastest growing in the world, with apparel retail forming a significant segment of organised and semi-organised retail. Despite the growth in store count and footfall, in-store inventory management at the operational level continues to rely on manual, reactive, and error-prone processes. Stock counting is typically done once a day by floor staff using handheld barcode scanners — a method that is labour-intensive, subject to human error, and incapable of providing any real-time visibility into item locations or movements throughout the day.

The consequences of poor inventory management are well-documented in retail research. When a customer cannot find a product on the shelf, research shows that 31% of them go to a competitor store, 26% switch to a different brand, and 9% simply do not purchase at all — representing a direct, permanent revenue loss. When these patterns repeat across thousands of customers and hundreds of SKUs over months and years, the cumulative financial damage is enormous. A single loyal family switching stores permanently represents a potential lifetime revenue loss of over EUR 1,50,000 according to research published in 2015. In the Indian context, even at lower average basket sizes, the aggregate impact on a store like Texs Mart is significant and measurable.

### The Field Research

Our team — Trend Trackers — conducted a direct field visit to Texs Mart, located at Gopalan Mall, Sirsi Circle, Bengaluru. We interviewed Sagar, the floor supervisor, who confirmed that the store loses over 1000 items every month and has no systematic way to track what happens to those items. He described the current process as entirely manual: staff scan barcodes at end of day, compare the count to the system record, and note discrepancies — but by that point, there is no way to determine whether an item was stolen, misplaced by a customer onto the wrong rack, or taken into a trial room and left there. The existing CCTV cameras record footage but provide no real-time alerts and no item-level tracking. The EAS security tag triggers an alarm at the exit but gives no information about which item caused the alarm or whether it was billed.

This field observation formed the foundation of our problem statement and directly shaped the design of our proposed solution.

### The Technology Gap

The EAS security tag is a standard fixture in apparel retail globally. It has been in use for decades and is specifically designed to prevent shoplifting by triggering an alarm when an active tag passes through the exit gate. However, the EAS tag in its current form is a completely passive and unintelligent device. It stores no data, communicates no information, and provides no insight beyond the binary signal of "active tag detected at exit."

Meanwhile, RFID (Radio Frequency Identification) technology has matured significantly over the past decade. Passive UHF RFID chips — which require no battery and are powered by the radio signal from a nearby reader — are now available at costs as low as ₹8 to ₹15 per chip in bulk. These chips can store item-level data including product ID, name, size, price, and assigned rack location. They can be embedded into the existing hard plastic casing of an EAS tag without replacing it, combining both functions — the theft alarm of the EAS tag and the intelligence of the RFID chip — in a single upgraded device. This is the central insight of our proposal: we are not asking the store to replace their existing security infrastructure. We are asking them to upgrade what they already have, at minimal additional cost, to gain transformative inventory intelligence.

### The Software Solution

To demonstrate the proposed system without requiring physical RFID hardware during the internship presentation, we built a complete software simulation: a live web-based dashboard connected to Firebase Realtime Database, accessible from any browser anywhere in the world. The dashboard shows the real-time location and status of every item in the store across three racks (Rack A, Rack B, Rack C), a billing counter, and an exit gate. A simulation engine running in a separate browser tab automatically triggers inventory events every few seconds — moving items between racks, sending items to billing, and simulating theft — exactly as events would occur in a real store with RFID readers. The dashboard updates in real time as each event occurs, demonstrating misplacement alerts and theft alerts visually and clearly. All source code is hosted publicly on GitHub and the live website is deployed on GitHub Pages, making the project fully accessible and verifiable by evaluators.

---

## Literature Review

This project is grounded in five published research papers spanning 2015 to 2025. Each paper was studied for its relevance to the inventory management problem in retail, the technologies it proposed or evaluated, the results it achieved, and — most importantly — how it either validates our proposed solution or reveals the limitations of alternative approaches.

---

### Paper 1 — On-Shelf Availability in Retailing
**Source:** International Journal of Computer Applications (IJCA), Volume 116, No. 23, April 2015 | DOI: IJCA Vol 116, No.23, 2015 | NMIMS University, Mumbai

This foundational paper introduced the concept of On-Shelf Availability (OSA) and Out-of-Stock (OOS) conditions in retail, and was the first paper we studied because it directly defines the problem our project solves. The paper established that 25% of all Out-of-Stock conditions are shelf-level problems — meaning the item exists in the warehouse or storeroom but is physically absent from the shelf when the customer wants to buy it. This is precisely what happens at Texs Mart when items are stolen or misplaced. The paper also introduced the concept of Phantom Inventory — where the inventory management system records an item as in stock even though it is physically not present, due to theft, damage, or misplacement. This is the exact condition confirmed by our field interview with Sagar.

The paper evaluated five existing solutions for shelf monitoring: QR codes (require customer to scan empty shelf — too customer-dependent), mobile apps (require customer to photograph and report — impractical), RFID (most reliable, but expensive at the time), weight sensor shelves (cannot detect misplaced items, cannot sense very light items), and camera-based image processing (requires cameras on every shelf, high setup cost). The paper concluded RFID as the most reliable technology but flagged cost as the main barrier. Our project directly addresses this barrier: since EAS tags already exist on every garment at Texs Mart, the only additional cost is the RFID chip — ₹10 to ₹15 per item — making the expensive RFID objection of 2015 obsolete in 2025. This paper identified the problem a decade ago. We built the solution today.

---

### Paper 2 — Shelf Management: A Deep Learning-Based System for Shelf Visual Monitoring
**Source:** Expert Systems With Applications, Volume 255, 2024 | DOI: 10.1016/j.eswa.2024.124635

This paper proposed an automated AI-powered camera system for retail shelf monitoring using multiple deep learning models: RetinaNet for product detection (75.2% mAP), Deep Hough Transform for automatic shelf row detection (97% F1 score), MobileNetV3 combined with Triplet Loss for product recognition (93% Top-1 accuracy), and FAISS for high-speed product embedding search (0.41ms per query). The system was designed to automatically audit shelves, detect missing products, and identify misplaced items by comparing shelf images against a reference planogram.

This paper helped our project in two important ways. First, it confirmed that the shelf monitoring problem is significant enough for top-tier academic journals to publish major research solutions for it — validating the importance of our project domain. Second, and more critically, it revealed the fundamental limitations of camera-based approaches for apparel retail specifically. A 75.2% detection rate means one in every four products goes undetected — an unacceptable error rate for inventory control. More importantly, camera-based systems struggle fundamentally with soft fabric that deforms when folded or hung, stacked or overlapping clothing items, and similar-colored garments that confuse visual recognition models. Every new product added to the store requires new reference images and potential model retraining. Our RFID solution bypasses all of these computer vision challenges entirely: the chip does not need to visually identify the garment — it simply needs to exist on it, which it already does at Texs Mart. This paper strengthens our argument by proving that the most advanced alternative to our approach still has critical limitations in the apparel context.

---

### Paper 3 — Towards Intelligent Retail: Automated On-Shelf Availability Estimation Using a Depth Camera
**Source:** IEEE Access, 2020 | DOI: 10.1109/ACCESS.2020.2968175

This paper used an Intel RealSense D435 depth camera to build a real-time 3D point cloud model of retail shelves. Unlike the previous paper which relied on visual product recognition, this system estimated shelf occupancy purely by measuring the physical volume of items on the shelf — making it product-agnostic and requiring no prior training on specific items. The system achieved less than one item estimation error per shelf, an R-squared value greater than 0.98 for quantity estimation, and a maximum discrepancy of 5% even for difficult items like fruit. The technologies used included RGB-D imaging, 3D point cloud reconstruction, occupancy grid modeling, and MSAC/MLESAC plane-fitting algorithms.

This paper was directly useful to our project because it validated that real-time automated stock level estimation is practically achievable, which supported the design of our dashboard's low-stock alert feature. When our RFID system detects that the number of tagged items on a rack has dropped below a set threshold, it automatically alerts store staff — the same outcome this paper's depth camera system achieves, but using the RFID reader infrastructure instead of expensive 3D cameras. However, this paper also highlighted what depth-camera systems cannot do: they cannot distinguish between a sold item and a stolen one, cannot identify individual garments, and cannot detect misplacement — all three of which our RFID system handles precisely. This paper confirmed automated inventory monitoring as a viable and necessary retail solution, while simultaneously showing the limitations that make RFID the superior approach for garment-level tracking.

---

### Paper 4 — Smart Inventory and Warehouse Automation for Fashion Retail
**Source:** TechRxiv (IEEE), 2025 | DOI: 10.36227/techrxiv.175987210.04689809/v1

This is the most directly relevant paper to our project because it specifically targets fashion and apparel retail — the same industry domain as Texs Mart. The paper examined how Industry 4.0 technologies including RFID, IoT, AI and machine learning, Autonomous Mobile Robots (AMRs), Blockchain, Digital Twin technology, Cloud Computing, and Warehouse Management Systems (WMS) can transform traditional fashion retail operations. Crucially, the paper reported quantified outcomes from real implementations: RFID reduced scanning errors by 80%, IoT integration reduced lost sales by 25%, robotics increased warehouse throughput by 30 to 40%, AI demand forecasting reduced overstock by 20%, and warehouse automation cut labour costs by 25 to 30%.

The 80% reduction in scanning errors from RFID implementation in fashion retail specifically is the single strongest academic validation of our core proposal. This is not a grocery store result or a general retail result — it is from fashion retail, from the same type of store we are proposing the solution for. This paper also makes our project academically credible by demonstrating that what we are proposing is not experimental or unproven — RFID has already been implemented in fashion retail at scale globally and the results are documented. Our project takes the most cost-effective and immediately deployable subset of this technology stack — RFID tagging combined with IoT dashboard and real-time alerting — and applies it to the specific context of a growing Indian apparel store where the existing EAS tag infrastructure makes the entry cost minimal.

---

### Paper 5 — Shelf Track: Intelligent Empty Shelf and Low-Stock Monitoring System
**Source:** Journal of Information Technology and Digital World, Volume 7, Issue 3, Pages 216–226, August 2025 | DOI: 10.36548/jitdw.2025.3.002

This paper proposed an AI system called Shelf Track that uses Faster R-CNN with a ResNet-50 backbone for empty shelf detection, Tesseract OCR for product label reading, and a CNN classifier for product categorisation — achieving over 95% empty shelf detection accuracy and 92% OCR product label recognition accuracy. The system was designed to automatically detect when shelves are empty or running low and generate restocking alerts without requiring manual staff involvement.

This paper directly validated the low-stock alert feature in our dashboard. When our RFID system counts fewer than a set minimum number of tagged items on a rack, it automatically notifies staff — achieving the same outcome as Shelf Track's camera-based approach, but without the limitations. Shelf Track explicitly noted that its system struggles under poor lighting conditions, with reflective packaging, and with unusual product orientations — all common challenges in apparel retail. More significantly, their system cannot identify individual stolen items, cannot detect misplacement at the garment level, and cannot provide billing cross-reference for theft detection. Our RFID system does all of this, and it does so without cameras, without lighting dependency, without model retraining, and with zero privacy concerns since no visual data of customers is captured. This 2025 paper — published just months before our project — confirms that the problem we are solving remains an active and unsolved research challenge, and that our approach offers meaningful advantages over the current state of the art.

---

## Objectives

1. To propose a cost-effective hardware upgrade — embedding a passive RFID chip into the existing EAS security tag at an additional cost of ₹10–15 per item — enabling item-level intelligence without replacing any existing store infrastructure.

2. To design and build a real-time software system that tracks every tagged garment from shelf to billing to exit — automatically detecting misplacement when an item appears on the wrong rack, and identifying theft when an unscanned item passes through the exit gate.

---



