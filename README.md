# **Linear Regression Simulator (ImGui + ImPlot + DirectX 11)**

This project is a **real-time linear regression visualizer** built using:

* **Visual Studio 2026**
* **DirectX 11**
* **Dear ImGui**
* **ImPlot**
* Live simulated data points
* CSV file loading
* Heatmap density visualization
* Real-time regression updates

It provides a fully interactive dashboard with scatter plots, regression fit lines, heatmaps, and residual histograms.

---

## **📌 Features**

✔ Real-time point simulation
✔ Adjustable slope, intercept, noise, and spawn rate
✔ CSV file importer (`x,y` pairs)
✔ Scatter plot + regression line
✔ Density heatmap (ImPlot Heatmap)
✔ Residual histogram
✔ Manual point insertion
✔ Adjustable data buffer size (rolling dataset)

---

## **🛠 Requirements**

To build this project, you MUST have:

### **1. Visual Studio 2026 (or later)**

Required for full C++20 support and DX11 SDK integration.

### **2. Dear ImGui**

You must download the official repository:

```
git clone https://github.com/ocornut/imgui.git imgui
```

### **3. ImPlot**

You must download the repository:

```
git clone https://github.com/epezent/implot.git implot
```

### **4. DirectX 11 Libraries**

Already included in Visual Studio’s Windows SDK.

The following libraries are linked automatically:

* `d3d11.lib`
* `dxgi.lib`
* `d3dcompiler.lib`

---

## **📁 Directory Structure Example**

Your project folder MUST look like this:

```
backend/
│
├── src/
│   └── main.cpp
│
├── imgui/
│   ├── imgui.h
│   ├── imgui.cpp
│   ├── imgui_draw.cpp
│   ├── imgui_widgets.cpp
│   ├── imgui_tables.cpp
│   ├── imgui_demo.cpp
│   ├── backends/
│   │   ├── imgui_impl_win32.cpp
│   │   ├── imgui_impl_win32.h
│   │   ├── imgui_impl_dx11.cpp
│   │   └── imgui_impl_dx11.h
│
├── implot/
│   ├── implot.h
│   ├── implot.cpp
│   ├── implot_items.cpp
│   ├── implot_demo.cpp
│
└── backend.vcxproj
```

---

## **📌 Visual Studio Setup Instructions**

### **1. Add .cpp files to the project**

In Visual Studio:

> Solution Explorer → Right-click Project → **Add → Existing Item**

Add:

From **imgui**:

* imgui.cpp
* imgui_draw.cpp
* imgui_widgets.cpp
* imgui_tables.cpp
* imgui_demo.cpp *(optional)*
* backends/imgui_impl_win32.cpp
* backends/imgui_impl_dx11.cpp

From **implot**:

* implot.cpp
* implot_items.cpp
* implot_demo.cpp *(optional)*

---

### **2. Add Include Directories**

Right-click project → **Properties**

Go to:

**C/C++ → General → Additional Include Directories**

Add:

```
$(ProjectDir)imgui
$(ProjectDir)imgui\backends
$(ProjectDir)implot
```

---

### **3. Link DirectX 11**

Go to:

**Linker → Input → Additional Dependencies**

Add:

```
d3d11.lib
d3dcompiler.lib
dxgi.lib
```

*(These are already in your Windows SDK so no download is required.)*

---

### **4. Build the project**

Click:

**Build → Build Solution**
or press **Ctrl + Shift + B**

To run:

Right-click **main.cpp → Set as Startup Item**
Then press **Ctrl + F5**

---

## **📂 Loading Data (CSV Files)**

The application accepts CSV files formatted like:

```
1,2
2,4.1
3,5
4,7.05
```

No headers, just **x,y** pairs.

To load:

> In the GUI → click **Load CSV**

A Windows file dialog will appear.

---

## **📈 Simulation Controls**

Once running, you can adjust:

* Spawn rate (points/sec)
* True slope & intercept
* Noise variance
* Max buffer size
* Manually add points

All visualizations update instantly.

---

## **🔥 Extra Notes**

* Heatmap resolution can be adjusted (rows/columns)
* Regression recalculates automatically
* CSV loading resets simulation and continues from last x-value
* Works with very large datasets (recommended max ≈ 50,000 points)

---

## **✔ Done**

This README provides everything you need to:

* Build
* Run
* Load data
* Configure ImGui + ImPlot
* Understand the project’s structure

If you want, I can also create:

✅ A **GIF demonstration**
✅ A **wiki-style documentation**
✅ A **YouTube-style demo script**
✅ A **release build packaging guide** (EXE + DLLs)

Just tell me!
