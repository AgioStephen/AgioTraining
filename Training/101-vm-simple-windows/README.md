\Download the code from Github
Open Powershell
\Install Azure Powershell
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
connect-azaccount -tenantid {Insert Tenant ID}
get-AZsubscription
Select-AzSubscription {InsertSubscriptionID}


$templateFile = "{Full_Local_Path_template\azuredeploy.json}"
$parameterFile="{Full_local_Path_parameter\azuredeploy.parameters.json}"
$ResourceGroup={ResourceGroupName}

New-AzResourceGroupDeployment `
	-Name LocalDeployment01 `
	-ResourceGroupName $ResourceGroup `
	-TemplateFile $templateFile `
	-TemplateParameterFile $parameterFile
