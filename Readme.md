<div align="center">

<img src="https://www.sju.edu.in/assets/img/st-joseph-university-logo.png" height="80" style="background:white; padding:8px; margin:0 16px;" />
<img src="https://www.erafoundationindia.org/images/logo.svg" height="80" style="background:white; padding:8px; margin:0 16px;" />
<img src="https://comedkares.org/wp-content/uploads/2023/04/Comedkares-Logo-EPS.png" height="80" style="background:white; padding:8px; margin:0 16px;" />

</div>

---

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

The Indian retail industry is among the fastest-growing sectors globally, with apparel retail representing a major component of both organized and semi-organized markets. Despite this rapid growth in store networks and customer footfall, inventory management at the operational level continues to rely heavily on traditional methods that are manual, reactive, and prone to human error. In many apparel stores, stock counting is typically performed once at the end of each day using handheld barcode scanners. Although this approach has been widely adopted because of its simplicity and low implementation cost, it suffers from several limitations, including labor-intensive operations, delayed discrepancy detection, and an inability to provide real-time information regarding item location and movement. As a result, stores frequently experience stock inconsistencies that negatively affect both operational efficiency and customer satisfaction.

The impact of inefficient inventory management on retail performance has been extensively documented in academic literature. Studies indicate that when customers fail to locate desired products on shelves, a significant proportion of them alter their purchasing behavior. Approximately 31% of customers tend to shift to competing stores, while 26% choose alternative brands, and nearly 9% abandon their purchase entirely. Such patterns contribute not only to immediate sales losses but also to long-term revenue reductions resulting from decreased customer loyalty. When these occurrences are repeated across multiple products and customer interactions over extended periods, the resulting financial impact becomes substantial. In the context of growing apparel retailers, persistent inventory inaccuracies can directly influence sales performance, forecasting accuracy, and overall business sustainability.

To understand these challenges in a practical setting, a field study was conducted at Texs Mart, an apparel retail store located at Gopalan Mall, Sirsi Circle, Bengaluru. During the study, discussions were held with the store floor supervisor, who reported that the store experiences losses of over 1000 items every month without a reliable mechanism to determine the exact cause of these discrepancies. The current inventory process relies entirely on manual barcode-based counting, where staff members compare end-of-day physical stock counts against system records. However, by the time discrepancies are identified, it becomes impossible to determine whether an item was stolen, misplaced by customers, shifted to an incorrect rack, or abandoned in trial rooms. Although CCTV systems and Electronic Article Surveillance (EAS) tags are currently deployed within the store, they offer limited functionality. CCTV systems provide only recorded footage without real-time intervention capabilities, while EAS tags merely trigger generic alarms at store exits without identifying the specific item involved or verifying whether the item was billed.

The limitations of the existing EAS infrastructure reveal a significant technological gap in modern apparel retail inventory systems. Conventional EAS tags have been used for decades as a theft prevention mechanism and are designed primarily to generate alarms when active tags pass through security gates. However, these devices do not possess any data storage or communication capabilities and therefore cannot provide item-level intelligence. In contrast, advancements in Radio Frequency Identification (RFID) technology over recent years have enabled the development of low-cost passive RFID chips capable of storing and transmitting product-specific information. These chips operate without batteries and derive power directly from nearby RFID readers. Furthermore, they can be integrated into existing EAS tag structures without requiring complete replacement of current store infrastructure. Such integration enables a single device to perform both theft prevention and intelligent inventory tracking functions while maintaining a relatively low additional cost.

To demonstrate the practical feasibility of the proposed approach without requiring immediate deployment of physical RFID infrastructure, a software-based simulation environment was developed. The system consists of a real-time dashboard integrated with Firebase Realtime Database and designed for browser-based access. The platform monitors the status and movement of inventory items across multiple locations, including storage racks, billing counters, and exit gates. A parallel simulation engine continuously generates inventory events such as product movement, rack misplacement, billing activity, and theft scenarios, replicating real-world customer and staff interactions within the store environment. The dashboard processes and visualizes these events in real time while automatically generating alerts for inventory anomalies such as theft or misplacement. This implementation provides a realistic demonstration of how RFID-enabled inventory intelligence can improve visibility, reduce losses, and support more efficient retail operations.

---

