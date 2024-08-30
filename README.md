# Convert_DomainNet126
convert domainnet to domainnet126

## Download dataset
Download DomainNet dataset.
```bash
#!/bin/bash

echo "Download DomainNet"
URL="http://csr.bu.edu/ftp/visda/2019/multi-source/"
DOMAINS=("groundtruth/clipart" "infograph" "groundtruth/painting" "quickdraw" "real" "sketch")

for domain in "${DOMAINS[@]}"
do
    echo "Download domain $domain"
    download_url="$URL$domain.zip"
    wget -b $download_url
done
```
Unzip dataset and organize as follows
```
data_dir
--clipart
----aircraft_carrier
      clipart_001_000001.jpg
      clipart_001_000002.jpg
--infograph
--painting
--quickdraw
--real
--sketch
```

## Convert
```python
python convert_domainnet126.py --raw_data_path your_dir --output_path output_dir
```
