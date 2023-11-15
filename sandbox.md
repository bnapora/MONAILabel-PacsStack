## Sample Application

### Download Radiology App
monailabel apps --download --name radiology --output D:\DataSets\Monai\apps

### Start Monai Label Server
monailabel start_server --app D:\DataSets\Monai\apps\radiology --studies http://localhost/dcm4chee-arc/aets/DCM4CHEE/rs --conf models segmentation_spleen

### Download Pathology App
monailabel apps --download --name pathology --output D:\DataSets\Monai\apps

### Start Server
monailabel start_server --app D:\DataSets\Monai\apps\pathology --studies D:\DataSets\GT450_SVS

- Ubuntu
### Start Server
monailabel start_server --port 8001 --app /host_Data/DataSets/Monai/apps/pathology --studies /host_Data/DataSets/GT450_SVS