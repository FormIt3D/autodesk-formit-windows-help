---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt for Windows has Dynamo built-in for incredible computational design workflows.

[Download FormIt for Windows](https://formit.autodesk.com/page/download)

## What's New With FormIt + Dynamo

### **Dynamo Visual Refresh, Data Graphs, and FormItGroupOptions Improvement**

FormIt 2023 adds Dynamo 2.13, featuring a modernized dark gray theme and a host of other improvements, the ability to run Dynamo graphs without a SendToFormIt node (known as data graphs), the ability to set curve and surface faceting counts via FormItGroupOptions, and more.

### **Dimension Inputs and Early JS API Access**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) adds the ability to use [familiar FormIt dimensions as inputs](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), introduces [object-level options](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes), and offers an early preview of [JavaScript API access](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Get it [here](https://formit.autodesk.com/page/download).

### **Multiple SendToFormIt Nodes**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) adds the ability to use [multiple SendToFormIt nodes and nested Dynamo graphs](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **SelectFromFormIt Node**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) adds the [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node, and enables always-connected sessions, multi-instance editing, and more.

## Getting Started

Learn about the interface and link your Dynamo directories to FormIt.

### **First Time Setup**

First time using FormIt + Dynamo? You may need to [configure your system](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes) first, in order to see the 3D canvas in Dynamo.

### **The Dynamo Panel**

Use the Dynamo panel to launch Dynamo, place Dynamo Groups, and edit Dynamo graphs:

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **Adding and Managing Local Dynamo Directories**

* The Dynamo panel works just like the [Content Library](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), allowing you to link and manage local directories containing Dynamo files.
* Click the "Link Directory" button in the Dynamo panel, and then click (+) again in the Preferences dialog to select a directory to link to FormIt: ![](../.gitbook/assets/dynamo\_selectdirectory.png)
* Switch between linked directories using the drop-down:

![](../.gitbook/assets/dynamo\_dropdown.png)

* You'll only be able to view .dyn files and subfolders through the Dynamo panel.
* Use the Filter bar to filter out Dynamo files and subfolders so you can easily find what you need:

![](../.gitbook/assets/dynamo\_filter.png)

## Different Ways to Dynamo

Author and edit graphs in Dynamo, or flex parameters in FormIt without ever seeing the graph. Or both at once!

### **Graph Types**

FormIt supports three types of Dynamo graphs:

* Data graph: Data graphs have no _SendToFormIt_ nodes and are used to surface or pass data through FormIt. For example, you can use data graphs to send data to Excel, produce text, pull information about levels, etc.
* Geometry graph: These graphs produce geometry immediately and must be placed into the canvas to see their parameters. After clicking the thumbnail, the geometry will appear on the cursor for placement into the 3D scene. This graph requires at least one _SendToFormIt_ node to be present and receiving geometry at the end of the graph.
* Selection graph: These graphs require FormIt selections before running. You'll see a prompt in the upper-left corner to indicate what needs to be selected. After clicking the check icon, the graph will run and generate geometry relative to the selected geometry. This graph requires at least one _SendToFormIt_ node to be present and receiving geometry at the end of the graph.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Send Dynamo Geometry to FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* In the Dynamo panel, click the thumbnail of the Dynamo graph you want to run.
  * You can use the built-in samples, or [link a library](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) of your own Dynamo files.
* Placing the geometry into FormIt will embed a copy of the Dynamo graph into the FormIt file.
  * To generate geometry, a [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node needs to be attached to output geometry nodes in the graph.
* The geometry from the SendToFormIt node will be available on your cursor for placement.
  * When the graph has [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) nodes marked as Is Input, FormIt will ask first for the selection (each selection node in vertical order), then generate the geometry in the correct place relative to the selection.
* A copy of the original Dynamo file is now embedded into the FormIt Group and is independent of the source graph.
* Upon placement, the Properties panel will automatically toggle to reveal the available parameters.

### **Modify Parameters**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* After placing a Dynamo Group, select it and switch to the Properties panel, or simply double-click the Group to automatically switch to Properties.
  * Any input nodes marked as "Is Input" in Dynamo will be listed here.
  * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) input nodes will show up as buttons at the top, and can be used to update the selection that's used to drive the graph.
  * FormIt supports these input nodes: Number Sliders, Integer Sliders, Boolean Toggles, and Number/String fields.
* Make changes to the inputs in FormIt, then click Run. The Run button will turn blue to indicate parameters have been modified, and the graph needs to be run.
  * Dynamo will run in the background to process the changes and return updated geometry in FormIt.
  * In FormIt 2022 and newer, the first run from the Properties panel spins up a dedicated Dynamo instance, making subsequent edits much faster.
  * You can continue using FormIt while Dynamo is running.&#x20;
* Note that all geometry inside each SendToFormIt Group will be deleted and replaced when the Dynamo graph runs.

### Send FormIt Levels to Excel

In FormIt 2023 and newer, you can use Dynamo to send FormIt levels to Excel:&#x20;

* Download the [sample Dynamo graph here](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Point the Dynamo palette to the local directory where the Dynamo graph was saved.
* Right-click on the thumbnail, and click _Edit Embedded Graph._
* Create an empty Excel spreadsheet somewhere.
* Edit the Spreadsheet Location field to use the path to the Excel spreadsheet.
* Edit any other fields you'd like such as Sheet Name.
* Close Dynamo and save the graph.

Now you can simply click the example file in the palette, and it'll run in FormIt without needing to generate geometry.&#x20;

You'll see the Dynamo inputs appear in the Dynamo palette, and you'll see Excel open up to display the results from the graph.&#x20;

As you make changes to the model, you can click the graph thumbnail again, or the _Run_ button, to update the spreadsheet with the level data from the latest version of the FormIt sketch.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Launch a New Dynamo Window

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* In FormIt 2021 and newer, clicking the Launch Dynamo button in the Dynamo panel will start a connected session with FormIt automatically.
  * This opens a graph template in Dynamo, and will automatically generate the template geometry in FormIt.
  * The resulting geometry will appear in a new Group, at the origin of the current Group editing context. It's best to be in the desired Group context before starting Dynamo.&#x20;
  * The template includes both FormIt nodes, and some example geometry. Adjusting the sliders will adjust the cube's size in both applications.
  * From here, you can open different Dynamo graphs, or build something new using these basic components in the template and Save As in Dynamo to a new location.

### **Edit Embedded + Source Graphs**

Existing Dynamo graphs can be edited in two distinct ways: by editing Embedded Graphs that have already been placed in FormIt, or by editing the Source Graph that's saved on your computer.

### **Embedded Graphs**

After placing a Dynamo object into FormIt, its underlying graph is copied and embedded into the current FormIt file. Editing this in Dynamo happens through the **Edit Embedded Graph** button.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Select the Dynamo Group and switch to the Properties panel, or simply double-click the Group to automatically switch to Properties.
* Click the **Edit Embedded Graph** button.
* In Dynamo, you'll notice the file name at the top will now contain "(FormIt)", which means you're editing a graph that is embedded in this FormIt file, and not modifying the Source Graph.
* Make sure one or more [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) nodes is connected to the geometry you want to send to FormIt.
* FormIt will display updates to the geometry in realtime as you adjust the graph.
* If you don't save changes in Dynamo, FormIt will roll back to the last-saved version of the Dynamo graph.
* Note that all geometry inside each SendToFormIt Group will be deleted and replaced when the Dynamo graph runs.

### **Source Graphs**

Source Graphs are displayed in the Dynamo panel after [linking local directories](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). These graphs are stored on your computer, and can be edited in Dynamo by clicking the Edit Source Graph button.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Link a directory](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) containing Dynamo files to the Dynamo Panel, then navigate to that location in the panel.&#x20;
* Right click the thumbnail of the Dynamo graph you want to edit (or click the arrow), and select the **Edit Source Graph** button.
* Dynamo will launch with the requested graph opened, and in FormIt, you'll see the geometry from the graph's final output appear.
  * For graphs that use one or more [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) nodes as an input, you may not see the resulting geometry until the SelectFromFormIt nodes are populated with selections.
* The resulting geometry will appear in a new Group, at the origin of the current Group editing context.
  * It's best to be in the desired Group context before clicking Edit Source Graph.
* When finished editing, save and close Dynamo. In FormIt, the source graph has been copied and embedded in the FormIt file.
  * If you need to make more edits to the **Source Graph**, delete the embedded copy and follow these steps again.

### **Control Curve + Surface Faceting**

*   Starting in FormIt 2023, you can control the faceting of curves and surfaces attached to SendToFormIt nodes by using the FormItGroupOptions nodes SetCurveFacetingCount and SetSurfaceFacetingCount.

    ![](../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png)
* These nodes will override the global curve and surface faceting settings, which are defined under Edit -> Preferences -> Units + Accuracy.
* This is very useful if your Dynamo graph needs to generate curved objects using specific faceting values, alleviating the need to change the global setting for each Dynamo graph run in the current session.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* Starting with FormIt v18.0, the quality of curves and surfaces imported from Dynamo is now customizable.
* After adjusting the faceting quality in Edit -> Preferences, you can now click "Run Graph" in the Properties panel without making any parameter changes, to re-generate the Dynamo geometry with the new faceting settings.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[Learn more about curve and surface faceting settings in FormIt.](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## Using FormIt Groups with Dynamo

Harness the power FormIt Groups for better Dynamo geometry organization and incredible workflows.

### **Groups and the SelectFromFormIt Node**

* When selecting geometry for a [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node, it's useful to store the geometry in a FormIt Group, and select the Group instead.
  * Doing so gives you the flexibility to change the contents of the selected FormIt Group, then simply re-run the graph that is referencing the Group to see the updated result.
* If you select ungrouped geometry, changes to that geometry may result in FormIt asking you to re-select the geometry the next time the graph is run.

### **Generating Geometry in Groups**

* When a Dynamo graph is run in FormIt, its geometric results are contained in a FormIt Group.
* Each [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node in the graph creates a sub-Group to contain the geometry from the node input port.
* After generating a Dynamo object in FormIt, the entire graph and its parameters are embedded as a copy in the FormIt file.
* When the graph runs, the geometry inside each sub-Group is deleted and regenerated.
  * Use caution when modifying geometry or painting surfaces inside sub-Groups, as those changes will be lost when the Dynamo graph runs next.
  * However, if you paint sub-Groups (not geometry inside them) with FormIt materials, those materials will persist between runs. See below.

### **Working with Groups and Materials**

* When using multiple **SendToFormIt** nodes, you can organize the nodes by material, so you can paint different FormIt sub-Groups with different materials.
* In this example, an entire building is generated from simple planes in FormIt. Each building component requiring unique materials gets its own **SendToFormIt** node:

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* After applying materials to each of the sub-Groups, the materials persist between Dynamo runs:

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Nesting Dynamo Groups**

* You can use the **SelectFromFormIt** node to select the sub-Group results from one Dynamo graph to drive the results of another graph.&#x20;
* Building on the example above, the glazing output of the building generator graph is used as the selection geometry for the built-in Storefront Curtainwall sample:

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* When the building shape changes, you can simply select the mullion system Group, and click Run in the Properties panel.
  * Although the contents of the glazing Group changed, the Group itself didn't, so there's no need to re-select the glazing when re-running the graph.
* The above model is available in FormIt 2022 and newer as the "Roof Planes Building" in the **Building Masses** subfolder of **Dynamo Samples**.
* Combined with FormIt**'**s vast capabilities, you can use Dynamo to create and flex an entirely parametric design - complete with materials and nested logic - in the rich context of a powerful conceptual modeler:

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **Standard FormIt Group Behavior Still Applies**

* Other than what's outlined above, Dynamo Groups in FormIt operate by the same rules as other Groups:
  * Placing a new Dynamo object from the Dynamo panel makes a Unique Group, and will not affect any instances of the same object already placed in the sketch.
  * Copying and pasting Dynamo Groups keeps them identical. Any changes made to one copy's Dynamo graph will also update the geometry in its identical instances, unless they are made Unique.
  * You can make Dynamo Groups Unique with shortcut MU or through the Context Menu:

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## Essential FormIt Nodes

The most powerful nodes to send data between FormIt and Dynamo.

### **The SendToFormIt Node**

* To generate Dynamo objects in FormIt, attach the desired geometric node outputs to the _geometry_ input of at least one SendToFormIt node:

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions is a new (optional) port in FormIt 2022 and is detailed in the **FormItGroupOptions Nodes** section below.
* In FormIt 2021.3 and newer, you can use multiple SendToFormIt nodes to organize your Dynamo results into tidy FormIt Groups and sub-Groups.
* [See how Dynamo works with FormIt Groups](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* The SendToFormIt node respects the Is Output flag, which is checked by default. You can right-click the node to verify:

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* When checked, the geometry attached to this SendToFormIt node will appear in FormIt, inside a sub-Group.
* When unchecked, no geometry will be sent to FormIt, and the corresponding sub-Group (if there is one) will be deleted.

### **The SelectFromFormIt Node**

* FormIt 2021 and newer offers the ability to select geometry from FormIt for use as inputs in Dynamo graphs:

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* The name of the SelectFromFormIt node will be used for prompts in FormIt, so you should name it in a way that describes what type of FormIt geometry should be selected:

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* When the Select From FormIt button is clicked from the Dynamo graph editor or the Properties panel, FormIt will start a selection wizard mode to walk you through selecting geometry:

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* The SelectFromFormIt node respects the Is Input flag, which is checked by default. This needs to be checked for selection to work in FormIt. Right-click the node to verify.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* When Is Input is checked:
  * The Dynamo panel thumbnail of the graph will indicate that a selection is required:

![](../.gitbook/assets/dynamo\_patharray.png)

* When running the graph, the FormIt selection wizard will walk you through setting selections for each SelectFromFormIt node, starting at the top of the graph.
* After generating the first time, you'll see a button for each SelectFromFormIt node in the FormIt Properties panel.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Clicking these will start the selection wizard, so you can change the selection used to generate the final geometry. The graph will re-run automatically after re-selecting.

### **Tips, tricks, and notes**

* Name the SelectFromFormIt node to indicate what type of geometry is expected. For example, "Select Site Boundary (Edges)"
  * You can select any type of FormIt geometry, but it's often best to contain the selection into a FormIt Group and [select that instead of the raw geometry](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* If you need to move the results of a selection-based Dynamo graph, it's best to move the selection geometry first, then re-run the graph, which will pick up on the updated selection geometry and reposition itself appropriately.&#x20;
  * You can also Group the Dynamo results **and** the selection, then move the containing Group.
* When FormIt geometry is sent to Dynamo, any attributes, Materials, or nested Groups will be lost when returning geometry back into FormIt.
* If you're editing a selection-based graph in Dynamo, and the selected geometry in FormIt changes, you'll need to re-select the geometry by clicking the "Select From FormIt" button on the SelectFromFormIt node.&#x20;
* When selecting in FormIt, the active [Selection Filter](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering) is applied. For example, if you want to select FormIt vertices, you'll have to enable that in the Selection Filter.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Other Input Nodes

A wide array of input options for easy customization of Dynamo graphs in FormIt.

### **FormItLengthString Node**

In FormIt 2022.1.0 or newer, you can use the **FormItLengthString** node to specify dimensions in any supported FormIt unit type (feet-inch, inch, m, cm, mm) regardless of FormIt's unit setting in the active sketch.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

As with other supported input nodes, the _FormItLengthString_ will show up in the FormIt Properties palette when marked as Is Input, and when renamed, its new name will show up in FormIt:

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Each instance of the _FormItLengthString_ node can be used in any unit type, so a single Dynamo graph could employ a mix of units, as shown above.

### **Switching from Raw Numbers to FormItLengthString**

In FormIt 2022.1.1 and newer, switching a graph to use FormItLengthString nodes (by placing the first one in a graph) or switching a graph to use raw numbers only (by removing the last FormItLengthString) will change certain behaviors while editing a graph in Dynamo:

* When using the [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node while editing a graph, switching between raw numbers and the _FormItLengthString_ node as above will require re-selecting the geometry for each _SelectFromFormItNode_, so the results continue to be scaled correctly in FormIt.
* After placing the first FormItLengthString node in a graph, all numbers in the graph intended as dimensions (including raw number inputs) will refer to meters (Dynamo's native unit under the hood).
  * The [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) node will account for the change and ensure generated geometry in FormIt remains the correct size.
  * Conversely, removing all FormItLengthString nodes from the graph will switch raw numbers to refer to whatever FormIt's unit settings are (old behavior).
* The numeric output of _FormItLengthString_ nodes will also be in meters, but that won't change the size of the geometric results in FormIt:

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **Other Supported Input Nodes**

Standard Dynamo input nodes will display in the FormIt Properties panel when marked as "Is Input" in Dynamo:

* Number Slider
* Integer Slider
* Number
* String
* Boolean Toggle

You can rename the input nodes (recommended for clarity), and their new name will appear in FormIt:

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Other Output Nodes

Different methods to display non-geometric results from Dynamo to FormIt.

### **Watch Node**

Watch nodes marked as "Is Output" will display in the "Watch Node Outputs" section of the Properties panel in FormIt 2022 and newer:

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **Show FormIt Notifications**

In FormIt 2022.1 or newer, you can show FormIt-side notifications from a Dynamo graph using the **UI.ShowNotification** node:&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **Log to the FormIt Console**

In FormIt 2022.1 or newer, you can log additional data directly to the FormIt application console (Script Output window) with the **FormIt.ConsoleLog** node:

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt Options Nodes

Control how data is sent to FormIt, either at the individual geometry level or at the containing Group level.

### **FormItGeometryOptions**

FormIt 2022.1 and newer offers the ability to customize how individual Dynamo geometries are sent to FormIt with **FormItGeometryOptions** nodes.

* Specify the Layer for individual geometries inside the generated Dynamo group.
* Specify a string attribute for the individual geometries inside the generated Dynamo Group.

_FormItGeometryOptions_ nodes can be used upstream from the _SendToFormIt_ node:

![](../.gitbook/assets/dynamo\_formitgeometryoptions.png)

### **FormItGroupOptions**

FormIt 2022 and newer offers the ability to customize how the Dynamo group from the _SendToFormIt_ node is generated in FormIt with **FormItGroupOptions** nodes.

* Specify whether the SendToFormIt node sends geometry to FormIt as a Mesh or an Object.
* Specify the Layer for the Group created by the SendToFormIt node.
* Specify a string attribute for the Group created by the SendToFormIt node.

You can use any combination of FormItGroupOptions nodes in any order by daisy-chaining them together:

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript API Nodes

FormIt 2022.1 and newer offers access to JavaScript APIs and custom functions from Dynamo via two new nodes:

### **CallJSAPI**

The **CallJSAPI** node allows you to invoke FormIt JavaScript APIs directly from Dynamo.

![](../.gitbook/assets/dynamo\_calljsapi.png)

For function names and parameters, take a look at our JavaScript documentation, which is divided into two parts: [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) and [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (modeling kernel).

**CallPluginJS**

Conversely, the **CallPluginJS** node allows you to invoke custom functions from a loaded plugin, or a script snippet that's been executed from the Script Editor window.

![](../.gitbook/assets/dynamo\_callpluginjs.png)

## Important Notes

### **System Requirements**

* To use Dynamo in FormIt, you'll need [FormIt for Windows](https://formit.autodesk.com/page/download) v17.0 or later.
  * The FormIt + Dynamo integration receives new features and fixes regularly, so it's always best to download the latest update when available.
* You'll also need Windows 10. For technical reasons, older versions of Windows are no longer supported.

**Troubleshooting**

* If you have a system with an [NVIDIA or AMD graphics card](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/), or multiple cards, you may need to set FormIt and Dynamo to use your high-powered GPU:
  * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
  * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
  * If you have an NVIDIA card, [ensure you have the NVIDIA Control Panel installed](https://whatsabyte.com/blog/find-nvidia-control-panel/)
  * Use the [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) or [AMD](https://www.amd.com/en/support/kb/faq/dh-017) control panels to set the following applications to use your discrete graphics card:
* If you're in a non-English locale, you may need to set the Windows 10 region settings to English to avoid issues with certain Dynamo nodes:
  * Search Start for "language" and choose "Language settings"
  * At the top right of the Language dialog, click "Administrative language settings"
  * Click the "Change system locale..." button
  * Choose "English (United States)"
* If you're experiencing graphs failing to generate results in FormIt when working with small geometry or numbers, try changing the Dynamo scaling setting to "Small":
  * Dynamo menu > Preferences > General > Geometry Scaling > Small

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Get Support**

Need help with FormIt + Dynamo? [Let us know on the forums](https://forums.autodesk.com/t5/formit-forum/bd-p/142).
