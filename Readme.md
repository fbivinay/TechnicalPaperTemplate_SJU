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
 
The apparel retail sector continues to face persistent challenges related to inventory accuracy, real-time item visibility, and shrinkage management. Traditional inventory practices, which rely primarily on manual barcode scanning and periodic stock audits, are fundamentally reactive in nature and are unable to provide continuous, item-level awareness of product location and movement within a store environment. Electronic Article Surveillance (EAS) tags, which are currently attached to garments in most apparel stores, function solely as theft deterrents through generic exit alarms and do not contribute to inventory intelligence in any meaningful way. This limitation results in a condition referred to in retail literature as Phantom Inventory, where the store management system records items as available while the physical items are misplaced, stolen, or otherwise unaccounted for on the sales floor.
 
This paper presents a conceptual framework for an intelligent inventory system designed specifically for apparel retail environments. The proposed system is centered on the upgrade of existing EAS security tags through the integration of passive Radio Frequency Identification (RFID) chips, transforming each garment tag from a simple alarm trigger into a data-carrying, location-aware inventory device. RFID readers positioned at clothing racks, billing counters, and store exit gates continuously communicate with these upgraded tags to monitor the real-time status and location of every garment in the store. The framework defines three core tracking states for each item: correctly placed on its assigned rack, moved to an incorrect rack by a customer or staff member, and exited through the store gate without a corresponding billing record. Each state transition generates an automatic system response, including dashboard alerts for misplacement and theft identification at the exit gate.
 
To support practical demonstration of the proposed framework, a software-based simulation environment has been developed. This environment consists of a real-time web dashboard connected to a cloud-hosted database, alongside a simulation engine that replicates store inventory events such as item movement, billing activity, and exit gate scanning. The dashboard provides continuous visibility into rack-level inventory status and generates real-time alerts for anomalies. The proposed framework is intended as a conceptual foundation for RFID-based inventory intelligence in apparel retail, with the software simulation serving as a proof-of-concept implementation that demonstrates the system's operational logic without requiring physical RFID deployment.
 
---
 
## Keywords
 
RFID, Inventory Intelligence, Apparel Retail, EAS Tag Integration, Phantom Inventory, On-Shelf Availability, Real-Time Tracking, Misplacement Detection, Theft Identification, Firebase, Dashboard, Conceptual Framework, Retail Shrinkage, IoT
 
---
 
## 1. Introduction
 
The apparel retail industry operates in a highly dynamic environment characterized by large product volumes, high customer interaction with merchandise, and significant exposure to inventory losses through misplacement and theft. Unlike packaged goods retail, apparel stores present unique inventory management challenges due to the physical nature of garments — customers frequently handle, try on, and reposition items, resulting in a store environment where product location is inherently unstable. These characteristics make real-time inventory visibility both more difficult and more important than in other retail categories.
 
Inventory management in most apparel stores continues to rely on manual processes. Stock counting is typically carried out once per day at store closing, during which staff use handheld barcode scanners to count items and compare physical counts against system records. While this approach has been widely adopted due to its simplicity and low cost of implementation, it has several fundamental limitations. First, it provides no real-time information — discrepancies are discovered hours after they occur, by which time intervention is no longer possible. Second, it is labor-intensive and subject to human error. Third, it cannot distinguish between different causes of stock discrepancy, such as theft, misplacement, or items left in trial rooms. As a result, store managers are left with aggregate loss figures at the end of each day but no actionable intelligence about when, where, or how those losses occurred.
 
The Electronic Article Surveillance (EAS) tag is the most widely deployed security technology in apparel retail. Attached to every garment, the EAS tag is designed to trigger an alarm when an active tag passes through detection gates at store exits, with the intent of deterring theft. However, the EAS tag in its conventional form is entirely passive with respect to inventory management. It stores no product information, communicates no location data, and provides no input to the store's inventory system. When an EAS alarm triggers, the system knows only that an active tag has been detected at the exit — it cannot identify which item, from which rack, or whether billing was attempted. In the context of a misplaced item, the EAS tag offers no functionality at all.
 
