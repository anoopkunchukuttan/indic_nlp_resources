# Transliteration Models for Indian languages
These are models for transliteration involving Indian languages. 
The models are essentially Statistical Machine Translation systems trained using Moses over a
character-level parallel corpora of transliterations. Hence, you will need Moses to use these transliteration models.
The transliteration corpus has itself been mined in an unsupervised fashion from a translation corpus. 

Commands to run the transliteration module using moses

$moseshome/mosesdecoder/scripts/Transliteration/post-decoding-transliteration.pl  \  
--moses-src-dir $moseshome/mosesdecoder --external-bin-dir $moseshome/tools \  
--transliteration-model-dir {path to transliteration model folder} --oov-file {path to file containing oov words, oovs are space separated with each line containing all oovs for the input line}\  
 --input-file {input file to transliterated}  --output-file {output file location} \  
 --input-extension {input language code for eg. en} --output-extension {output language code for eg. hi} --language-model {path to language model}   
 --decoder $moseshome/mosesdecoder/bin/moses  

A sample execution of the model will be as follows:   

export moseshome=/home/raj/ratish/ililmt/statisticalpostediting/moses  
$moseshome/mosesdecoder/scripts/Transliteration/post-decoding-transliteration.pl  \  
--moses-src-dir $moseshome/mosesdecoder --external-bin-dir $moseshome/tools \  
--transliteration-model-dir /home/raj/ratish/project/icon-smt/moses/working-ems-en-hi-translit/model/Transliteration.5 \  
--oov-file /home/raj/ratish/project/icon-smt/moses/working-ems-en-hi-translit/evaluation/newstest2011.output.5.oov \  
 --input-file /home/raj/ratish/project/icon-smt/moses/working-ems-en-hi-translit/evaluation/newstest2011.cleaned.5  \  
 --output-file /home/raj/ratish/project/icon-smt/moses/working-ems-en-hi-translit/evaluation/translated.out.hi \  
 --input-extension en --output-extension hi --language-model /home/raj/ratish/project/icon-smt/moses/working-ems-en-hi-translit/lm/nc.binlm.1 \  
 --decoder $moseshome/mosesdecoder/bin/moses  
