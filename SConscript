from building import *
import rtconfig

# get current directory
cwd     = GetCurrentDir()
# The set of source files associated with this SConscript file.
src     = Glob('py/*.c')
src    += Glob('lib/mp-readline/*.c')
src    += Glob('lib/utils/*.c')
src    += Glob('extmod/*.c')
src    += Glob('port/*.c')
src    += Glob('lib/netutils/*.c')

path    = [cwd + '/']
path   += [cwd + '/port']
path   += [cwd + '/lib/netutils']

LOCAL_CCFLAGS = ''

if rtconfig.CROSS_TOOL == 'gcc':
    LOCAL_CCFLAGS += ' -std=c99'
elif rtconfig.CROSS_TOOL == 'keil':
    LOCAL_CCFLAGS += ' --c99 --gnu'

group = DefineGroup('MicroPython', src, depend = ['PKG_USING_MICROPYTHON'], CPPPATH = path, LOCAL_CCFLAGS = LOCAL_CCFLAGS)

Return('group')
