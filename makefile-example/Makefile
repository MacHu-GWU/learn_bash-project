py_ver_major="2"
py_ver_minor="7"
py_ver_path="13"
venv_name="venv"

# options: pyenv_virtualenv / virtualenv / system
pyenv="system"

py_version="${py_ver_major}.${py_ver_minor}.${py_ver_path}"

ifeq (${pyenv}, "pyenv_virtualenv")
    python="${HOME}/.pyenv/versions/${py_version}/envs/${venv_name}/bin/python"
    pip="${HOME}/.pyenv/versions/${py_version}/envs/${venv_name}/bin/pip"
endif

ifeq (${pyenv}, "virtualenv")
    python="./${venv_name}/bin/python"
    pip="./${venv_name}/bin/pip"
endif

ifeq (${pyenv}, "system")
    python="python${py_ver_major}.${py_ver_minor}"
    pip="pip"${py_ver_major}"."${py_ver_minor}
endif

.PHONY: try
try:
	${python} --version
	${pip} list