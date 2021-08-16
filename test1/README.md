
grid datastore create --name cm-ds --source .

grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type g4dn.4xlarge test1/argecho.py \
--lr .000001

