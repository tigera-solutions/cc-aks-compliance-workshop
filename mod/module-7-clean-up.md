# Module 7 - Clean up

1. Delete the applications stack to clean up any `loadbalancer` services.

   ```bash
   kubectl delete -f web
   kubectl delete -f pre/004-vote-app-manifest.yaml
   ```

2. Delete the AKS cluster.
   
   ```bash
   az aks delete \
     --resource-group $RESOURCE_GROUP \
     --name $CLUSTERNAME
   ```

3. If you didn't yet, delete the virtual machine created with terraform for the `tigera-scanner` tests.

   ```bash
   cd tfm
   source ~/workshopvars.env 
   terraform destroy -auto-approve
   ```

4. Delete the resource group.
   
   ```bash
   az group delete \
     --name $RESOURCE_GROUP
   ```

5. Delete environment variables backup file.

   ```bash
   rm ~/workshopvars.env
   ```

6. Delete this cloned repository

   ```bash
   rm -Rf cc-aks-strengthen-security-workshop
   ```
---

[:arrow_left: Module 6 - Quarantine Infected Workloads and KSPM](/mod/module-6-quarantine-kspm.md)  <br>

[:leftwards_arrow_with_hook: Back to Main](/README.md) 