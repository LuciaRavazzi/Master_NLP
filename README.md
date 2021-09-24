
# Classificazione di Amazon reviews 

Scopo: il dataset fornito è caratterizzato da reviews etichettate in modo binario. Questo permette di
implementare delle tecniche di classificazione. 
A tale scopo, si sono costruiti tre diversi approcci: classificazione pura, supervised sentiment analysis
e classificazione con l'uso di reti neurali.

Tutte le librerie e funzioni utilizzate sono descritte nel file 'LIBRERIE.txt'. In particolare, sono
state utilizzate librerie già fornite da python oppure installate tramite il comando pip.

<ul>
💡 <li>La classificazione pura è stata implementata per diverse rappresentazioni del testo (BOW con pesi
   binari, con frequenze e tf_idf) per diversi tipi di vocabolari. I jupyter del tipo 'Classificazione(min,max)'
   si riferiscono all'implementazione di questo task con un vocabolario caratterizzato da un minimo
   e massimo numero di gram, nello specifico:
	- Classificazione(1,1).ipybn: il vocabolario è costituito solo da 1-gram.
	- Classificazione(1,2).ipybn: il vocabolario è costituito da 1-gram e 2-gram
	- Classificazione(2,2).ipybn: solo 2-gram costituiscono il vocabolario.
   I jupyter sono identici tranne per la differenza legata all'uso di un vocabolario.
   Per poter riprodurre tutti i risultati, è necessario definire il corretto path per il file di train 'train.ft.txt' che
   viene passato alla funzione loader appartenente alla classe preprocessing.
   Poiché la classificazione è stata implementata in cross validation, si è utilizzato solo il dataset di training fornito come se fosse quello totale.</li>

💡 <li>Per la sentiment supervised analysis vi è un solo file jupyter: Classification_sentiment.ipybn
   Per riprodurre i risultati, è necessario caricare il file legato al training set 'train.ft.txt' con la stessa procedura di cui sopra.</li>

💡 <li>Per la classificazione con le reti neurali, sono stati implementati due algoritmi: BERT e FastText.
   Per riprodurre i risultati di BERT è necessario solo caricare il file di train 'train.ft.txt' come descritto in precedenza.
   Per FastText, è necessario utilizzare il terminale di ubuntu. In particolare, il dataset di training
   utilizzato è 'train_sample.txt' e 'test_sample.txt' i quali sono dei campionamenti del dataset di training e test forniti.
   I comandi per classificare le reviews sono i seguenti:
	- Fase di training: ./fasttext supervised -input train_sample -output model -label __label__
	- Fase di test: ./fasttext predict model.bin test_sample > predicted_labels
   Poiché l'algoritmo restituisce solo la recall e la precision, si è deciso di memorizzare le predizioni nel file 'predicted_labels.txt'
   per poi calcolare i valori dell'accuratezza ottenuta. </li>
</ul>
Tutti i codici sono stati scritti e testati attraverso Google Colab PRO dato che i dati forniti hanno richiesto 
una quantità di RAM maggiore rispetto a quella fornita dai nostri terminali.
