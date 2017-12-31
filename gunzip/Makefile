out/nist/2011.json.gz:
	mkdir -p out/nist
	curl https://static.nvd.nist.gov/feeds/json/cve/1.0/nvdcve-1.0-2011.json.gz > out/nist/2011.json.gz

current_dir := $(shell pwd)
run:
	cd dlang && dub run --quiet --build=release --compiler=ldc2
	cd $(current_dir) && cd java && ./gradlew --quiet
	cd $(current_dir) && cd ruby && ./gunzip_benchmark.rb
	cd $(current_dir) && cd python && ./gunzip_benchmark.py