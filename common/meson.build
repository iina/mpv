git = find_program('git', required: false)
if not git.found()
    git = ''
endif

generate_ver = '''
#!/usr/bin/env python3
sys.stdout.write("0.40.0")
'''

version_h = vcs_tag(
    command: [python, '-c', generate_ver, git, source_root, meson.project_version().replace('-UNKNOWN', '')],
    fallback: 'v' + meson.project_version(),
    input: 'version.h.in',
    output: 'version.h',
    replace_string: '@VERSION@',
)

sources += version_h
