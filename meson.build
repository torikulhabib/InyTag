project('inytag', 'cpp', version: '0.5.0')
gettext_version = meson.project_version()
gettext_name = meson.project_name()
add_project_arguments(['-DGETTEXT_PACKAGE="@0@"'.format(gettext_name)], language: 'cpp',)
add_global_arguments(['-DGETTEXT_PACKAGE="@0@"'.format(gettext_name)], language: 'cpp',)

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
    gettext_name,
    inytag_files,
    dependencies: [
        dependency('taglib'),
    ],
    install: true,
    install_dir: join_paths(get_option('prefix'), get_option('libdir')),
    version: gettext_version,
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
    subdirs: gettext_name,
    filebase: gettext_name,
    name: 'inytag',
    description: 'Simple Taglib for Vala',
    version: gettext_version,
)
