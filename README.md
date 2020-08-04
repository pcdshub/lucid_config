LUCID Configurations
====================

Individual LUCID home screens are launched using small bash functions.

Where do these settings come from?
----------------------------------

Using the LFE screen as an example, and showing where the configuration settings come from:

`EPICS_SETUP` is configured in the setup scripts:
```
/reg/g/pcds/setup/fixed-epics-setup.sh:export EPICS_SETUP=/reg/g/pcds/setup
```

And shortcut functions are defined in `pcds_shortcuts.sh`:

```bash
lfe ()
{
    ${EPICS_SETUP}/lucid-launcher.sh LFE
}
```

```bash
#!/usr/bin/env bash

source /reg/g/pcds/pyps/conda/dev_conda

lucid "$1" --toolbar=$LUCID_CONFIG/"$1"_toolbar.yaml &
```


where `dev_conda` includes:

```bash
export LUCID_CONFIG=/reg/g/pcds/pyps/apps/hutch-python/lucid_config/
export HAPPI_CFG=/reg/g/pcds/pyps/apps/hutch-python/device_config/happi.cfg
```

And `lucid_config` is this repository.
