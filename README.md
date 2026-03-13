# Branching-Tool

Table-Level Branching: Unlike traditional branching systems that operate at the database level, our tool takes it a step further by introducing the concept of branches at the table level. This allows for a more granular and targeted approach to version control within your ClickHouse environment.

Effortless Branch Creation: With just a few simple commands, users can create branches for specific tables, enabling parallel development, experimentation, and testing without affecting the main dataset.

Data-Efficient Workflow: Our tool employs a unique approach that eliminates the need for extra storage. Instead of copying data during branching, it creates symbolic links to the actual data directory. This means that developers can seamlessly access data from these symbolic links without incurring additional storage overhead.



### Installation Pre-request

1- Install clickhouse-driver
<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
pip install clickhouse-driver
</code></pre>

2- Install resync

<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
sudo apt-get update
sudo apt-get install resync
</code></pre>

3- Install Click

<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
sudo apt-get install Click
</code></pre>

#### Usage
<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
Usage: clickhouse-branching.py [OPTIONS]

Options:
  --database TEXT     Database name
  --table TEXT        Table name
  --branch-name TEXT  Branch name
  --username TEXT     ClickHouse username
  --password TEXT     ClickHouse password
  --hostname TEXT     ClickHouse hostname
  --port TEXT         ClickHouse port
  --help              Show this message and exit.
</code></pre>


#### Run the Script
<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
python3 clickhouse-branching.py --database default --table uk_price_paid --branch-name tabletest --username default --password '' --hostname localhost --port 9000
</code></pre>


#### Example Output

Following uk_price_paid table is 4 GB. Creating branch with new table name will take 5.878 seconds.

