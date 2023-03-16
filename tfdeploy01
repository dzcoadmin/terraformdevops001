provider "azurerm" {
    # The "feature" block is required for AzureRM provider 2.x.
    # If you're using version 1.x, the "features" block is not allowed.
    version = "~>2.0"
    features {}
}
 
terraform {
  backend "azurerm" {}
}
 
data "azurerm_client_config" "current" {}
 
resource "azurerm_resource_group" "RG-DZCO" {
  name     = "dzco-tf"
  location = "eastus2"
}
 
resource "azurerm_storage_account" "dzcosa" {
  name                     = "dzcosaf"
  resource_group_name      = azurerm_resource_group.RG-DZCO.name
  location                 = azurerm_resource_group.RG-DZCO.location
  account_tier             = "Standard"
  account_replication_type = "LRS"
}
