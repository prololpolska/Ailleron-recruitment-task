# Ailleron-recruitment-task
Create an Infrastructure as a Code terraform script that passes these 6 points:

1. A resource group in the West Europe region called "recruitment-challenge". All resources should be deployed inside the resource group.

2. Create VNet called "recruitment-vnet" with settings: 

	 1.     address_space = 10.0.10.0/23

3. Subnet "recruitment-subnet" with the settings: 

	1.     address_prefixes = 10.0.10.0/24

	2. connect to the "recruitment-vnet" VNet

4. AKS Cluster called "recruitment-aks" with the settings: 
	1. default_node_pool: 

		1.     name = recruitmentpool

	2. autoscale enabled

	3. Available zones: 

		1.     Minimum: 3

		2.     Maximum: 10

	4. use subnet "recruitment-subnet"

	5. System Disks - 256GiB

	6.     dns_prefix = "recruitment-dns-prefix"

	7.     identity = SystemAssigned

	8. network_profile: 

		1.     network_plugin = "azure"

		2.     dns_service_ip = "10.254.0.10"

		3.     docker_bridge_cidr = "172.17.0.1/16"

		4.     service_cidr = "10.254.0.0/16"

	9. auto_scaler_profile: 

		1.     scale_down_utilization_threshold = 0.8

		2.     skip_nodes_with_system_pods = false

		3.     skip_nodes_with_local_storage = false

	10.     role_based_access_control.enabled = true

5. All cloud resources should use the below tags: 

	1.     env: recruitment

	2.     name: AuthorFullName

6. The task can be resolved by any method. 

	1. The code can be delivered as a single file or reusable modules. 

	2. Please use the newer versions of terraform script and provider. 

	3. Terraform Backend should use a storage account - here, please prepare only a configuration template - subscription, state name, 

	4. Please remember to use the best practices, as you know. 

	5. if any setting is required and hasn't been included, use the default values or values preferred by you
