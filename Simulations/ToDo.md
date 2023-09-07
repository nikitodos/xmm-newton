# Lista delle cose da fare

+ Trasformare tutti i dati in formato Python/Colab;
+ Eseguire i fit con i dati simulati della funzione a pag. 6 delle References di Data Analysis di A. Tiengo;
+ Plottare l'una sopra all'altra la funzione di fit dai dati sperimentali (di Tiengo) con quella dai dati simulati (mia).

Nota bene:
+ F(E) è la distribuzione (counts) dei protoni (che sono stati emessi) in funzione dell'energia iniziale;
+ Ef thin/thick sono parametri (da fittare) chiamati energie di folding, e descrivono il decadimento dell'esponenziale;
+ Perdita di energia=ΔE+c*E*np.exp(-E/Ef);
+ ΔE è un'incertezza dovuta allo spettro osservato;
+ E è l'energia finale.

Se questo passaggio va bene, si procede con il fit simultaneo - ovvero dei due spettri di MOS1 E MOS 2 insieme.
In caso si può anche testare il sistema invertendo gli strati
