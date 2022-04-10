# Backup all conda environments

A small Python snippet inspired by _@bgriffen_ to backup all your anaconda environments automatically without having to check each env one-by-one.

```Python
# write environment packages out
for env in env_names:
    print("Backing up...",env)
    cmd = "conda env export --name %s > %s\%s.yml" % (env,dirname,env)
    sub.check_call(cmd,shell=True)

print("Backup complete and stored in "+dirname)
```
## Backup

Running the cell from backup.ipynb saves the `environment.yml` files in a separate dated folder.

## Recover from backup
To reconstruct the conda environment from the yml file, use the following command:
```
conda env create -f environment.yml
```