Radio Frequency Identification (RFID) technology presents a well-established alternative that addresses many of the limitations inherent in barcode-based inventory systems and conventional EAS infrastructure. Passive RFID chips, which derive power from the electromagnetic field emitted by nearby RFID readers, can store item-level data and respond to reader queries without requiring line-of-sight or manual scanning. RFID readers can detect multiple tags simultaneously across a defined range, enabling automated, continuous inventory monitoring without staff involvement. Importantly, passive RFID chips can be physically integrated into existing EAS tag housings, enabling a single device to perform both the theft deterrence function of the EAS tag and the inventory intelligence function of an RFID tag. This integration approach eliminates the need to replace existing store security infrastructure and allows the proposed system to be adopted incrementally.
 
A field study conducted at Texs Mart, an apparel retail store located at Gopalan Mall, Sirsi Circle, Bengaluru, revealed that the store experiences consistent monthly inventory discrepancies with no available mechanism to identify their root cause. Store staff confirmed that the current process is entirely manual and provides no real-time visibility into item location or movement. The findings from this field study motivated the development of the conceptual framework presented in this paper, which proposes RFID-based inventory intelligence as a practical and implementable solution for apparel retail environments of this nature.
 
To demonstrate the operational logic of the proposed framework without requiring physical RFID infrastructure, a software simulation has been developed. The simulation consists of a real-time dashboard built on Firebase Realtime Database and a simulation engine that automatically generates inventory events — including item movement between racks, billing transactions, and exit gate scanning — replicating the behavior of a live RFID-enabled store environment. The dashboard visualizes all inventory states and alerts in real time, providing a functional proof-of-concept of the proposed system's capabilities.
 
---
 
## 2. Literature Review
 
This study is informed by a review of published research conducted between 2015 and 2025, examining inventory management challenges in retail environments, the application of RFID and related technologies to inventory tracking, and the development of intelligent monitoring systems for shelf availability and stock management. The reviewed literature collectively establishes the context for the proposed framework and identifies the limitations of existing approaches that the present work seeks to address.
 
Research published in the International Journal of Computer Applications (2015) provided foundational insight into the concept of On-Shelf Availability (OSA) and Out-of-Stock (OOS) conditions in retail. The study introduced the notion of Phantom Inventory — a condition in which the inventory management system records items as available while the physical products are absent from the shelf due to misplacement, theft, or other causes. The research noted that a significant proportion of out-of-stock situations originate at the shelf level rather than from actual warehouse shortages, and that this distinction is critical for designing effective inventory interventions. Several monitoring technologies were evaluated, including QR-based customer-reporting systems, mobile applications, RFID tagging, weight-sensing shelves, and camera-based image processing. While RFID was identified as the most reliable approach for automated inventory monitoring, the study highlighted implementation cost as a primary constraint. The present framework addresses this concern by proposing integration of RFID functionality into existing EAS tag infrastructure rather than deploying RFID as an entirely new system, thereby reducing the incremental cost of adoption.
 
Research published in Expert Systems with Applications (2024) proposed a deep learning-based shelf monitoring system employing computer vision techniques for automated product detection and misplacement identification. The system utilized multiple neural network architectures including RetinaNet for object detection, Deep Hough Transform for shelf structure analysis, and MobileNetV3 with triplet loss for product recognition. While the reported detection metrics demonstrated the technical capability of image-based monitoring approaches, the study also acknowledged challenges inherent to apparel retail environments, including the deformable nature of fabric items, visual similarity between garments, and the need to retrain models when new products are introduced. These characteristics make camera-based approaches less directly applicable to the apparel context than to grocery or packaged goods retail, where products have stable visual appearances and fixed orientations.
 
