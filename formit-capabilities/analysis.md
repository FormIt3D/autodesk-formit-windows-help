---
description: >-
  Start a BIM workflow by evaluating the performance of elements from the
  beginning of the design process.
---

# Solar + Energy Analysis

![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Energy Analysis in FormIt

Analyze your building model for energy efficiency early in the design process.

[View Your Insight Projects](https://gbs.autodesk.com/OneEnergy/Insight)

## Energy Analysis with Insight

With a **FormIt Pro** subscription through the [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), you have access to Energy Analysis with **Insight:**

* Analyze early-stage design models with Green Building Studio's analysis engine
* Connect to a dashboard view of the analysis results to compare options for your design
* Adjust the Energy Analysis factor widgets, such as Window to Wall Ratio, Building Orientation, and others
* Summarize your building's energy impact with a single number calculated as a bottom-line cost per area
* Save your Energy Analysis results for future review with clients and other stakeholders

## What's New With FormIt + Insight <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Improvements to Insight Reliability** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) now checks your model for common model issues before launching Insight runs, and fixes common Insight failures for a more reliable experience.
* FormIt 2021 also generally improves reliability of the FormIt + Insight connection, addressing many known failures and improving run success rates.

## Getting Started <a href="#insight-getting-started" id="insight-getting-started"></a>

### **How It Works** <a href="#how-it-works" id="how-it-works"></a>

* Insight Energy Analysis uploads your FormIt model data, and runs several hundred analyses in the cloud to determine various energy scores
* Energy Analysis uses Revit to analyze your model, so just like when sending FormIt data to Revit, you'll need to [ensure your FormIt model is watertight and manifold](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **Preparing Your FormIt Model** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight will use any visible geometry in your FormIt sketch
  * Ensure the building shell you want to analyze is the only visible geometry
  * Put supporting geometry like entourage, furniture, and site elements on a separate [Layer](../tool-library/layers.md), and turn the Layer off
* Insight works best with a simple, solid building model
  * Ensure your building mass is [solid and watertight](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * If your building design already has openings for windows and doors, it's best to create a new mass with no openings specifically for Energy Analysis, and hide the more detailed version using Layers
* The simple building mass needs to have [Levels](../tool-library/levels-and-area.md) applied
* The FormIt model needs to have a [Location](../tool-library/setting-location.md) set

![](../.gitbook/assets/insight.png)

### **Starting Energy Analysis** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Look for the Energy Analysis button in the toolbar

![](../.gitbook/assets/generate\_insight.png)

* Click "Generate Insight" to start the process
* This will upload the visible model data, and will run several hundred simulations in the cloud
* When complete, a message will appear at the top of the screen, and the menu will update to indicate a new Insight is ready to view
  * Click "View Insight" to view the analysis in your web browser
  * You can also find all your Insights at [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Troubleshooting <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Common Errors** <a href="#common-errors" id="common-errors"></a>

* "Insight project could not be created. Please try again later."
  * Log in to the [Green Building Studio dashboard](https://gbs.autodesk.com/GBS/Project), then restart FormIt
    * If you're not able to log in, or if you see an "access denied" page, you may need to [purchase a subscription to Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
  * Check that your model is [solid and watertight](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * Check for any issues with FormIt services on the [Autodesk Health Dashboard](https://health.autodesk.com/)
* To see if Green Building Studio successfully executed Energy Analysis runs for this project, take a look at the [Green Building Studio dashboard](https://gbs.autodesk.com/GBS/Project)
  * Your latest project should appear at the top of the list, and should display 248 runs
  * If it displays 0 runs, [let us know on the FormIt forums](https://forums.autodesk.com/t5/formit-forum/bd-p/142), and we can help troubleshoot further

### **Detailed Logs** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt Web provides additional details when Energy Analysis fails:
  * Go to [FormIt Web](https://formit.autodesk.com/app)
  * Open the model that's having issues with Energy Analysis
  * Run Energy Analysis
  * Open Developer Tools (hit F12 in either Google Chrome or Firefox)
  * Look at the Console tab
  * Copy or screenshot any errors, and [report them on the FormIt forums](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## Solar Analysis

With a **FormIt Pro** subscription through the [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), you can visualize the sun's impact on your building:

* Specify relevant faces to be analyzed for solar impact
* Visualize results in seconds within the app canvas
* Hover your mouse over an input point to see specific calculated values of solar impact
* Choose to view results as a monthly glazing study, or as a yearly solar panel feasibility study

Learn more about [Solar Analysis](../tool-library/solar-analysis.md) in FormIt Pro.
