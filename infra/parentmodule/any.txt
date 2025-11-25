rg = {
  rg1 = {
    name     = "devbankrg"
    location = "centralindia"
  }
}

vnet = {
  vnet1 = {
    vnet_name     = "devbankvnet"
    vnet_location = "centralindia"
    rg_name       = "devbankrg"
    address_space = ["10.0.0.0/16"]
    #   dns_servers = 
    # }
  }
}

subnet = {
  subnet1 = {
    subnet_name      = "devbanksubnet"
    rg_name          = "devbankrg"
    vnet_name        = "devbankvnet"
    address_prefixes = ["10.0.1.0/24"]

  }
}
pip = {
  pip1 = {
    pip_name          = "frontendbank-ip"
    rg_name           = "devbankrg"
    pip_location      = "centralindia"
    allocation_method = "Static"

  }
}

lb = {
  lb1 = {
    pip_name = "frontendbank-ip"
    rg_name  = "devbankrg"
    name     = "frontendbanklb"
    location = "centralindia"
  }
}

acr = {
  acr1 = {
    acr_name      = "devbankacr"
    rg_name       = "devbankrg"
    acr_location  = "centralindia"
    admin_enabled = false
    sku           = "Basic"
    # zone_redundancy_enabled = false
    # geo_location = "eastus"
  }
}

aks = {
  aks1 = {
    aks_name       = "devbankaks"
    aks_location   = "centralindia"
    rg_name        = "devbankrg"
    dns_prefix     = "niteshbankaks"
    node_pool_name = "pool2"
    node_count     = 2
    vm_size        = "Standard_D2_v2"
    type_identity  = "SystemAssigned"
  }
}

sqlserver = {
  sqlserver1 = {
    login_username               = "Niteshkumarojha@rajeshprajapati3outlook.onmicrosoft.com"
    object_id                    = "44c71aeb-c5e3-4120-bc48-47adbe961e72"
    minimum_tls_version          = "1.2"
    administrator_login_password = "Admin@843531"
    administrator_login          = "admin"
    sqlserver_location           = "centralindia"
    rg_name                      = "devbankrg"
    sql_name                     = "sqlserver251125"
    version = "12.0"
  }
} 

sqldb = {
  sqldb1 = {
    sqldb_name = "sqldb251126"
    sqlserver_name = "sqlserver251125"
    rg_name = "devbankrg"

  }
}

kv= {
  kv1 = {
    kv_name = "kv251125"
    kv_location = "centralindia"
    rg_name = "devbankrg"
    enabled_for_disk_encryption = true
    soft_delete_retention_days = "7"
    purge_protection_enabled = false
    sku_name = "standard"

  }
}