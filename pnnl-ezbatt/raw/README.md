# Raw Data from Box

Download the "DegredationV2" data [from Box](https://app.box.com/folder/263565529882) then compress the `data` folder into a tar file:

```bash

tar cvf data.tar data
rm -r data
gzip --verbose --best data.tar
```