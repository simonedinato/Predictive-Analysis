# regressione lineare semplice
La regressione lineare semplice è un metodo statistico fondamentale usato per esaminare la relazione tra due variabili, una variabile **dipendente** e una variabile **indipendente**

### in cosa consiste
La regressione lineare semplice (Simple Linear Regression, **SLR**) è una tecnica statistica che permette di *studiare* e *quantificare* la *relazione* tra due variabili. In particolare, si cerca di modellare la relazione tra una variabile **dipendente** ($Y$) e una variabile **indipendente** ($X$) attraverso una linea retta che **minimizza la distanza** (**errori**) tra i valori osservati e i valori predetti dalla retta di regressione

### obiettivo
L'obiettivo della retta di regressione lineare semplice è quello di **predirre** il valore della variabile **dipendente** $Y$ basandosi sul valore della variabile **indipendente** $X$.
Tramite SLR siamo inoltre in grado di predirre la natura della relazione tra le due variabili. La SLR può anche essere utilizzata per testare ipotesi scientifiche riguardo le relazioni tra variabili.

Attraverso la retta di regressione semplice otteniamo la formula matematica di una retta espressa come

$$
Y = a + bX + \epsilon
$$

- $Y$: rappresenta la variabile **dipendente** che vogliamo prevedere o spiegare
- $X$: è la variabile **indipendente** che stiamo usando per la predizione
- $a$: è l'intercetta sull'asse $Y$ della retta di regresssione
- $b$: è la **pendenza** della retta di regressione, rappresenta il cambiamento di $Y$ per unità di cambiamento di $X$
- $\epsilon$: consiste nell'**errore** di stima, ovvero la differenza tra i valori osservati di $Y$ e quelli predetti dall'equazione della retta di regressione

### assunzioni
- **linearità**: indica che la relazione tra la variabile **indipendente** ($X$) e la variabile **dipendente** ($Y$) è lineare. Questo significa che il cambiamento nella variabile dipendente è proporzionale al cambiamento nella variabile indipendente.
- **normalità**: gli erorri del modello (**residui**) devono essere *normalmente distribuiti*, è possibile verificare questa assunzione attraverso test statistici o graficamente come un `plot Q-Q`
- **omoschedascticità**: indica che la **varianza** degli errori è **costante**; la varianza dei residui (errori) deve rimanere costante attraverso i vari valori della variabile indipendente ($X$). Se la varianza cambia a diversi valori della variabile indipendente, allora si dice che la varianza è **eteroschedastica**, la quale può invalidare le predizioni del modello
- **indipendenza dagli errori**: gli errori (residui) devono rimanere indipendenti l'uno dall'altro. Nel caso in cui gli errori sono dipendenti, si parla di **autocorrelazione**, la quale può invalidare le predizioni del modello

Ognuna di queste assunzioni è fondamentale per garantire l'**accuratezza** e l'**affidabilità** del modello di regressione lineare semplice. Nel caso in cui queste assunzioni sono verificate si parla di un modello in grado di fornire stime **unbiased** (non distorte) 

### stima dei parametri
I parametri fondamentali in una retta di regressione lineare semplice sono il coefficente della retta (**pendenza**) e l'**intercetta**. Questi parametri sono scelti in modo da **minimizza** la somma dei quadrati degli errori (residiui) tra i valori osservati e i valori predetti dal modello di regressione.
Il metodo utilizzato per stimare questi parametri è il metodo dei **minimi quadrati**.

#### metodo dei minimi quadrati
Il metodo dei minimi quadrati è una tecnica per stimare la retta di regressione che consiste nel trovare il valore che **minimizza** la somma dei quadrati delle differenze tra i valori osservati e i valori predetti dalla linea di regressione.

$$
a = \overline y - b \overline x \qquad b = \frac{\sum_{i=1}^n (x_i - \overline x)(y_i - \overline y)}{\sum_{i=1}^n (x_i - \overline x)^2} = \frac{c_{xy}}{s^2_x}
$$

Una volata che sono stati trovati i parametri della retta si ha la migliore predizione possibile per quel modello. Prima di poter usare il modello bisogna controllare che sia valido:
- verificare che anche le assunzioni siano valide (omoschedasticità, normalità, indipendenza degli errori)
- valutare quanto bene il modello si **adatta** ai dati, attraverso diversi metodi come il controllo del coefficiente $R^2$ o la verifica dei residui

#### valutazione del modello
Una volta che i parametri del modello sono stati scelti, è necessario assicurarsi che il modello sia **valido** e che si adatti correttamente ai dati. Esistono diversi metodi per valutare il modello:

**coefficiente di determinazione** $R^2$
indica la proporzione tra la varianza della variabile dipendente che è predicibile dalla variabile indipendente;

