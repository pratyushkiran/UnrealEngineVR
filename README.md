# Unreal Engine VR Project Setup

This guide will walk you through setting up a VR project in Unreal Engine using the VR Template and configuring essential project settings to ensure optimal performance and visual quality.

## 1. **Creating the Project**
- Open Unreal Engine and select **Games** > **VR** template.
- Choose the **No Starter Content** option for a cleaner project setup (optional).
- Name your project and set the directory for saving.

## 2. **Project Settings Configuration**

After creating the project, follow these steps to configure project settings for VR performance:

### 2.1 **DirectX 12 and Shader Model 6**
1. Navigate to **Edit > Project Settings**.
2. In the **Platforms** section, select **Windows**:
    - Set **Default RHI** to **DirectX 12**.
    - Enable **Shader Model 6** (SM6), if not already enabled.
3. Change the **Target Platform** to **Desktop** and **Scalable** (for high-end VR performance).
4. Restart the Unreal Editor when prompted.

### 2.2 **Lighting and Rendering Settings**

After restarting the editor:
1. Disable **Static Lighting**:
    - In **Project Settings**, go to **Engine > Rendering**.
    - Uncheck **Allow Static Lighting**.
2. Disable **Forward Renderer**:
    - Uncheck **Forward Shading**.
3. Set **Global Illumination**:
    - Under **Dynamic Global Illumination Method**, select **LUMEN**.
4. Adjust **Reflection Capture Resolution** (optional):
    - Default value is 128. You may reduce it if needed to improve performance.

### 2.3 **VR Optimization Settings**

If you notice jitteriness in the VR experience:
1. Disable **Fixed Foveation**:
    - Go to **Project Settings > VR**.
    - Under **HMD Fixed Foveation**, set it to **Disabled**.
2. Disable **Instanced Stereo**:
    - Go to **Project Settings > VR**.
    - Set **Instanced Stereo** to **Disabled**.

### 2.4 **Auto Exposure and Anti-Aliasing Settings**
1. Enable **Auto Exposure**:
    - In **Project Settings**, go to **Engine > Rendering**.
    - Enable **Auto Exposure**.
2. Set **Anti-Aliasing Method**:
    - Change the **Anti-Aliasing Method** to **Temporal Anti-Aliasing (TAA)**.
3. Disable **MSAA**:
    - Set **MSAA Sample Count** to **No MSAA**.
4. Enable **Shader Permutation Reduction**:
    - Check **Support Sky Atmosphere Affecting Height Fog**.

---

With these settings configured, your project should be optimized for VR performance with Unreal Engine. You can now proceed with adding assets, designing levels, and customizing gameplay for your VR application.
