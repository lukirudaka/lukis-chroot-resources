# Hardware Acceleration Resources

  Freedreno Turnip: https://drive.google.com/file/u/0/d/1f4pLvjDFcBPhViXGIFoRE3Xc8HWoiqG-/view?pli=1
  - plays nicely with virgl, just use LIBGL_KOPPER_DISABLE and the classic GALLIUM_DRIVER to control when to use it. latest precompiled version I could find.
  - only works on qualcomm SOCs
  - this precompiled version also comes with the adreno 7xx patch applied.
  - version in this gdrive link is 24.1, which is pretty recent as of writing this.  
  
xMeM made a vulkan wrapper ICD for Termux that allows you to keep vulkan-loader-generic, and it's being mirrored at https://github.com/sabamdarif/termux-desktop/releases.  
I have also gotten virtio-gpu VENUS going which allows the wrapper ICD mentioned above to pass it's driver through virgl to the proot. In order for this to work, the following environment variables need to be set in the proot/chroot environment:
```
VN_DEBUG=vtest VK_DRIVER_FILES=/usr/share/vulkan/icd.d/virtio_icd.aarch64.json
```
  You can also run virgl_test_server_android at the same time so long as you pass ```virgl_test_server --venus --no-virgl``` instead of just running ```virgl_test_server --venus```. If you're on an Exynos SOC with an Xclipse GPU, it's best to run Venus and virgl_test_server_android at the same time, with virgl_test_server_android having the ```--angle-vulkan``` option on. The proprietary vulkan driver for Xclipse GPUs is incredibly good as it stands, so it's best to do any openGL translations from vulkan either via Zink or via ANGLE. Virgl VENUS is really only for running pure vulkan applications, though, and even then I've really only seen it work under Electron and Chrome. Other use cases didn't work, such as DXVK. More advanced 3d rendering stuff just.. doesn't work really. Don't expect games to work, because I really did NOT know what I did to get this working, but it was probably something very stupid.
  
  panfrost VK?? (rumored)
  - can't find any evidence to back this up, don't have a way to try it either as I have no devices with Mali GPUs as of right now. only xclipse lol
