project('directx-headers', ['cpp', 'c'])

inc_dirs = ['include', 'include/directx']

if host_machine.system() != 'windows'
    inc_dirs += 'include/wsl/stubs'
endif

directxheaders_dep = declare_dependency(
    include_directories: inc_dirs,
)

meson.override_dependency('directx-headers', directxheaders_dep)
