# PhrasalAlignment

Anusaaraka is a rule based English-Hindi Machine Translation system, which has integrated various tools to give 
a machine translation tool.

Alignment tool is a tool which takes following outputs as input:
1. Anusaaraka Eng-Hin translation
2. SMT output
 And it gives alignment on word, phrase and parser level. 
 
 The goal of this project is to use Alignment tool for bootstrapping, which results in development of Eng-Hin parallel corpora.
 We can also impprove existing hindi rule based parser by this procedure. So its a cycle. Alignment tool leads to 
 improve accuracy 
 of Hindi parser and a good Hindi parser will help to create an parallel Treebank.
 
 This tool will help to automate the procedure of corpus creation, which is vital in creation of resources, which drastically
 reduces the human cost as well as time required to create a Treebank.
