# GoogleCloudPlatform
This document will guide you to running deep neural network libraries on the Google Cloud Platform. It was specifically designed for [Machine Learning in Practise](https://www.ru.nl/prospectus/socsci/courses-osiris/ai/nwi-imc030-machine-learning-practice/), a course given at the Radboud University. We will guide you trough the following steps:
* Costs
* Upgrading the GPU quota
* Deploying your first VM

Please note that:
* You are responsible for your own budget.
* You _need_ to shut down VMs if you don't need them.
* This guide was designed for running machines in `us-west1`, as those machines are the cheapest.

## Costs
It is smart to think about costs before spinning up your machine, as you'll quickly go over budget when you leave your machine running.

With the configuration below, you will only be charged when your machine is running, except for the SSD. An SSD costs $0.17 per GB per month. We'll make a quick calculation for a project of two months. With $375 budget and an SSD of 150GB, and some networking, you will have $320.00 left as budget.

A VM costs $0.38 per hour and a Nvidia Tesla P100 will cost you $1.46 per hour, so that adds up to a grand total of $1.84 per hour. This means that you will have about $330 / $1.84 = *170 VM hours*, which is approximately a week of computation. Please use your time wisely and shut down the machine when not in use!

## Upgrading the GPU quota
By default, the GPU quota is set to 0.
1. Go to [IAM Quotas](https://console.cloud.google.com/iam-admin/quotas)
2. Use the filter to search for `NVIDIA P100 GPUs` in `us-west1`. 
3. Check the selectbox and click _Edit Quotas_ in the top left.
4. Enter your contact information and set the new quota limit.
Please note that the request can take some time to process.

![Update Quota](gifs/quota.gif)

## Deploy your first VM
1. Open [AISE TensorFlow NVidia GPU Notebook on Google Cloud Launcher](https://console.cloud.google.com/projectselector/launcher/details/jetware/tensorflow-python-cuda-minilab)
2. Select your project.
3. Under _Zone_, select `us-west1-b`.
4. Increase _Boot disk size in GB_ to the size of your dataset plus approximately 20GB for the operating system.
5. Click _Deploy_
6. The machine should take some time to boot. After it has been succesfully booted, the IP address for Jupyter Notebook and the password will be shown in the panel.

![Install VM](gifs/vm.gif)

## Shutdown a VM
When a VM is not running, you'll be only charged for the costs of the SSD.
1. Open [VM Instances](https://console.cloud.google.com/compute/instances).
2. Select the VM that you want to stop and click _stop_ in the top control bar.

