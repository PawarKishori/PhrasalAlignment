# PhrasalAlignment

Anusaaraka is a rule based English-Hindi Machine Translation system, which has integrated various tools to give a machine translation tool.

Bootstrapping using alignment tool.
The goal of this project is to use Alignment tool for bootstrapping, which results in development of Eng-Hin parallel corpora.
 We can also improve existing hindi rule based parser by this procedure. So its a cycle. Its a debugging tool. Alignment tool leads to 
 improve accuracy of Hindi parser and a good Hindi parser will help to create an parallel Treebank.
 
 This tool will help to automate the procedure of corpus creation, which is vital in creation of resources, which drastically reduces the human cost as well as time required to create a Treebank.

Alignment tool is a tool which takes following outputs as input:
1. Anusaaraka Eng-Hin translation
2. SMT output
 And it gives alignment on word, phrase and parser level. 

sh run.sh <phrase-table-en-hi> <phrase-table-hi-en> <corpus_name>
 sh run.sh phrases_en-hi  phrases_hi-en  physics
 sh run.sh gyan_nidhi_en_hi_wx gyan_nidhi_hi_en_wx gyan_nidhi

This command takes the phrase table of the corpus created by Phrasal tool and changes this phrase output into dictionary gdbm format.
The gdbm output(gyan_nidhi_en_hi_wx, gyan_nidhi_hi_en_wx) will be saved in /anusaaraka/miscellaneous/SMT/phrasal_alignment

To run Alignment tool on parallel corpus, input is parallel chunks of sentences given parallel corpus. These are obtained by training parallel corpus on a statistical tool - Phrsal tool. So on 30k gyan nidhi parallel sentences, Phrasal is ran and we got gyan_nidhi_en_hi_wx and gyan_nidhi_hi_en_wx. These are phrase tables we obtatined, which are stored in gyan_nighi folder

sh run_alignment.sh e1 h1 gyan_nidhi
This command is used to run alignment tool on parallel corpus e1 and h1, which also uses gyan_nidhi dictionary (gdbm- created by above run.sh command)

After that we need to do compilation steps to run alignment data.

*****
Giving error

Debugging:
/anusaaraka$ git diff --namestatus
error: invalid option: --namestatus
master@kishori-ThinkCentre-E73:~/anusaaraka$ git diff --name-status
M       multifast-v1.4.2/src/phrasal_mwe/extract_hindi_key.c
M       multifast-v1.4.2/src/phrasal_mwe/extract_key-hi-en.c
M       multifast-v1.4.2/src/phrasal_mwe/extract_key.c

git checkout all these 3 files
++
Did some changes in run_alignment.sh // which was not committed
******
After successfully running phrasal alignment output will be generated in following dir with filename_eng_slign.html file
firefox /home/master/anu_output/e1_eng_align.html

The backend files of phrasal alignment will be in :
cd /home/master/tmp_anu_dir/tmp/gyan_nidhi_e500_tmp/

