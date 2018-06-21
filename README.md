# GoogleCloudPlatform
This document will guide you to running deep neural network libraries on the Google Cloud Platform. It was specifically designed for [Machine Learning in Practise](https://www.ru.nl/prospectus/socsci/courses-osiris/ai/nwi-imc030-machine-learning-practice/), a course given at the Radboud University. We will guide you trough the following steps:
* Upgrading the GPU quota
* Installing your first Virtual Machine (VM)

Please note that:
* You are responsible for your own budget.
* You _need_ to shut down VMs if you don't need them.
* This guide was designed for running machines in `us-west1`, as those machines are the cheapest.

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

![Install VM](gifs/vm.gif)
