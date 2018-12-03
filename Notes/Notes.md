## Documentation Notes
 ### Notes on `bootstrap.py`
**Environment variables used by bootstrap.py:**
 Should these be added to `docstring`?
- TLJH_INSTALL_PREFIX     - Installation path for TLJH (default /opt/tljh)
- TLJH_BOOTSTRAP_DEV      - use --editable option with pip install (default=no, allowable option=yes)
- TLJH_BOOTSTRAP_PIP_SPEC - alternative source to git+https://github.com/jupyterhub/the-littlest-jupyterhub.git
 **What it does:**
- Creates TLJH_INSTALL_PREFIX directory
- Creates TLJH_INSTALL_PREFIX/hub directory
- Creates python3 venv in above
- Writes to TLJH_INSTALL_PREFIX/installer.log
- Creates TLJH_INSTALL_PREFIX/hub/bin/ directory
- Installs python3 there
- runs the tljh.installer
 **How**
- apt-get update
- apt-get python3 python3-venv
- python3 -m venv
- pip install --upgrade TLJH_BOOTSTRAP_PIP_SPEC TLJH_INSTALL_PREFIX/hub
- exec's the virtual env python3 -m tljh.installer with any command line arguments