<pre id="example"><code class="language-lang"  style="color: #333; background: #f8f8f8;">
The table default.uk_price_paid has been frozen with name 'default.uk_price_paid_tabletest'
Table information is saved into /tmp/default.uk_price_paid.sql
New Table information is saved into /tmp/default.uk_price_paid_tabletest.sql
Table default.uk_price_paid_tabletest created successfully.
/var/lib/clickhouse/shadow/default%2Euk_price_paid_tabletest/store/e64/e64c4657-416b-40af-abde-275b70f9672c
/var/lib/clickhouse/data/default/uk_price_paid_tabletest/detached/
sending incremental file list
./
all_13_18_1/
all_13_18_1/addr1.bin
all_13_18_1/addr1.cmrk2
all_13_18_1/addr2.bin
all_13_18_1/addr2.cmrk2
all_13_18_1/checksums.txt
all_13_18_1/columns.txt
all_13_18_1/count.txt
all_13_18_1/county.bin
all_13_18_1/county.cmrk2
all_13_18_1/county.dict.bin
all_13_18_1/county.dict.cmrk2
all_13_18_1/date.bin
all_13_18_1/date.cmrk2
all_13_18_1/default_compression_codec.txt
all_13_18_1/district.bin
all_13_18_1/district.cmrk2
all_13_18_1/district.dict.bin
all_13_18_1/district.dict.cmrk2
all_13_18_1/duration.bin
all_13_18_1/duration.cmrk2
all_13_18_1/is_new.bin
all_13_18_1/is_new.cmrk2
all_13_18_1/locality.bin
all_13_18_1/locality.cmrk2
all_13_18_1/locality.dict.bin
all_13_18_1/locality.dict.cmrk2
all_13_18_1/postcode1.bin
all_13_18_1/postcode1.cmrk2
all_13_18_1/postcode1.dict.bin
all_13_18_1/postcode1.dict.cmrk2
all_13_18_1/postcode2.bin
all_13_18_1/postcode2.cmrk2
all_13_18_1/postcode2.dict.bin
all_13_18_1/postcode2.dict.cmrk2
all_13_18_1/price.bin
all_13_18_1/price.cmrk2
all_13_18_1/primary.cidx
all_13_18_1/serialization.json
all_13_18_1/street.bin
all_13_18_1/street.cmrk2
all_13_18_1/street.dict.bin
all_13_18_1/street.dict.cmrk2
all_13_18_1/town.bin
all_13_18_1/town.cmrk2
all_13_18_1/town.dict.bin
all_13_18_1/town.dict.cmrk2
all_13_18_1/type.bin
all_13_18_1/type.cmrk2
all_19_24_1/
all_19_24_1/addr1.bin
all_19_24_1/addr1.cmrk2
all_19_24_1/addr2.bin
all_19_24_1/addr2.cmrk2
all_19_24_1/checksums.txt
all_19_24_1/columns.txt
all_19_24_1/count.txt
all_19_24_1/county.bin
all_19_24_1/county.cmrk2
all_19_24_1/county.dict.bin
all_19_24_1/county.dict.cmrk2
all_19_24_1/date.bin
all_19_24_1/date.cmrk2
all_19_24_1/default_compression_codec.txt
all_19_24_1/district.bin
all_19_24_1/district.cmrk2
all_19_24_1/district.dict.bin
all_19_24_1/district.dict.cmrk2
all_19_24_1/duration.bin
all_19_24_1/duration.cmrk2
all_19_24_1/is_new.bin
all_19_24_1/is_new.cmrk2
all_19_24_1/locality.bin
all_19_24_1/locality.cmrk2
all_19_24_1/locality.dict.bin
all_19_24_1/locality.dict.cmrk2
all_19_24_1/postcode1.bin
all_19_24_1/postcode1.cmrk2
all_19_24_1/postcode1.dict.bin
all_19_24_1/postcode1.dict.cmrk2
all_19_24_1/postcode2.bin
all_19_24_1/postcode2.cmrk2
all_19_24_1/postcode2.dict.bin
all_19_24_1/postcode2.dict.cmrk2
all_19_24_1/price.bin
all_19_24_1/price.cmrk2
all_19_24_1/primary.cidx
all_19_24_1/serialization.json
all_19_24_1/street.bin
all_19_24_1/street.cmrk2
all_19_24_1/street.dict.bin
all_19_24_1/street.dict.cmrk2
all_19_24_1/town.bin
all_19_24_1/town.cmrk2
all_19_24_1/town.dict.bin
all_19_24_1/town.dict.cmrk2
all_19_24_1/type.bin
all_19_24_1/type.cmrk2
all_1_6_1/
all_1_6_1/addr1.bin
all_1_6_1/addr1.cmrk2
all_1_6_1/addr2.bin
all_1_6_1/addr2.cmrk2
all_1_6_1/checksums.txt
all_1_6_1/columns.txt
all_1_6_1/count.txt
all_1_6_1/county.bin
all_1_6_1/county.cmrk2
all_1_6_1/county.dict.bin
all_1_6_1/county.dict.cmrk2
all_1_6_1/date.bin
all_1_6_1/date.cmrk2
all_1_6_1/default_compression_codec.txt
all_1_6_1/district.bin
all_1_6_1/district.cmrk2
all_1_6_1/district.dict.bin
all_1_6_1/district.dict.cmrk2
all_1_6_1/duration.bin
all_1_6_1/duration.cmrk2
all_1_6_1/is_new.bin
all_1_6_1/is_new.cmrk2
all_1_6_1/locality.bin
all_1_6_1/locality.cmrk2
all_1_6_1/locality.dict.bin
all_1_6_1/locality.dict.cmrk2
all_1_6_1/postcode1.bin
all_1_6_1/postcode1.cmrk2
all_1_6_1/postcode1.dict.bin
all_1_6_1/postcode1.dict.cmrk2
all_1_6_1/postcode2.bin
all_1_6_1/postcode2.cmrk2
all_1_6_1/postcode2.dict.bin
all_1_6_1/postcode2.dict.cmrk2
all_1_6_1/price.bin
all_1_6_1/price.cmrk2
all_1_6_1/primary.cidx
all_1_6_1/serialization.json
all_1_6_1/street.bin
all_1_6_1/street.cmrk2
all_1_6_1/street.dict.bin
all_1_6_1/street.dict.cmrk2
all_1_6_1/town.bin
all_1_6_1/town.cmrk2
all_1_6_1/town.dict.bin
all_1_6_1/town.dict.cmrk2
all_1_6_1/type.bin
all_1_6_1/type.cmrk2
all_25_25_0/
all_25_25_0/addr1.bin
all_25_25_0/addr1.cmrk2
all_25_25_0/addr2.bin
all_25_25_0/addr2.cmrk2
all_25_25_0/checksums.txt
all_25_25_0/columns.txt
all_25_25_0/count.txt
all_25_25_0/county.bin
all_25_25_0/county.cmrk2
all_25_25_0/county.dict.bin
all_25_25_0/county.dict.cmrk2
all_25_25_0/date.bin
all_25_25_0/date.cmrk2
all_25_25_0/default_compression_codec.txt
all_25_25_0/district.bin
all_25_25_0/district.cmrk2
all_25_25_0/district.dict.bin
all_25_25_0/district.dict.cmrk2
all_25_25_0/duration.bin
all_25_25_0/duration.cmrk2
all_25_25_0/is_new.bin
all_25_25_0/is_new.cmrk2
all_25_25_0/locality.bin
all_25_25_0/locality.cmrk2
all_25_25_0/locality.dict.bin
all_25_25_0/locality.dict.cmrk2
all_25_25_0/postcode1.bin
all_25_25_0/postcode1.cmrk2
all_25_25_0/postcode1.dict.bin
all_25_25_0/postcode1.dict.cmrk2
all_25_25_0/postcode2.bin
all_25_25_0/postcode2.cmrk2
all_25_25_0/postcode2.dict.bin
all_25_25_0/postcode2.dict.cmrk2
all_25_25_0/price.bin
all_25_25_0/price.cmrk2
all_25_25_0/primary.cidx
all_25_25_0/serialization.json
all_25_25_0/street.bin
all_25_25_0/street.cmrk2
all_25_25_0/street.dict.bin
all_25_25_0/street.dict.cmrk2
all_25_25_0/town.bin
all_25_25_0/town.cmrk2
all_25_25_0/town.dict.bin
all_25_25_0/town.dict.cmrk2
all_25_25_0/type.bin
all_25_25_0/type.cmrk2
all_26_26_0/
all_26_26_0/addr1.bin
all_26_26_0/addr1.cmrk2
all_26_26_0/addr2.bin
all_26_26_0/addr2.cmrk2
all_26_26_0/checksums.txt
all_26_26_0/columns.txt
all_26_26_0/count.txt
all_26_26_0/county.bin
all_26_26_0/county.cmrk2
all_26_26_0/county.dict.bin
all_26_26_0/county.dict.cmrk2
all_26_26_0/date.bin
all_26_26_0/date.cmrk2
all_26_26_0/default_compression_codec.txt
all_26_26_0/district.bin
all_26_26_0/district.cmrk2
all_26_26_0/district.dict.bin
all_26_26_0/district.dict.cmrk2
all_26_26_0/duration.bin
all_26_26_0/duration.cmrk2
all_26_26_0/is_new.bin
all_26_26_0/is_new.cmrk2
all_26_26_0/locality.bin
all_26_26_0/locality.cmrk2
all_26_26_0/locality.dict.bin
all_26_26_0/locality.dict.cmrk2
all_26_26_0/postcode1.bin
all_26_26_0/postcode1.cmrk2
all_26_26_0/postcode1.dict.bin
all_26_26_0/postcode1.dict.cmrk2
all_26_26_0/postcode2.bin
all_26_26_0/postcode2.cmrk2
all_26_26_0/postcode2.dict.bin
all_26_26_0/postcode2.dict.cmrk2
all_26_26_0/price.bin
all_26_26_0/price.cmrk2
all_26_26_0/primary.cidx
all_26_26_0/serialization.json
all_26_26_0/street.bin
all_26_26_0/street.cmrk2
all_26_26_0/street.dict.bin
all_26_26_0/street.dict.cmrk2
all_26_26_0/town.bin
all_26_26_0/town.cmrk2
all_26_26_0/town.dict.bin
all_26_26_0/town.dict.cmrk2
all_26_26_0/type.bin
all_26_26_0/type.cmrk2
all_27_27_0/
all_27_27_0/addr1.bin
all_27_27_0/addr1.cmrk2
all_27_27_0/addr2.bin
all_27_27_0/addr2.cmrk2
all_27_27_0/checksums.txt
all_27_27_0/columns.txt
all_27_27_0/count.txt
all_27_27_0/county.bin
all_27_27_0/county.cmrk2
all_27_27_0/county.dict.bin
all_27_27_0/county.dict.cmrk2
all_27_27_0/date.bin
all_27_27_0/date.cmrk2
all_27_27_0/default_compression_codec.txt
all_27_27_0/district.bin
all_27_27_0/district.cmrk2
all_27_27_0/district.dict.bin
all_27_27_0/district.dict.cmrk2
all_27_27_0/duration.bin
all_27_27_0/duration.cmrk2
all_27_27_0/is_new.bin
all_27_27_0/is_new.cmrk2
all_27_27_0/locality.bin
all_27_27_0/locality.cmrk2
all_27_27_0/locality.dict.bin
all_27_27_0/locality.dict.cmrk2
all_27_27_0/postcode1.bin
all_27_27_0/postcode1.cmrk2
all_27_27_0/postcode1.dict.bin
all_27_27_0/postcode1.dict.cmrk2
all_27_27_0/postcode2.bin
all_27_27_0/postcode2.cmrk2
all_27_27_0/postcode2.dict.bin
all_27_27_0/postcode2.dict.cmrk2
all_27_27_0/price.bin
all_27_27_0/price.cmrk2
all_27_27_0/primary.cidx
all_27_27_0/serialization.json
all_27_27_0/street.bin
all_27_27_0/street.cmrk2
all_27_27_0/street.dict.bin
all_27_27_0/street.dict.cmrk2
all_27_27_0/town.bin
all_27_27_0/town.cmrk2
all_27_27_0/town.dict.bin
all_27_27_0/town.dict.cmrk2
all_27_27_0/type.bin
all_27_27_0/type.cmrk2
all_28_28_0/
all_28_28_0/addr1.bin
all_28_28_0/addr1.cmrk2
all_28_28_0/addr2.bin
all_28_28_0/addr2.cmrk2
all_28_28_0/checksums.txt
all_28_28_0/columns.txt
all_28_28_0/count.txt
all_28_28_0/county.bin
all_28_28_0/county.cmrk2
all_28_28_0/county.dict.bin
all_28_28_0/county.dict.cmrk2
all_28_28_0/date.bin
all_28_28_0/date.cmrk2
all_28_28_0/default_compression_codec.txt
all_28_28_0/district.bin
all_28_28_0/district.cmrk2
all_28_28_0/district.dict.bin
all_28_28_0/district.dict.cmrk2
all_28_28_0/duration.bin
all_28_28_0/duration.cmrk2
all_28_28_0/is_new.bin
all_28_28_0/is_new.cmrk2
all_28_28_0/is_new.sparse.idx.bin
all_28_28_0/is_new.sparse.idx.cmrk2
all_28_28_0/locality.bin
all_28_28_0/locality.cmrk2
all_28_28_0/locality.dict.bin
all_28_28_0/locality.dict.cmrk2
all_28_28_0/postcode1.bin
all_28_28_0/postcode1.cmrk2
all_28_28_0/postcode1.dict.bin
all_28_28_0/postcode1.dict.cmrk2
all_28_28_0/postcode2.bin
all_28_28_0/postcode2.cmrk2
all_28_28_0/postcode2.dict.bin
all_28_28_0/postcode2.dict.cmrk2
all_28_28_0/price.bin
all_28_28_0/price.cmrk2
all_28_28_0/primary.cidx
all_28_28_0/serialization.json
all_28_28_0/street.bin
all_28_28_0/street.cmrk2
all_28_28_0/street.dict.bin
all_28_28_0/street.dict.cmrk2
all_28_28_0/town.bin
all_28_28_0/town.cmrk2
all_28_28_0/town.dict.bin
all_28_28_0/town.dict.cmrk2
all_28_28_0/type.bin
all_28_28_0/type.cmrk2
all_7_12_1/
all_7_12_1/addr1.bin
all_7_12_1/addr1.cmrk2
all_7_12_1/addr2.bin
all_7_12_1/addr2.cmrk2
all_7_12_1/checksums.txt
all_7_12_1/columns.txt
all_7_12_1/count.txt
all_7_12_1/county.bin
all_7_12_1/county.cmrk2
all_7_12_1/county.dict.bin
all_7_12_1/county.dict.cmrk2
all_7_12_1/date.bin
all_7_12_1/date.cmrk2
all_7_12_1/default_compression_codec.txt
all_7_12_1/district.bin
all_7_12_1/district.cmrk2
all_7_12_1/district.dict.bin
all_7_12_1/district.dict.cmrk2
all_7_12_1/duration.bin
all_7_12_1/duration.cmrk2
all_7_12_1/is_new.bin
all_7_12_1/is_new.cmrk2
all_7_12_1/locality.bin
all_7_12_1/locality.cmrk2
all_7_12_1/locality.dict.bin
all_7_12_1/locality.dict.cmrk2
all_7_12_1/postcode1.bin
all_7_12_1/postcode1.cmrk2
all_7_12_1/postcode1.dict.bin
all_7_12_1/postcode1.dict.cmrk2
all_7_12_1/postcode2.bin
all_7_12_1/postcode2.cmrk2
all_7_12_1/postcode2.dict.bin
all_7_12_1/postcode2.dict.cmrk2
all_7_12_1/price.bin
all_7_12_1/price.cmrk2
all_7_12_1/primary.cidx
all_7_12_1/serialization.json
all_7_12_1/street.bin
all_7_12_1/street.cmrk2
all_7_12_1/street.dict.bin
all_7_12_1/street.dict.cmrk2
all_7_12_1/town.bin
all_7_12_1/town.cmrk2
all_7_12_1/town.dict.bin
all_7_12_1/town.dict.cmrk2
all_7_12_1/type.bin
all_7_12_1/type.cmrk2

sent 327,670,989 bytes  received 7,417 bytes  43,690,454.13 bytes/sec
total size is 327,565,238  speedup is 1.00
Attach copy successfully done.
[]
</code></pre>