$$
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
$$

dove $SS_{res}$ indica la somma dei quadrati dei residui e $SS_{tot}$ indica la somma dei quadrati totali (varianza totale)

Il coefficiente $R^2$ restituisce valori compresi tra $0$ e $1$, un valore vicino a $1$ indica che una grande porzione della varianza di $Y$ è spiegata dal modello, mentre un valore vicino a $0$ indica che il modello non è in grado di spiegare correttamente la varainza di $Y$.

**test di significatività dei coefficienti (test t)**
Il **test t** è usato per determinare se i coefficienti di regressione sono significativamente diversi da zero; un coefficiente che non è significativamente diverso da zero è un coefficiente poco significativo e può essere omesso.

$$
t = \frac{b}{SE(b)}
$$

in questo caso $b$ indica il coefficiente che si intende stimare e $SE(b)$ è il suo errore standard; un alto valore di $t$ (o un basso valore di $p$)indica che il coefficiente è significativamente diverso da zero

**intervallo di confidenza**
sono degli intervalli di valori nei quali c'è un'alta probabilità di trovare l'effettivo parametro della popolazione, con un certo livello di confidenza (es. $95 \%$), più è ristretto il parametro e più è precisa la stima

**analisi dei residui**
Dopo aver stimato il modello, è importante esaminare i residui per verificare se le assunzioni del modello sono state soddisfatte. Ciò include la verifica della normalità, omocedasticità, e l'indipendenza degli errori.

**validazione del modello**
la validazione del modello può includere l'uso di dati di convalida per verificare la performance del modello su un set di dati non visto in precedenza. Questo aiuta a garantire che il modello non sia sovraadattato ai dati di addestramento.

**confronto con altri modelli**
potrebbe essere utile confrontare la performance del modello di regressione lineare semplice con altri modelli statistici o di machine learning per valutare se esistono modelli che forniscano previsioni più accurate o insight più utili.

#### diagnostica del modello
questo processo si occupa di identificare eventuali problemi nel modello di regressione lieare e assicurarsi che le assunzioni fatte siano corrette.
Diversi sono gli aspetti che possono essere controllati:

**analisi dei residui**
- consistono nella differenza tra i valori osservati dalla variabile dipendente $Y $ e i valori predetti dal modello di regressione. Analizzando la distribuzione dei residui è possibile individuare problemi nel modello, come la *eteroschedasticità*, *non linearità*, *outliers*.
- comunemente viene fatto il **plot** dei residui contro i valori predetti o la variabile indipendente

#### interpretazione dei risultati
**coefficienti**
- l'intercetta $a$ indica il valore atteso della variabile dipendente $Y$ quando la variabile indipendente $X$ è uguale a $0$
- la pendenza $b$ indica il cambiamento atteso nella variabile dipendente $Y$ per unità di cambiamento della variabile indipendente $X$

**statistiche di output**
- coefficiente $p$: rappresenta la possibilità di ottenere un valore estremo, assumendo che la *null hyoptesis* (assenza di relazione tra le variabili) sia verificata. Un valore piccolo (tendenzialmente $p \lt 0.05$) indica che il coefficiente statistico è significativo
- coefficiente di determinazione $R^2$: come spiegato prima, indica la porzione di varianza di $Y$ che viene spiegata dal modello

#### estensioni e limitazioni
quali sono le limitazioni della regressione lineare semplice? quando la regressione lineare semplce è adatta e quando deve essere estesa/modificata per poter affrontare problemi più complessi?

**le assunzioni non vengono soddisfatte**
Se le assunzioni della regressione lineare semplice non sono soddisfatte, le stime dei coefficienti possono essere distorte, e le inferenze statistiche possono essere invalidi. Ad esempio, la presenza di eteroscedasticità o di relazioni non lineari può rendere il modello inadatto.

**dati categorici**
Nella regressione lineare semplice, la variabile indipendente è tipicamente continua. Tuttavia, se si dispone di dati categorici, possono essere convertiti in variabili dummy (0 o 1) per l'inclusione nel modello, anche se ciò è più comune nella regressione lineare multipla.

**regressione lineare multipla**
La regressione lineare multipla è un'estensione della regressione lineare semplice che permette l'inclusione di più variabili indipendenti. Questo modello può catturare relazioni più complesse e fornire insight più dettagliati, ma richiede anche una maggiore attenzione alle assunzioni e alle condizioni del modello.
è possibile fare riferimento al seguente [link](./02-regressione-lineare-multipla.md) per maggiori informazioni.

**trasformazioni delle variabili**
Se la relazione tra la variabile indipendente e quella dipendente non è lineare, potrebbe essere utile trasformare le variabili (ad esempio, logaritmo, radice quadrata) per linearizzare la relazione.