A study published in IEEE Access (2020) explored the use of depth-sensing technology for automated shelf occupancy estimation. The proposed system employed an Intel RealSense depth camera to construct three-dimensional representations of shelf contents and estimate product quantities based on physical volume rather than visual product recognition. The approach demonstrated strong performance in quantity estimation across diverse product types without requiring product-specific training. However, the study acknowledged that the system was unable to distinguish between sold and stolen items, could not identify individual products, and was not designed for misplacement detection at the item level. These limitations are particularly significant in the apparel context, where item-level identification and cause-of-loss differentiation are important operational requirements.
 
Research published in TechRxiv (2025) examined the application of Industry 4.0 technologies to fashion retail inventory and warehouse management. The study proposed a conceptual framework integrating IoT sensors, RFID tagging, artificial intelligence, autonomous robotic systems, blockchain, and digital twin technologies to address inventory inaccuracies and operational inefficiencies in fashion retail supply chains. The findings reported in the study indicated that RFID-enabled tracking systems have demonstrated significant reductions in inventory scanning errors and improvements in real-time stock visibility in implementations documented across the retail sector. The study emphasized that RFID, when combined with IoT infrastructure and intelligent dashboards, represents a scalable and practical solution for the inventory visibility challenges characteristic of fashion and apparel retail. The present framework draws directly from this conceptual foundation, focusing specifically on the store-level implementation of RFID inventory intelligence as distinct from the broader supply chain and warehouse automation scope of that study.
 
Research published in the Journal of Information Technology and Digital World (2025) proposed the Shelf Track system, an AI-driven framework for empty shelf detection and low-stock monitoring using convolutional neural networks and optical character recognition. The system demonstrated strong accuracy in detecting empty shelves and identifying product labels under controlled conditions. However, the study noted performance limitations under variable lighting conditions, with reflective packaging, and for products positioned at non-standard orientations. Additionally, the system was designed for shelf-level stock monitoring and did not incorporate item-level identification, theft detection logic, or misplacement tracking. The low-stock alert concept demonstrated in this study is directly relevant to the proposed framework, which incorporates a similar alert mechanism triggered by RFID-based rack-level item count monitoring rather than camera-based shelf image analysis.
 
The reviewed literature collectively indicates that while substantial research has addressed retail inventory monitoring from multiple technological perspectives, significant gaps remain in achieving item-level tracking, theft identification, and misplacement detection in apparel retail environments using approaches that are compatible with existing store infrastructure. The proposed framework seeks to address these gaps by leveraging RFID technology in a manner that integrates with, rather than replaces, the EAS systems already deployed in apparel stores.
 
---
 
## 3. Problem Statement
 
Apparel retail stores face a persistent inventory management challenge characterized by the inability to obtain real-time, item-level visibility into product location and movement on the sales floor. Existing inventory practices based on manual barcode scanning provide only periodic, aggregate stock counts and cannot detect misplacement events, identify theft at the item level, or differentiate between causes of inventory discrepancy. EAS tags, while universally deployed in apparel retail as theft deterrents, do not contribute to inventory intelligence and provide no information about item identity, location within the store, or billing status at the exit gate.
 
This combination of reactive manual processes and unintelligent security infrastructure results in a condition in which store operators have awareness of aggregate inventory losses only after they have occurred, with no mechanism to determine their cause, timing, or location. The proposed framework addresses this problem by defining a system architecture in which existing EAS tags are upgraded with RFID functionality, enabling continuous, automated, item-level inventory monitoring without replacing current store security infrastructure.
 
---
 
## 4. Proposed System Framework
 
### 4.1 RFID Tag Integration
 
The core component of the proposed framework is the integration of a passive RFID chip into the housing of the existing EAS security tag attached to each garment. This integration enables a single tag to perform both the alarm function of the conventional EAS tag and the data communication function of an RFID device. Each upgraded tag stores item-level information including a unique item identifier, product category, size designation, assigned rack location within the store, and current status. The tag operates passively, drawing power from the electromagnetic field emitted by nearby RFID readers, and requires no battery or active power source.
 
This integration approach is central to the practical feasibility of the proposed framework. By utilizing the EAS tag infrastructure already present on every garment in the store, the system avoids the need to introduce an entirely new tagging process and allows RFID capability to be added incrementally to existing inventory.
 
