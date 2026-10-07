# MechooRi Compiler

MechooRi is a multilingual compiler that allows programs to be written using different human languages as keywords. It uses **SableCC** for lexical and syntactic analysis and **Java** to execute the compiler.

Currently supported languages:

* English
* Arabic
* Italian
* Tagalog

## Project Structure

```text
mechoori-compiler/
├── programs/       # Example MechooRi programs
├── output/         # Compiler output
├── sablecc/        # SableCC grammar and tools
└── src/            # Java compiler source code
```

## Requirements

Before building the compiler, make sure you have:

* Java JDK
* `javac`
* SableCC
* BlueJ (currently used to compile the generated Java source files)

Check your Java and Java compiler versions:

```cmd
java -version
javac -version
```

If the compiler does not work, check that your installed JDK version is compatible with the project.

## Build the Compiler

### 1. Generate the compiler using SableCC

Open the `sablecc` folder.

In the File Explorer address bar, type:

```text
cmd
```

and press **Enter**.

Run:

```cmd
sablecc mechoori.grammar
```

This generates the `mechoori` source folder based on the grammar.

### 2. Copy the generated source

After SableCC finishes:

1. Open the `sablecc` folder.
2. Locate the generated `mechoori` folder.
3. Copy the `mechoori` folder.
4. Paste it into the `src` folder.

### 3. Compile the Java source

Open the `src` folder in **BlueJ**.

Compile the Java source files.

## Run a MechooRi Program

After compiling the source code:

1. Open the `src` folder.
2. In the File Explorer address bar, type:

```text
cmd
```

3. Press **Enter**.
4. Run the compiler with a MechooRi program:

```cmd
java MechooRi < ..\programs\YourLanguage.mechoori > ..\output\OutputXxx.txt
```

For example:

```cmd
java MechooRi < ..\programs\English.mechoori > ..\output\OutputEnglish.txt
```

The generated output will be saved inside the `output` folder.

## Changing the Program Language

To create a program using another supported language:

1. Open the `programs` folder.
2. Open `English.mechoori` and the language file you want to modify.
3. Use the English program as a reference.
4. Copy the program structure into the language file.
5. Replace the English keywords with the corresponding language keywords.
6. Save the file.
7. Run the compiler using that `.mechoori` file.

For example:

```cmd
java MechooRi < ..\programs\Italian.mechoori > ..\output\OutputItalian.txt
```

## Adding a New Language

To add a new language to MechooRi:

1. Open the `sablecc` folder.
2. Open:

```text
mechoori.grammar
```

3. Add the new language and its corresponding keywords to the grammar.
4. Save the grammar.
5. Generate the compiler again:

```cmd
sablecc mechoori.grammar
```

6. Copy the newly generated `mechoori` folder into `src`.
7. Compile the generated Java source files using BlueJ.
8. Create a new `.mechoori` program inside the `programs` folder.
9. Run the compiler using the new language file.

## Example

A language program is stored in the `programs` folder:

```text
programs/
├── English.mechoori
├── Arabic.mechoori
├── Italian.mechoori
└── Tagalog.mechoori
```

The corresponding compiler outputs are stored in:

```text
output/
├── OutputEnglish.txt
├── OutputArabic.txt
├── OutputItalian.txt
└── OutputTagalog.txt
```

## Notes

The current build process uses **BlueJ** to compile the generated Java source files. The project also includes the SableCC files required by the compiler.

This project is currently configured primarily for a **Windows + Java + BlueJ** development environment.
