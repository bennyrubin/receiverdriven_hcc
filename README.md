I want to make graphs of:
How each experiment affects the IOMMU hit rate. Graph for each factor probably 
    should I do total IOMMU hitrate? or IOMMU hitrate per packet or per DMA size?

For each factor, graph network tput and retries, maybe memory/pcie bandwidth? as a function of IOMMU on and off 


commands to re-run data extraction script:
arr=( $(ls | grep -v "RUN") )
for i in "${arr[@]}"
do 
sudo python3 collect-tput-stats.py $i 1 0
done

I should extract all the info I need for the plots into the .dat file (and add a header line). Should try to keep it backwards compatible with Saksham's script. Maybe fork a seperate collect-stats.py file for my purposes. 