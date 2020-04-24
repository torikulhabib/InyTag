project('inytag', 'cpp', version: '0.5.0')
add_project_arguments(['-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name())], language: 'cpp',)
add_global_arguments(['-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name())], language: 'cpp',)

pkg_mod = import('pkgconfig')

inytag_c_files = files(
    'Source/inytag.cpp',
)

inytag_h_files = files(
    'Source/inytag.h',
)

inytag_files = [
    inytag_c_files,
    inytag_h_files,
]

inytag_files_lib = shared_library(
    meson.project_name(),
    inytag_files,
    dependencies: [
        dependency('taglib'),
    ],
    install: true,
    version: meson.project_version(),
)

install_headers(
    inytag_h_files,
)

declare_dependency(
    link_with: inytag_files_lib,
    include_directories: include_directories('.'),
)
subdir('Vapi')
pkg_mod.generate(
    inytag_files_lib,
    subdirs: meson.project_name(),
    filebase: meson.project_name(),
    name: 'inytag',
    description: 'Simple Taglib for Vala',
    version: meson.project_version(),
)
