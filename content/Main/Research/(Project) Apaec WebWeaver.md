
## Introducing Project Apaec Web Weaver


- Mythological foundations
	- Ai Apaec
- Not search engine, framework for webcrawler production
- crawler production through AI
	- Explanation
- Web navigation and Large Action models
	- Selenium IDE
- Contribute by making your crawlers, testing them and uploading them to the datapool
	- Discord server for help with development
- Roadmap
- Open Source model integration (no OpenAI)
	- Training custom model
- Integrating model into an open source Large Action model
	- As the technology develops
(Nicht vollständig)

# Installation

#### Schritt 1: Git Installation

Bevor wir beginnen, müssen wir sicherstellen, dass Git auf Ihrem System installiert ist. Git ist ein Versionskontrollsystem, das es uns ermöglicht, Änderungen am Code nachzuverfolgen und mit anderen zusammenzuarbeiten. Folgen Sie diesen Schritten, um Git zu installieren:

1. Gehen Sie zur offiziellen Git-Website: [https://git-scm.com/](https://git-scm.com/)
2. Laden Sie die für Ihr Betriebssystem passende Version herunter.
3. Führen Sie die heruntergeladene Datei aus und folgen Sie den Installationsanweisungen.
4. Nach der Installation öffnen Sie die PowerShell und geben Sie `git --version` ein, um zu überprüfen, ob die Installation erfolgreich war. Sie sollten die installierte Git-Version sehen.

## Installation der IDE

#### Was ist eine IDE?

Eine Integrierte Entwicklungsumgebung (IDE) ist eine Softwareanwendung, die Computerprogrammierern und Entwicklern eine umfassende Einrichtung zur Softwareentwicklung bietet. Eine IDE enthält in der Regel einen Quelltext-Editor, Build-Automatisierungstools und einen Debugger. Sie vereinfacht und beschleunigt den Entwicklungsprozess, indem sie alle notwendigen Tools in einer einzigen Anwendung bündelt.

#### Installation von VSCode

Visual Studio Code (VSCode) ist eine beliebte, kostenlose, plattformübergreifende IDE, die von Microsoft entwickelt wurde. Sie unterstützt eine Vielzahl von Programmiersprachen und verfügt über eine riesige Auswahl an Erweiterungen, um ihre Funktionalität zu erweitern.

1. Gehen Sie zur offiziellen VSCode-Website: https://code.visualstudio.com/
2. Laden Sie die Version für Ihr Betriebssystem herunter.
3. Führen Sie die heruntergeladene Datei aus und folgen Sie den Installationsanweisungen.

#### Alternativen zu VSCode

Während VSCode eine hervorragende Wahl für viele Entwickler ist, gibt es zahlreiche andere IDEs, die je nach Ihren spezifischen Bedürfnissen und Vorlieben besser geeignet sein könnten:

- **IntelliJ IDEA**: Ideal für Java-Entwicklung, bietet aber auch Unterstützung für andere Sprachen. Es gibt eine kostenlose Community-Version und eine kostenpflichtige Ultimate-Version. https://www.jetbrains.com/idea/
    
- **PyCharm**: Von denselben Machern wie IntelliJ IDEA, speziell für Python-Entwicklung entworfen. Ebenfalls erhältlich in einer kostenlosen Community-Version und einer kostenpflichtigen Professional-Version. https://www.jetbrains.com/pycharm/
    
- **Eclipse**: Eine weitere beliebte Wahl, besonders unter Java-Entwicklern, aber auch für C/C++, PHP und JavaScript. Eclipse ist kostenlos. [https://www.eclipse.org/](https://www.eclipse.org/)
    
- **Atom**: Ein kostenloser, open-source Quelltext-Editor, der auch als leichte IDE verwendet werden kann. Entwickelt von GitHub, ist es hochgradig anpassbar. [https://atom.io/](https://atom.io/)
    
- **Sublime Text**: Ein schneller und leistungsstarker Texteditor, der durch den Kauf einer Lizenz in vollem Umfang genutzt werden kann, aber auch in einer unbegrenzten, kostenlosen Testversion zur Verfügung steht. [https://www.sublimetext.com/](https://www.sublimetext.com/)


### IDE einrichten

Im IDE Ihrer Wahl. Erstellen Sie zunächst einen neuen Ordner wo Sie das Projekt installieren möchten und öffnen Sie diesen im IDE. Dann öffnen wir das Terminal.
In VSCode unter Terminal -> New Terminal

Nun klonen wir das Projekt in das lokale Verzeichnis:

```
https://github.com/JaYani55/AIApaec.git
```


#### Schritt 3: Virtuelle Umgebung Einrichten

Nachdem Sie das Verzeichnis erfolgreich geklont haben, navigieren Sie in das Projektverzeichnis und erstellen Sie eine virtuelle Umgebung. Eine virtuelle Umgebung ermöglicht es uns, die Abhängigkeiten des Projekts isoliert von anderen Projekten zu verwalten. Verwenden Sie diese Befehle:

``` powershell
python -m venv env
```
(Terminal muss in 'env' modus sein)

Aktivieren Sie die virtuelle Umgebung mit:

PowershellCopy code

`env\Scripts\Activate.ps1`

Überprüfen Sie die ExecutionPolicy mit:

PowershellCopy code

`Get-ExecutionPolicy`

Falls erforderlich, ändern Sie die ExecutionPolicy, indem Sie PowerShell als Administrator öffnen und folgenden Befehl eingeben:

PowershellCopy code

`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine`

#### Schritt 4: Pakete Installieren

Installieren Sie die notwendigen Pakete für den Webcrawler mit folgendem Befehl:

PowershellCopy code

`pip install selenium bs4 datetime pandas requests subprocess logging importlib configparser`


#### Schritt 5: WebDriver Installieren

Um Selenium zu verwenden, benötigen Sie den Chrome WebDriver. Folgen Sie diesen Schritten, um ihn zu installieren:

1. Besuchen Sie [Chrome for Testing availability](https://googlechromelabs.github.io/chrome-for-testing/) und laden Sie die Chrome (win64) und Chromedriver (win64) Versionen herunter. Achten Sie darauf, die Entwicklerversion 120.0.6099.109 zu wählen.
2. Entpacken Sie beide heruntergeladenen Dateien in Ihrem Projektverzeichnis.


