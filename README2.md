

## Practice - biological databases

 Entrez accessed: $(date)      

Databases used - NCBI-refseq , Uniprot 

1.Data retrived - rbcl_gene from NCBI Refseq as Fasta and Genbank format
and the accession number is NC_000932
 
2.Arabidopsis thaliana esearch done using NBCI e utility API and found the id GI in the json output 

3.MALT-1 mouse protein sequence fetch from Uniprot using accesion id and parsed them with grep , tr -d linux toold 
the protein sequence data more descriptive in text format
   
##Repractice 2026-9-23


## Retrieving sequence from NCBI API : Fasta format and GenBank format 

1.count how many sequeneces grep -c ">" .fasta file 

2.count characters like grep -v "^>" .fasta file | tr -d '\n' | wc -c

3.count the ACGT count -   grep -v "^>" .fasta file | tr -d '\n' |fold -w1 | sort | uniq -c | sort -rn

4.count what are the bases : grep -v "^>" .fasta file | tr -d '\n' |fold -w1 | sort -u

5. find this soft masked or hard masked : grep -v "^>" | grep -o 'a-z' | head -10 and grep -v "^>" | grep -o 'N' | head -10

* Through GenBank format we can get the accession , sequence length what is this molecule and which gene encodes which protein like that 
  Ex - Gene TP53 transcribed in to mRNA transcript variant 1 of TP53 it translated / encode into  tumor protein p53



## Retrieving protein from Uniprot : fasta and text format 

**curl used to get sequence from Uniprotkb , which can be swissprot or Trensembl

** for protein fasta format the sequence / AA length needs to be seen by command (grep and tr -d ) 
** but if we get the protein by txt format from uniprot we can get the length by seeing the header 

grep "^DR   GO;" TP53_protein.txt | grep -o "; C:" | wc -l 

uniq -c and sort -u grep -oE and uniq 

uniq -c - count how many times each character present and sort -u - this is used for sort and remove 