## Literature Review
<p align="justify">
This study is supported by an extensive review of published research conducted between 2015 and 2025 focusing on inventory management challenges, retail monitoring systems, and intelligent tracking technologies. Existing literature was examined to understand the causes of inventory inaccuracies, the technologies employed to address such challenges, and the strengths and limitations of current approaches. The reviewed studies collectively establish the importance of real-time inventory visibility and provide a foundation for the proposed RFID-based solution.

The concept of On-Shelf Availability (OSA) and Out-of-Stock (OOS) conditions in retail environments was extensively discussed in research published by the International Journal of Computer Applications (2015). The study introduced the concept of Phantom Inventory, a condition in which inventory systems indicate products as available while the physical items are missing due to theft, misplacement, or other factors. The research reported that approximately 25% of out-of-stock situations originate from shelf-level issues rather than actual warehouse shortages. Several approaches for shelf monitoring were evaluated, including QR-based systems, customer-driven mobile applications, RFID technologies, weight-sensing shelves, and image-processing approaches. Although RFID was identified as the most reliable solution, implementation cost was highlighted as a major limitation during that period. Advancements in RFID technology and reductions in component cost now make practical implementation considerably more feasible.

Recent developments in computer vision and deep learning techniques have led to the emergence of intelligent shelf monitoring systems. Research published in Expert Systems with Applications (2024) proposed a camera-based monitoring framework employing RetinaNet, Deep Hough Transform, MobileNetV3, and FAISS algorithms for product detection and shelf monitoring applications. The system achieved detection accuracies of approximately 75.2% for product recognition and 97% for shelf row identification. While these results demonstrate the capability of deep learning approaches for retail applications, several limitations remain in apparel environments. Soft and deformable products such as clothing, overlapping garments, and visually similar items create significant challenges for image-based identification systems. Furthermore, such approaches frequently require retraining and large image datasets whenever new products are introduced.

Alternative approaches based on depth-sensing technologies have also been investigated for inventory monitoring. A study published in IEEE Access (2020) proposed an automated shelf monitoring system utilizing an Intel RealSense D435 depth camera for constructing real-time three-dimensional point cloud representations of shelves. The system estimated product quantities using occupancy measurements rather than visual product recognition and achieved an R-squared value greater than 0.98 with less than one-item estimation error per shelf. Although this approach demonstrated high accuracy in quantity estimation, it lacked the capability to distinguish between sold and stolen items and could not provide item-level identification or misplacement detection.

Research specifically targeting fashion and apparel retail has increasingly focused on Industry 4.0 technologies. A study published in TechRxiv (IEEE) (2025) investigated the impact of RFID, Internet of Things (IoT), artificial intelligence, autonomous mobile robots, digital twin technologies, and warehouse management systems within fashion retail environments. The study reported that RFID implementation reduced scanning errors by approximately 80%, while IoT-enabled systems reduced lost sales by nearly 25%. In addition, warehouse automation technologies demonstrated improvements in operational efficiency and reductions in labor costs. These findings provide significant support for the application of RFID-based technologies in apparel retail inventory systems.

Recent literature has also emphasized intelligent low-stock detection systems using computer vision methods. The Shelf Track system proposed in the Journal of Information Technology and Digital World (2025) employed Faster R-CNN with ResNet-50, optical character recognition, and convolutional neural networks for empty-shelf detection and stock monitoring. The system achieved more than 95% accuracy in empty shelf detection and approximately 92% product label recognition accuracy. However, limitations related to lighting conditions, reflective surfaces, and product orientation were observed. In addition, the system lacked item-level identification capabilities and could not accurately detect theft or product misplacement.

The reviewed literature collectively demonstrates that while substantial progress has been achieved in retail monitoring technologies, significant limitations remain in achieving accurate item-level tracking, theft detection, and misplacement identification in apparel retail environments. RFID technology, particularly when integrated with existing security infrastructure, presents a practical and cost-effective approach capable of overcoming many of these limitations. Consequently, the proposed RFID-based inventory intelligence system seeks to address the shortcomings identified in existing studies while providing real-time visibility and improved operational efficiency.

---

## Objectives
1. To propose a cost-effective hardware upgrade — embedding a passive RFID chip into the existing EAS security tag at an additional cost of ₹10–15 per item — enabling item-level intelligence without replacing any existing store infrastructure.

2. To design and build a real-time software system that tracks every tagged garment from shelf to billing to exit — automatically detecting misplacement when an item appears on the wrong rack, and identifying theft when an unscanned item passes through the exit gate.

---



