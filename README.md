<div align="center">
  <h1>MedCode Pro</h1>
  <p>
    A modern browser based medical coding and billing workspace built for fast lookup, clean claims, and practical revenue insights.
    <br /><br />
    <a href="https://tabitha-dev.github.io/MedCode/"><strong>Open Live Demo »</strong></a>
    <br /><br />
    <a href="https://github.com/tabitha-dev/MedCode/issues">Report Bug</a>
    ·
    <a href="https://github.com/tabitha-dev/MedCode/issues">Request Feature</a>
  </p>
</div>

<p align="center">
<img width="1906" height="732" alt="image" src="https://github.com/user-attachments/assets/92d38d8d-1dc1-4977-8249-a3a56c55fc35" />

</p>

<p align="center">
  <img src="assets/medcode-demo.gif" alt="MedCode Pro animated demo" width="900" />
</p>

<p align="center">
  <em>Modern, fast, and zero backend. Designed for real world coding and billing workflows.</em>
</p>

---

## 💡 Why MedCode Pro matters

Billing teams, coders, students, and small practices often switch between many disconnected tools. MedCode Pro brings common workflows together in one clean interface.

✅ Faster code lookup and comparison  
✅ Immediate claim preview with scrubber  
✅ Simple revenue insights without analytics software  
✅ No installation, account creation, or backend required  
✅ Works offline once loaded  

<em> This project is ideal for learning, demos, classrooms, interviews, and portfolio storytelling.

 fast, zero backend. Designed for real world coding and billing workflows.</em>
</p>

---

## 📌 Table of Contents

- [Core views](#core-views)
- [Shared helpers and simulators](#shared-helpers-and-simulators)
- [Tech stack](#tech-stack)
- [Running the app](#running-the-app)
- [Keyboard shortcuts](#keyboard-shortcuts)
- [Notes on data and licensing](#notes-on-data-and-licensing)
- [Live demo and repository](#live-demo-and-repository)

---

---

## Core views


1. Dashboard  
   • Landing view with system status, recent activity, and a compact overview of trending codes  
   • Quick access search bar plus shortcut hint for the command palette  
   • Superbill section that shows starred codes saved by the user  
   • Small daily challenge widget with one coding question per session for practice

2. Code search  
   • Tabbed search for three code families  
     ◦ ICD eleven diagnosis search using the NLM clinical tables application programming interface  
     ◦ HCPCS level two search using the NLM clinical tables application programming interface  
     ◦ CPT style procedure search using a small mock data set stored in the file  
   • Each result card shows  
     ◦ Code, title, and source badge  
     ◦ Optional relative value units for mock CPT data and a simple estimated payment based on the twenty twenty five conversion factor  
     ◦ Automatic ICD eleven to ICD ten style mapping label where available  
     ◦ Prior authorization button for codes that are flagged as needing it in the mock data  
   • Actions on each result  
     ◦ Add to claim preview  
     ◦ Star or unstar for the superbill list  
     ◦ Open details with a click which also updates local history

3. Billing preview workspace  
   • Two layouts  
     ◦ CMS one five zero zero style form for professional claims  
     ◦ UB zero four style form for facility claims  
   • Diagnosis section uses ICD eleven codes and the mapped ICD ten representation where available  
   • Procedure section uses CPT style and HCPCS style codes with optional modifiers  
   • Point of service selector that drives the place of service value on the CMS one five zero zero view  
   • Claim scrubber that runs simple denial risk rules  
     ◦ Checks for missing diagnosis or procedure codes  
     ◦ Looks for risky patterns such as modifier use that does not match usual payer expectations  
     ◦ Flags high level evaluation and management visit codes that need strong documentation  
   • Risk report modal that shows all detected issues and allows the user to open the appeal helper  
   • Appeal letter helper that generates a starting template for a claim appeal based on the detected risk pattern  
   • Patient eligibility simulator for a simple eligibility style check  
   • Patient cost estimator that lets you enter totals, remaining deductible, and coinsurance to show a good faith estimate split between payer and patient

4. Revenue analytics view  
   • Simple analytics cards that show pipeline, revenue, clean claim rate, denial rate, and days in accounts receivable  
   • Time range toggle with month, quarter, and year options  
   • Animated bar chart that represents revenue trend for the selected time frame  
   • Simple mix widget showing payer mix for medicare, commercial, and self pay segments  
   • Table of top performing codes with rough revenue amounts based on the selected time range

5. Tools and reference view  
   • Filterable list of common modifiers with short descriptions  
   • Compact grid of place of service codes with their descriptions  
   • This view is read only and meant as a small quick reference panel

## Shared helpers and simulators

1. Command palette  
   • Opens with control plus k and shows a spotlight style search  
   • Can search across mock CPT codes, modifiers, and mock patient records  
   • Selecting a procedure from the palette adds it directly to the billing items

2. Prior authorization simulator  
   • For selected procedure codes that are marked as requiring authorization  
   • Shows a small flow where the artificial intelligence themed agent looks at payer rules  
   • Can either approve immediately or request additional documentation before approval

3. Clinical documentation improvement helper  
   • When you try to add an unspecified ICD item, a clinical documentation improvement modal opens  
   • Shows targeted documentation questions based on condition type  
   • Lets the user copy a provider query text or proceed with the unspecified code

4. Local storage support  
   • Recent history of viewed codes is saved in browser storage  
   • Starred items for the superbill list are also stored locally  
   • No external database or backend is used

## Tech stack

React eighteen rendered into a root container in `index.html`  

React and ReactDOM loaded through universal module definition builds from a public content delivery network  

JSX compiled in browser through a babel stand alone script  

Tailwind style utility classes loaded from content delivery network and mixed with custom cascading style sheets for the CMS one five zero zero and UB zero four grid layouts  

No build step and no package manager required

## Running the app

1. Open `index.html` in any modern browser  
2. Or serve the file from a simple static server  

Everything runs in the browser. There is no authentication, no external storage, and all simulated payer behavior is hard coded for demo use only.

## Keyboard shortcuts

1. Control plus k opens or closes the command palette  
2. Escape closes open modals such as the command palette or risk report

## Notes on data and licensing

1. ICD and HCPCS search uses public NLM clinical tables application programming interfaces  
2. CPT content in this demo is a small handcrafted mock list with imaginary values  
   This avoids any direct use of proprietary CPT content from AMA  
3. All financial numbers, payer rules, and risk checks are sample logic for training or demo environments and are not intended for production billing

---

## 🚀 Live demo and repository

**Live demo**  
https://tabitha-dev.github.io/MedCode/

**Project repository**  
https://github.com/tabitha-dev/MedCode

**Author**  
Tabitha Khadse
