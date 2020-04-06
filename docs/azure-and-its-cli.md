## Stop and deallocate VMs
```
az vm stop --ids $(az vm list --query "[].id" -o tsv --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)
az vm deallocate --ids $(az vm list --query "[].id" -o tsv --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)
```


## List all resource group, then delete a resource group by its name
```
az group list --query "[].name" -o tsv --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
az group delete --yes --no-wait --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx --name  BETTY-RG-XXXX
```

## Show VM's PowerState (use ```jq``` to process JSON output)
```
az vm show -d --ids $(az vm list --query "[].id" -o tsv -g "BETTY-RG-XXXX" --subscription xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx ) | jq '.[] | .name + " [" +  .hardwareProfile.vmSize + "]  =>"  + .powerState'
```
