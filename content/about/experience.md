---
title: "Work Experience"
weight: 2
breadcrumbs: false
---

{{% steps %}}

### Embedded & IoT Systems Engineer

<div style="display: flex; justify-content: space-between;">
    <span style="font-size: 1em; color: #888;">
        IOTIQ GmbH · Leipzig, Germany
        <br>
        <em>September 2020 – August 2024</em>
    </span>
    <a href="https://iotiq.de/" target="_blank" aria-label="IOTIQ website">
        <img src="/about/experience/iotiq-logo.png" alt="IOTIQ Logo" style="max-height:80px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
        </a>
</div>

At IOTIQ GmbH I worked as an Embedded & IoT Systems Engineer involved in the design and development of hardware, firmware, and integration of smart embedded systems. My work covered both B2B projects for clients (such as DEMAG or Deskcenter) and R&D-driven initiatives under European frameworks (ITEA, Horizon Europe), and also internal product development such as AccessCtrl.

I participated end-to-end in the architecture, development, prototyping, testing, and deployment of embedded solutions, often combining hardware design (PCB), firmware (C/C++, FreeRTOS), and communication stacks (MQTT, Bluetooth, NFC, LoRaWAN). In addition, I was also responsible for DevOps processes (CI/CD, containerization, infrastructure automation) as well as full-stack development where needed, including backend services and Angular-based frontends.

My role evolved to include project leadership and mentoring, especially in later stages of internal product development for multiple projects such as AccessCtrl and InnoSale.

#### Main Responsibilities

- Hardware design (PCB, ESP32/ESP8266, sensors)
- Firmware development (C/C++, FreeRTOS, MQTT, NFC, BLE)
- DevOps (CI/CD, Docker, Azure Pipelines)
- Full-stack development (Angular, FastAPI, Keycloak)
- Project leadership and mentoring
- Collaboration in multinational R&D consortia and European-funded innovation projects (ITEA, Horizon Europe)


#### Notable Projects
##### AccessCtrl

<span style="font-size: 0.9em; color: #888;">
<em>April 2021 – August 2024</em>
</span>

Designed a custom control board based on ESP32 SoC including power stage, relay-based outputs for electronic/magnetic locks, NFC reader interface, and door state sensing. The board connected via Wi-Fi to a secure backend API, enabling door control via NFC cards/keyfobs or a Flutter-based mobile app via BLE. Designed PCB in KiCad, tested SMD prototypes manually. Also implemented embedded API logic, secure and fast communication (MQTT+WebSockets+SSL), and managed and mentored interns for frontend/backend support.

