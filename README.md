# Compariason_guppy_HAC-SUP_config

Job specifics: 
#$ -q gpu.q
#$ -l gpu=1
#$ -l cpu=2


Configuration files are locating within a data folder in Scicomp:
/apps/x86_64/guppy/6.3.8-gpu/data/
HAC file: dna_r10.4_e8.1_hac.cfg
SUP file: dna_r10.4_e8.1_sup.cfg

Guppy version 6.3.8 was used.
module load guppy/6.3.8-gpu

The following command was used to basecall the fast5 files:

guppy_basecaller -i /scicomp/home-pure/ppn7/WORK/SUP_guppy_basecaller/fast5_pass/2023_03_17_MI_MinION/barcode01 -s /scicomp/groups/OID/NCEZID/DPEI/LPRB/BDRD/Mark_Itsko/PenResistance/2023_03_17_MI_MinION/basecalling_HAC/barcode01 --num_callers 14 --gpu_runners_per_device 8 --device cuda:0 --fast5_out --config /apps/x86_64/guppy/6.3.8-gpu/data/dna_r10.4_e8.1_hac.cfg 

The following command was used to time stamp: 
start=`date +%s`
start_time=`date`
...
code
...
end=`date +%s`
end_time=`date`
runtime=$((end-start))
echo "Runtime: $runtime"




A PAF file was created using minimap2 and the mismatches between the sample and the pilon parent Sterne were extracter per sequence keeping the best match only, excluding the secondary possible matches. 


PAF files were filtered to keep sequences that were found in both HAC/SUP configurations. Resulting PAF Files were sorted by sequence ID to ensure that every line belonged to the same sequence.







