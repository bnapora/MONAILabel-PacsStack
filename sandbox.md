## Sample Application

### Download Radiology App
monailabel apps --download --name radiology --output D:\DataSets\Monai\apps

### Start Monai Label Server
monailabel start_server --app D:\DataSets\Monai\apps\radiology --studies http://localhost/dcm4chee-arc/aets/DCM4CHEE/rs --conf models segmentation_spleen

### Download Pathology App
monailabel apps --download --name pathology --output D:\DataSets\Monai\apps

### Start Server
monailabel start_server --app D:\DataSets\Monai\apps\pathology --studies D:\DataSets\GT450_SVS

- mlworkspace-localhost
monailabel start_server --port 8001 --app /host_Data/DataSets/Monai/apps/pathology --studies /host_Data/DataSets/GT450_SVS

monailabel start_server --port 8001 --app /host_Data/DataSets/Monai/apps/radiology --studies http://localhost/dcm4chee-arc/aets/DCM4CHEE/rs --conf models segmentation_spleen

- wsl-22.04
monailabel start_server --port 8000 --app /mnt/d/DataSets/Monai/apps/pathology --studies /mnt/d/DataSets/GT450_SVS

monailabel start_server --app /mnt/d/DataSets/Monai/apps/radiology --studies http://localhost/dcm4chee-arc/aets/DCM4CHEE/rs --conf models segmentation_spleen

### Docker Run
docker run -it --rm --gpus all -p 8000:8000 --name monailabel -v /mnt/d/DataSets/Monai/workspace-ubu/:/workspace/ projectmonai/monailabel:latest bash

monailabel apps --download --name radiology --output /workspace/apps

monailabel start_server --host 127.0.0.1 --app /workspace/apps/radiology --studies http://localhost/dcm4chee-arc/aets/DCM4CHEE/rs --conf models segmentation_spleen