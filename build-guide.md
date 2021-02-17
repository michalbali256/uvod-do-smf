Tento dokument by mal pomoct s buildenim a spustenim projektu.

Prvym krokom je, ze si naklonujeme repo `https://github.com/eclipse/che-che4z-lsp-for-hlasm`.

# Build
Dalej je potrebne ho zbuildit - instrukcie ako na to su tu: https://github.com/eclipse/che-che4z-lsp-for-hlasm/wiki/Build-instructions

Na linuxe je to straight-forward - staci zadat 4 prikazy ktore su uvedene v build instructions do terminalu.

## Windows build
Na windowse vyvijame vo Visual Studio 2019 Community, urcite sa to da zbuildit aj inym toolom, ale nemam to vyskusane. Uvediem kratky navod ako na to:
1. Potrebne stiahnut a nainstalovat JDK, Maven a npm z prerequisities z build instructions. CMake a C++ compilator su obsiahnute vo visual studiu. Vsetky z nich musia byt pristupne v `PATH` a spustitelne z terminalu.
Po instalacii mozeme overit, ze nasledujuce prikazy funguju:
```
mvn --version

javac --version

npm --version
```
2. Vo Visual Studiu otvorime priecinok s projektom che-che4z-lsp-for-hlasm - pouzijeme `Open a local folder`, nepouzijeme `Open a project or solution`
3. Po otvoreni VS samo detekuje ze je to CMake projekt. A mozeme zvolit Build All pre zbuildenie.


Je mozne overit build testami.

## Spustenie
Su tu 2 moznosti.
1. Build vytvori `.vsix` subor v `build/bin` - linux, resp. `build/x64-Release/bin` - windows. VSIX je balicek s Visual Studio Code extension.
[Build instructions](https://github.com/eclipse/che-che4z-lsp-for-hlasm/wiki/Build-instructions) obsahuju navod ako tento balicek nainstalovat do VS Code.
2. Spustit debug vyvojarsku session, ktoru ponuka visual studio code. Predviedol som to aj na prvej prednaske, ale tu je navod:  
    1. Otvorit priecinok clients/vscode-hlasmplugin vo VS Code.
    2. Zvolit tab Debug
    3. V drop down liste hore zvolit `Launch extension` a spustit zelenym "play"
    4. Spusti sa nove okno so spustenou extensionou, ktoru sme prave zbuildili.