<!-- [LinkedIn AccessCtrl post](https://www.linkedin.com/posts/iotiq-gmbh_accessctrl-unser-digitales-zutrittsmanagementsystem-activity-6867110761710268418-qKg9?utm_source=share&utm_medium=member_desktop&rcm=ACoAABOkcXQBXGV1XjMqaRaR42fkofhDVLb4Gek) -->

<div style="display: flex; justify-content: center; margin: 1em 0;">
    <iframe src="https://www.linkedin.com/embed/feed/update/urn:li:ugcPost:6867110731502903296?collapsed=1" height="579" width="504" frameborder="0" allowfullscreen="" title="Embedded post"></iframe>
</div>


##### InnoSale

<span style="font-size: 0.9em; color: #888;">
<em>November 2021 – August 2024</em>
</span>

Developed reusable Angular components for a smart quotation tool supporting complex industrial sales (e.g., cranes for DEMAG). Defined and coordinated UI component specifications tailored to the German use-case. Supported an intern in frontend implementation and contributed to later refinements and issue resolution. Designed and implemented the initial backend prototype using FastAPI, with secure user management through Keycloak, based on a defined OpenAPI specification.

Managed technical collaboration across a multinational consortium (Germany, Finland, Turkey, and Spain). Responsibilities included setting up and configuring an SVN server for version control, handling on-site consortium meetings, presenting company results, and attending regular progress sessions. Contributed to the architectural design of IOTIQ's development components and prepared derivables required for ITEA reporting.


{{< figure 
    src="/images/innosale.png" 
    link="https://www.innosale.eu/"    target="_blank"   
    alt="InnoSale" 
    caption="InnoSale — https://www.innosale.eu/"
    class="experience-webpage-figure"
>}}


##### Light Lifting Equipment Automation

<span style="font-size: 0.9em; color: #888;">
<em>March 2023 – August 2024</em>
</span>

Designed the system logic and communication interfaces to automate industrial crane operations using a Jetson Nano (Ubuntu), Docker and C++. Integrated HMI Flutter app (via OPC-UA), ERP system (via REST APIs), and crane controller (via MQTT under OPTIMUM framework). Implemented state handling, workplan execution, and heartbeat-based safety checks.



##### OPTIMUM

<span style="font-size: 0.9em; color: #888;">
<em>September 2020 – March 2021</em>
</span>

Designed and developed a custom embedded hardware sensor device for crane obstacle detection, integrated into one of the OPTIMUM project demonstrators. The system was based on an ESP8266 SoC and a Time-of-Flight (ToF) sensor, selected after evaluating and comparing performance with ultrasound alternatives. Designed the PCB and prototyped the device enclosure using 3D printing.

Developed the firmware for the device using a custom IoT firmware stack, implementing a PID control loop to ensure precise and responsive obstacle detection in real time. Established robust MQTT communication for seamless integration into the OPTIMUM Distributed Control Platform (DCP), ensuring reliable and low-latency data exchange with the rest of the system. Data was visualized using Processing for validation and testing during development.

{{< figure 
    src="/images/optimum.png" 
    link="https://www.optimum-itea3.eu/" 
    target="_blank"   
    alt="OPTIMUM" 
    caption="OPTIMUM -  https://www.optimum-itea3.eu/"
    class="experience-webpage-figure"
>}}

<!-- | [Demo video](https://www.youtube.com/watch?v=1g-sNCBvK1o) -->



##### Deskcenter Software Catalogue

<span style="font-size: 0.9em; color: #888;">
<em>September 2020 – April 2021</em>
</span>

Led the setup and maintenance of the CI/CD infrastructure using Azure Pipelines for Deskcenter’s software catalogue system, which identifies and normalizes installed software, versions, patches, and licenses. Configured deployment pipelines for on-premises Windows machines, defined the Git branching strategy (release/feature), managed Docker-based builds, and integrated automated integration testing. Supported Scrum-based workflows and conducted technical research to establish a robust and scalable delivery process.

Also contributed to the Angular-based frontend by resolving UI component issues, fixing routing bugs, and developing the visualization of registered machines as interactive nodes—gaining practical experience with the Angular framework and reinforcing the stability and usability of the interface.

{{< figure 
    src="/images/deskcenter.png" 
    link="https://www.deskcenter.com/en/software-4" 
    target="_blank"   
    alt="Deskcenter Software Catalogue" 
    caption="Deskcenter Software Catalogue -  https://www.deskcenter.com/en/software-4"
    class="experience-webpage-figure"
>}}


##### CULTURATI

<span style="font-size: 0.9em; color: #888;">
<em>February 2023 – August 2024</em>
</span>

Developed software bridge to integrate LoRa-based sensors for visitor presence detection into CULTURATI’s digital heritage platform. Enabled data ingestion and real-time presence analysis across multiple exhibition areas.


{{< figure 
    src="/images/culturati.png" 
    link="https://culturati.eu/" 
    target="_blank"   
    alt="CULTURATI" 
    caption="CULTURATI -  https://culturati.eu/"
    class="experience-webpage-figure"
>}}

<br>
<br>
<br>

### DevOps Engineer

<div style="display: flex; justify-content: space-between;">
    <span style="font-size: 1em; color: #888;">
        Sensape GmbH · Leipzig, Germany
        <br>
        <em>November 2018 – June 2019</em>
    </span>
    <a href="https://www.sensape.com/" target="_blank" aria-label="Sensape website">
        <img src="/about/experience/sensape-logo.png" alt="Sensape Logo"style="max-height:50px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

During my period at Sensape, I mainly analyzed and streamlined the development pipeline from business ideas to the customer experience, focusing on redefining the current architecture to customize applications and services easily for different customers, reducing repetitive work, simplifying triage work needed to fix issues, and improving the time of development, support, and production deployment of new features.

To reach those goals, I developed:

- Configuration-handler: Merged several configs (following Linux priority standard style) and restarted the apps and services involved, applying those configurations. Also exported configuration for third-party software components handling several formats, such as JSON5, JSON, or YAML.
- Reduced existing strong coupling and increased cohesion among different services and applications by developing unit services to manage Front-end, hardware modules, and Back-end services.
- Application-handler: Redistributed specific configurations among the system, removing redundancy, duplicated code, and the same functionality between different applications. Redesigned the whole Back-end architecture to fit the new configuration paradigm, adding a legacy layer for old systems.
- Created a Python library to work in sync with the Configuration-handler ecosystem and easily configure classes or libraries imported on Python services.
- Developed a service to reshape and convert production devices to development mode, managing Linux user configurations, deb package components and versions installed, networking interfaces, and cloning and installing repositories for debugging and developing. Also added the fallback to production operations, keeping new desired staged configurations.
- Reduced several common issues by adding automated scripts to fix systemd services, such as the local MongoDB, display and touch screen, or hard disk failures.
- Documented new infrastructure and supported migration of services for the China region.

<br>
<br>
<br>

### Lead Software Development Engineer

<div style="display: flex; justify-content: space-between;">
    <span style="font-size: 1em; color: #888;">
        IoCare · Leipzig, Germany
        <br>
        <em>July 2017 – December 2018</em>
    </span>
    <a href="https://iocare.de/de/" target="_blank" aria-label="IoCare website">
        <img src="/about/experience/iocare-logo.png" alt="IOTIQ Logo"style="max-height:80px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

IoCare develops a service that improves the peace of mind of caregivers and at the same time keeps the independence of the alone living elderly. This solution autonomously and continuously self-learns the daily living pattern of the elderly in their home based on a sensor device that remotely aggregates the user's movements. Using the deviation level of the daily routine, the service is capable of providing the necessary feedback to the respective caregivers.

During my time at IoCare, I developed the following responsibilities:

- Studied and designed use cases and service blueprints for IoCare IoT products.
- Created and built the Back-End software architecture and built up the system following the requirements previously studied.
- Defined the software requirements for the dashboard Front-End web application to control the IoT devices, as well as led the development and executed Quality Assurance (testing and bug fixing).
- Managed and developed the production and testing procedures for the IoT hardware devices in the mass production line in China.
- Responsible for creating, developing, and maintaining repositories for hardware, firmware, and software products, including CI/CD pipelines for automating deployment.
- Configured, deployed, and maintained AWS services (IAM, IoT, S3 Buckets, Cognito, Lambda, API Gateway, DynamoDB, and RDS) for global use of IoT devices and a dashboard web application, synchronizing with our requirements of security and performance within the Europe and China regions.
- Performed the Scrum master role for managing the SW and HW products of the company, covering sprint planning, development, and retrospective reviews.

<br>
<br>
<br>

### Hardware Development Manager

<div style="display: flex; justify-content: space-between;">
    <span style="font-size: 1em; color: #888;">
        The Papaya Group · Madrid, Spain
        <br>
        <em>September 2016 – April 2017</em>
    </span>
    <a href="https://thepapayagroup.com/" target="_blank" aria-label="The Papaya Group website">
        <img src="/about/experience/thepapayagroup-logo.png" alt="The Papaya Group Logo"style="max-height:60px; margin:0;" transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

I led the development, management, and implementation of an energy measurement tool which was installed in electrical substations, factories, and cultural buildings for electrical network analysis, control, and alerts generation.

Additionally, I designed and developed IoT devices for diverse clients related to logistics, tourism, and Smart Cities. I also implemented documentation and supervision tools for projects, such as Confluence, Jira, and Bitbucket.

<br>
<br>
<br>

### R&D Engineer, Innovation and Robotics Department

<div style="display: flex; justify-content: space-between; margin: 0;">
    <span style="font-size: 1em; color: #888;">
        BQ · Las Rozas de Madrid & Pamplona, Spain
        <br>
        <em>September 2013 – April 2016</em>
    </span>
    <a href="https://bqeducacion.cc/" target="_blank" aria-label="BQ website">
        <img src="/about/experience/bq-logo.png" alt="BQ Logo"style="max-height:80px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

In this position, I was a key contributor in the setup and growth of the company’s manufacturing facility for desktop 3D printers and educational robotics, based in Pamplona. I led prototyping activities across hardware, firmware, and software, conducting feasibility studies and quality assessments for new products.

As an expert in the emerging and democratized 3D printing technology, one of my responsibilities during this time included defining and evaluating new product lines, alongside which I carried out regular audits on the production line to ensure consistent quality in mass manufacturing. Specifically, I was responsible for designing the relevant tests on the assembly line and ensuring production quality by leading the EVT, DVT, and PVT for the flagship products Witbox and its successor Witbox 2. These efforts successfully scaled the production rate up to 25 printers per 8-hour shift, contributing to the Witbox being recognized as one of the top 10 best-rated 3D printers globally in 2014, with over 7,000 units sold annually.

Thanks to my broad knowledge of the 3D printing sector and my experience delivering public demonstrations and talks across Spain, I also played an important role in representing the company at major technology fairs. This included designing and delivering presentations, coordinating exhibitions, and engaging with partners and the wider tech community.

<br>
<br>
<br>

### Expert in Digital and New Technologies

<div style="display: flex; justify-content: space-between; margin: 0;">
    <span style="font-size: 1em; color: #888;">
        bq CIRCOLAB · Spain
        <br>
        <em>June 2015 – February 2016</em>
    </span>
    <a href="https://studiobanana.com/es/work/reduciendo-la-brecha-digital-a-traves-de-un-viaje-por-carretera/" target="_blank" aria-label="CIRCOLAB website">
        <img src="/about/experience/circolab-logo.png" alt="CIRCOLAB Logo"style="max-height:100px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

Supported by BQ, I actively contributed to a nationwide STEAM outreach initiative across Spain, preparing and delivering interactive workshops and hands-on activities aligned with the STEAM philosophy. I played a key role in designing engaging educational content to inspire participants.

I provided technical expertise and support for the use and maintenance of digital fabrication tools and equipment onboard the mobile laboratory.

Additionally, I contributed to creating and publishing digital resources and documentation to enhance the project’s online presence.

As part of my responsibilities, I had the honor (and occasional challenge) of being the official driver for the Circolab van, crisscrossing Spain on this exciting journey.

<!-- [Studio Banana: CIRCOLAB Tech Learning Experience](https://studiobanana.com/work/circolab-tech-learning-experience/) | [CIRCOLAB YouTube Channel](https://www.youtube.com/channel/UCIg6UiZobaCTi8IAtioFV6Q) | [Twitter: @cir_co_lab](https://twitter.com/cir_co_lab) -->

{{< figure 
    src="/images/studiobanana.png" 
    link="https://studiobanana.com/work/circolab-tech-learning-experience/" 
    target="_blank"   
    alt="CIRCOLAB" 
    caption="CIRCOLAB - [Studio Banana: CIRCOLAB Tech Learning Experience](https://studiobanana.com/work/circolab-tech-learning-experience/)"
    class="experience-webpage-figure"
>}}

<br>
{{< youtube h0n4ctsfT9I >}}
<br>
{{< instagram BBVFtH3iDcc >}}
<br>

<br>
<br>
<br>

### IT Support Technician

<div style="display: flex; justify-content: space-between; margin: 0;">
    <span style="font-size: 1em; color: #888;">
        HP (Hewlett-Packard) · Madrid, Spain
        <br>
        <em>June 2008 – September 2008</em>
    </span>
    <a href="https://hp.com/" target="_blank" aria-label="HP website">
        <img src="/about/experience/hp-logo.png" alt="HP Logo"style="max-height:80px; margin:0; transition:box-shadow 0.3s;" onmouseover="this.style.boxShadow='0 4px 16px rgba(0,0,0,0.25)';" onmouseout="this.style.boxShadow='none';">
    </a>
</div>

Provided remote support to HP laptop customers by diagnosing and identifying technical issues via email. Assisted clients with step-by-step solutions for software and configuration problems, and coordinated repair logistics for hardware cases, ensuring a smooth process for warranty-covered repairs.

{{% /steps %}}

<br>
<br>
<br>

### Reference Letters

Reference letters available upon request via the [contact section](/contact/).