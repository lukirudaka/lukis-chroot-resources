# Hardware Accerleration Resources

  Freedreno Turnip: https://drive.google.com/file/u/0/d/1f4pLvjDFcBPhViXGIFoRE3Xc8HWoiqG-/view?pli=1
  - plays nicely with virgl, just use LIBGL_KOPPER_DISABLE and the classic GALLIUM_DRIVER to control when to use it. latest precompiled version I could find.
  - only works on qualcomm SOCs
  - this precompiled version also comes with the adreno 7xx patch applied.
  - version in this gdrive link is 24.1, which is pretty recent as of writing this.
  
  vulkan-loader-android: termux package
  - native termux only :(
  - passes vulkan drivers from the system to Termux
  - should we ever get virtio vulkan working, this'll be the way to go for anyone not using a qualcomm SOC.
  - some vendor drivers for qualcomm SOCs dont expose all vulkan APIs so use the freedreno driver if you can.

  panfrost VK?? (rumored)
  - can't find any evidence to back this up, don't have a way to try it either as I have no devices with Mali GPUs as of right now. only powervr and qualcomm lol
