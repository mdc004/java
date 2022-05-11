# Gestione dei file in java

I file, in java, si possono dividere in file di oggetti e file di testo.

## File di oggetti

i file di oggetti (estensione ad esempio .dat) sono dei file che contengono appunto un insieme di oggetti.
In base all' operazione che si desidera eseguire il file va aperto in:
- **Output** per scrivere sul file e quindi viene aperto in scrittura.
- **Input** per leggere da file e quindi viene aperto in lettura.

> Nota bene: il frammento di codice per aprire un file va sempre inserito all'interno di un try catch.

### Apertura di un file in scrittura (Output)

```
  try {
    FileOutputStream NomeVariabile1 = new FileOutputStream("NomeFile.estensione");
    ObjectOutputStream NomeVariabile2 = new ObjectOutputStream(NomeVariabile1);
   } catch (Exception e) {
    System.out.println("Eccezione: "+e.getMessage());
   }
```

### Apertura di un file in lettura (Input)

```
  try {
    FileInputStream NomeVariabile1 = new FileInputStream("NomeFile.estensione");
    ObjectInputStream NomeVariabile2 = new ObjectInputStream(NomeVariabile1);
  } catch (Exception e) {
    System.out.println("Eccezione: "+e.getMessage());
  }
```

### Scrivere sul file

` NomeVariabile2.writeObject( Object ) `

### Leggere da file

` Object temp = NomeVariabile2.readObject() `

``` 
  while( true ){
    try{
      Object temp = F.readObject();
      f.flush();
    } catch(EOFException e){
      break;
    }
  }  

```


## File di testo

I file di testo (estensione ad esempio .txt) sono dei file che contengono del testo. 
In base all'operazione che si desidera eseguire un file va aperto in:
- **Read** per leggere dal file
- **Write** per scrivere sul file

> Nota bene: il frammento di codice per aprire un file va sempre inserito all'interno di un try catch.

### Apertura di un file in scrittura (Write)

```
  try {
    FileWriter NomeVariabile1 = new FileWriter("NomeFile.estensione");
    PrintWriter NomeVariabile2 = new PrintWriter(NomeVariabile1);
   } catch (Exception e) {
    System.out.println("Eccezione: "+e.getMessage());
   }
```

### Apertura di un file in lettura (Read)

```
  try {
    FileReader NomeVariabile1 = new FileReader("NomeFile.estensione");
    BufferedReader NomeVariabile2 = new BufferedReader(NomeVariabile1);
  } catch (Exception e) {
    System.out.println("Eccezione: "+e.getMessage());
  }
```


### Scrivere sul file

` NomeVariabile2.println("Stringa") `

### Leggere da file

` String temp = NomeVariabile2.nextLine() `

esempio:

```
  

```

> In Java un file non può essere aperto in append, tuttavia si può sviare a questo inconveniente con diversi metodi.

### Chiusura di un file
ogni tipo di file deve **sempre** essere chiuso, sia che sia stato aperto in lettura, sia in scrittura, sia che sia di oggetti, sia che sia di testo.

` NomeVariabile1.close(); `
