# setup
```
git clone https://github.com/robert-s-lee/grid-public-tests
cd public-tests
```

# Run all argecho.py without requirements.txt
```bash
for f in $(find . -name "argecho.py" -print); do
  echo $f
  grid run --ignore_warnings $f --lr .000001
done
```


grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium argecho.py \
--lr .000001


grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium argecho.py \
--lr .000001

grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium test1/argecho.py \
--lr .000001


# run
grid run \
--dependency_file test1/requirements.txt
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium test1/argecho.py \
--lr .000001

# will automatically pick up requirements.txt

grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium test1/argecho.py \
--lr .000001

# will automatically pick up requirements.txt

grid run \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type t2.medium test1/test1-copy/argecho.py \
--lr .000001
```

