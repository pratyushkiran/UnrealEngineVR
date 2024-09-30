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


# Unreal Engine 5: Dynamic Lighting Setup for VR

Since static lighting has been disabled in your VR project, only dynamic lighting will be used. This guide outlines the steps to remove all static light components, set up dynamic lighting using the Environment Light Mixer, adjust viewport settings, and optimize Lumen performance for VR.

## 1. **Remove All Light Components**
- In your scene, remove all **Light Actor** components that were placed by default or manually.
  
## 2. **Set Up Dynamic Lights Using Environment Light Mixer**
1. Go to the **Window** menu and select **Environment Light Mixer**.
2. In the Environment Light Mixer, enable the following:
   - **Create Sky Light**: This adds a dynamic sky light to capture ambient lighting from the sky.
   - **Create Atmospheric Light**: This creates a directional light that represents the sun or moon.
   - **Create Sky Atmosphere**: Adds the sky atmosphere component to simulate realistic sky colors.
   - **Create Volumetric Cloud**: Enables dynamic volumetric clouds for enhanced visual atmosphere.
   - **Create Height Fog**: Adds height fog to create depth in your scene, especially in outdoor environments.

### 2.1 **Configuring Lumen**
By default, Unreal Engine uses high-quality Lumen settings, which can be overkill for VR projects. To optimize for performance, we’ll downscale Lumen quality slightly.

## 3. **Adjusting Viewport Resolution**
1. Go to **Edit > Editor Preferences**.
2. Navigate to **Level Editor > Viewport**.
3. In the **Advanced Settings** section, change the **New Viewport Resolution** to **1920 x 1080**. This will make the preview screen larger for better visibility while developing.

## 4. **Optimizing Lumen for VR**
To maintain a good balance between quality and performance:
1. Go to **Edit > Project Settings > Rendering**.
2. Scroll down to **VR** settings.
3. **Disable Instanced Stereo**:
   - Under **VR**, uncheck **Instanced Stereo** to avoid performance issues that may arise from using Lumen with instanced stereo rendering.

---

With this setup, you’ll be able to leverage dynamic lighting for a fully dynamic VR experience while keeping the performance optimized for VR platforms. You can now further tweak these settings based on your project's needs to achieve the perfect balance between visual fidelity and performance.
