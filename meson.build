project('simple_launcher', 'c',
  version : '0.1',
  default_options : ['warning_level=3'])

windows = import('windows')
win_res = windows.compile_resources('launcher.rc')

cc = meson.get_compiler('c')
deps = [cc.find_library('shlwapi')]

executable('simple_launcher_cli',
           ['launcher.c', win_res],
           c_args: ['-D_CONSOLE'],
           dependencies: deps,
           win_subsystem: 'console',
           install : true)

executable('simple_launcher_gui',
           ['launcher.c', win_res],
           dependencies: deps,
           win_subsystem: 'windows',
           install : true)