### 4.2 RFID Reader Infrastructure
 
RFID readers are proposed for deployment at three locations within the store: mounted on or adjacent to each clothing rack, positioned at the billing counter, and integrated into the existing EAS detection gates at store exits. Rack-mounted readers continuously scan for tags within their detection range, enabling the system to maintain an ongoing, automatically updated record of which items are present on each rack. Readers at the billing counter detect tags as garments are processed for sale, updating item status to reflect completed billing transactions. Exit gate readers detect tags as customers pass through, enabling cross-reference against billing records to identify items leaving the store without a corresponding sale.
 
### 4.3 Three-State Inventory Tracking Model
 
The proposed framework defines a three-state model for tracking each garment's inventory status throughout the store environment.
 
In the first state, an item is detected by the reader associated with its assigned home rack. This state indicates that the item is correctly positioned and available for customer purchase. The dashboard reflects this state as normal inventory.
 
In the second state, an item is detected by a reader associated with a rack other than its designated home rack. This state indicates that the item has been moved to an incorrect location, either by a customer who handled the item and replaced it on the wrong rack, or through other means. The system identifies this condition automatically by comparing the detecting reader's location against the item's stored home rack assignment and generates a misplacement alert for store staff.
 
In the third state, an item's tag is detected at the exit gate reader while the item's billing status remains unconfirmed in the system record. This state indicates that the item has left the store without a completed billing transaction, which the framework treats as a theft event. The system generates an immediate alert identifying the specific item, its most recently recorded rack location, and the time of exit gate detection.
 
### 4.4 Dashboard and Software Implementation
 
The proposed framework includes a software layer consisting of a real-time inventory dashboard and a cloud-hosted database. The dashboard provides store management with continuous visibility into rack-level inventory counts, item status across all three tracking states, and a timestamped activity log of all inventory events. Alert notifications for misplacement and theft events are displayed in real time as the relevant state transitions are detected by the reader infrastructure.
 
A simulation environment has been developed to demonstrate the operational logic of this framework without requiring physical RFID hardware. The simulation consists of a browser-accessible dashboard connected to Firebase Realtime Database, and a parallel simulation engine that automatically generates inventory events replicating realistic store activity. This implementation provides a functional proof-of-concept of the dashboard, alert logic, and real-time data flow that would characterize a live deployment of the proposed system.
 
---
 
## 5. Objectives
 
1. To propose a conceptual framework for upgrading existing EAS security tags in apparel retail stores with passive RFID chips, enabling item-level inventory intelligence without replacing current store security infrastructure.
2. To define the system architecture, tracking logic, and software components of an RFID-based real-time inventory dashboard that identifies misplacement and theft events automatically, and to demonstrate this architecture through a functional software simulation.
---
 
## References
 
[1] Moorthy, R., Behera, S., and Verma, S., "On-Shelf Availability in Retailing," *International Journal of Computer Applications*, vol. 116, no. 23, April 2015.
 
[2] Pietrini, R., Paolanti, M., Mancini, A., Frontoni, E., and Zingaretti, P., "Shelf Management: A Deep Learning-Based System for Shelf Visual Monitoring," *Expert Systems With Applications*, vol. 255, 2024. DOI: 10.1016/j.eswa.2024.124635.
 
[3] "Towards Intelligent Retail: Automated On-Shelf Availability Estimation Using a Depth Camera," *IEEE Access*, 2020. DOI: 10.1109/ACCESS.2020.2968175.
 
[4] Hossain, M. T., "Smart Inventory and Warehouse Automation for Fashion Retail," *TechRxiv (IEEE)*, 2025. DOI: 10.36227/techrxiv.175987210.04689809/v1.
 
[5] "Shelf Track: Intelligent Empty Shelf and Low-Stock Monitoring System," *Journal of Information Technology and Digital World*, vol. 7, no. 3, pp. 216–226, August 2025. DOI: 10.36548/jitdw.2025.3.002.

