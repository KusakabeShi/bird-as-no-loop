# a bird function to check there is no as-loop in the path

Psudo code
```
old_path = bgp_path.copy()

## 以下 block 複製20遍，當作迴圈

current_asn = old_path.last   
asn_count = old_path.filter(current_asn).len
if asn_count == 1:
    pass
if asn_count == 2:
    if [= * current_asn current_asn =] == false:
        reject
if asn_count == 3:
    if [= * current_asn current_asn current_asn =] == false:
        reject
if asn_count == 4:
    if [= * current_asn current_asn current_asn current_asn =] == false:
        reject
if asn_count == 5:
    if [= * current_asn current_asn current_asn current_asn current_asn =] == false:
        reject
if asn_count == 6:
    if [= * current_asn current_asn current_asn current_asn current_asn current_asn =] == false:
        reject
if asn_count == 7:
    if [= * current_asn current_asn current_asn current_asn current_asn current_asn current_asn =] == false:
        reject
if asn_count >= 8:
    reject # too many prepend
old_path = delete(current_asn, old_path)

## 以上 block 複製20遍，當作迴圈

if old_path.len > 0:
    reject
```
