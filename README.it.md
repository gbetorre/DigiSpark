# DigiSpark

Localizzazione in italiano della libreria per la programmazione del microcontroller a 8 bit Digispark ATTiny85.

## _Nota dell'autore_

_Alcuni anni fa realizzai un progetto sui microcontrollori Arduino compatibili, con un focus particolare sul DigiSpark._

_Quel lavoro, supervisionato dall'allora docente dell'esame di Internet of Things, ha prodotto una documentazione che, trascorsi diversi anni, ho pensato ora di rendere pubblica, sperando che possa essere utile, come spunto o per curiosità, a qualche studente di materie STEM._

---

# Emulazione di periferiche USB tramite microcontrollori e rischi per la sicurezza informatica

&copy; G. Torre, 2021<br>
Progetto:
INTERNET OF THINGS<br>
INGEGNERIA INFORMATICA E DELL'AUTOMAZIONE (D.M. 270/04)

## Introduzione

La pervasività delle porte USB nei moderni computer rappresenta una grande comodità ma comporta
anche elevati rischi per la sicurezza.

Le porte USB, nei PC e Mac, consentono lo scambio di dati tra un gran numero di dispositivi ed il
Personal Computer, permettono di aggiungere con facilità periferiche senza preoccuparsi di riavviare
il sistema o del riconoscimento delle stesse e, non ultimo, offrono anche una moderata tensione che
può permettere la ricarica di dispositivi a basso consumo. Tuttavia, queste comodità hanno una
contropartita in termini di vulnerabilità, e ogni porta USB è di fatto una porta aperta verso il
potenziale rischio di accesso non autorizzato al sistema e la distruzione di dati o, peggio,
l’inserimento di codice malizioso che può originare problemi per la privacy e la sicurezza dei dati.

Il primo dispositivo commerciale di ampia notorietà capace di effettuare attacchi tramite porta USB è
stata la Rubber Ducky. Questa periferica richiedeva però la conoscenza di un linguaggio specifico
per la programmazione degli script e aveva una sua propria architettura.

Oggigiorno, tuttavia, grazie alla ampia diffusione dei microcontrollori (in particolare degli Arduino
compatibili), è diventato possibile costruire dispositivi del genere personalizzati, che è possibile
"camuffare" da chiavette USB e che, essendo sviluppati ad hoc, sono particolarmente elusivi nei
confronti di software di sicurezza (p.es Antivirus). In più, utilizzando Digispark, un microcontroller
compatibile con Arduino, il set di comandi per la programmazione di exploit è semplicemente quello
standard di Arduino e soprattutto le caratteristiche tecniche (16 MHZ a 5V) permettono di
mascherare queste board da periferiche USB (mouse, joystick o tastiere) fornendo in input al sistema
comandi che in realtà sono stati precaricati tramite sketch.

Questo tipo di attacchi può essere effettuato verso tutte le piattaforme: Windows, Mac e Linux,
previa personalizzazione degli script e della sintassi dei comandi eventualmente da eseguire.
Approfondiremo di seguito i dettagli sia implementativi che di programmazione di questo tipo di
interessanti e innovativi microcontrollori, e della loro contropartita in termini di rischi per la
sicurezza informatica.

### 1. - Il microcontrollore Digispark Rev.3 ATTiny85

In questa sezione esamineremo, con qualche dettaglio, la scheda di sviluppo microcontroller
Digispark basata sul chip microcontroller ATTiny85. Vedremo quindi quali sono le caratteristiche
del dispositivo, lo schema e la piedinatura.<br>
Passeremo quindi alla configurazione dell’ambiente operativo destinato alla programmazione del
microcontrollore; in particolare: configurazione dei driver per il riconoscimento da parte del sistema
operativo, connessione del dispositivo, riconoscimento della scheda dall’interno di Arduino IDE.

#### 1.1 - Overview

Il microcontrollore Digispark oggetto di questa tesina è una schedina di sviluppo microcontroller
compatta basata sul chip ATTiny85, un chip microcontroller a 8 bit ad alte prestazioni e bassa
potenza, prodotto un tempo da Atmel - oggi da Microchip -, con 8 KB di memoria flash
programmabile, di cui 2 KB necessari al micronucleo bootloader e 6 KB disponibili per i programmi.
Si tratta di un prodotto molto economico, acquistabile per pochi euro sugli store digitali, ma non per
questo di poco valore; il dispositivo è infatti un raffinato microcontrollore programmabile a 8 bit ad
alte prestazioni, dotato nativamente di un comodo connettore USB OTG e, per di più, compatibile
con Arduino, con cui può essere integrato nei progetti, e la cui programmazione può essere fatta
sfruttando lo stesso IDE, con alcune piccole personalizzazioni che vedremo più avanti.


