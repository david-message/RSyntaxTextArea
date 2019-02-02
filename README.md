# RSyntaxTextArea
[![Build Status](https://travis-ci.org/bobbylight/RSyntaxTextArea.svg?branch=master)](https://travis-ci.org/bobbylight/RSyntaxTextArea)
[![Coverage Status](https://coveralls.io/repos/bobbylight/RSyntaxTextArea/badge.svg)](https://coveralls.io/r/bobbylight/RSyntaxTextArea)

RSyntaxTextArea is a customizable, syntax highlighting text component for Java Swing applications.  Out of
the box, it supports syntax highlighting for 40+ programming languages, code folding, search and replace,
and has add-on libraries for code completion and spell checking.  Syntax highlighting for additional languages
[can be added](https://github.com/bobbylight/RSyntaxTextArea/wiki) via tools such as [JFlex](http://jflex.de).

RSyntaxTextArea is available under a [BSD 3-Clause license](https://github.com/bobbylight/RSyntaxTextArea/blob/master/RSyntaxTextArea/src/main/resources/META-INF/LICENSE).
For more information, visit [http://bobbylight.github.io/RSyntaxTextArea/](http://bobbylight.github.io/RSyntaxTextArea/).

Available in the [Maven Central repository](http://search.maven.org/#search%7Cga%7C1%7Crsyntaxtextarea%20jar) (`com.fifesoft:rsyntaxtextarea:XXX`).
SNAPSHOT builds of the in-development, unreleased version are hosted on [Sonatype](https://oss.sonatype.org/content/repositories/snapshots/com/fifesoft/rsyntaxtextarea/).

# Building

RSyntaxTextArea uses [Gradle](http://gradle.org/) to build.  To compile, run
all unit tests, and create the jar, run:

    ./gradlew build --warning-mode all

RSTA 3.0 and newer requires Java 8 to compile and run.  If you need
Java 6 compatibility, you'll need to use a 2.6.x version.

# Example Usage

RSyntaxTextArea is simply a subclass of JTextComponent, so it can be dropped into any Swing application with ease.

```java
import javax.swing.*;
import java.awt.BorderLayout;
import org.fife.ui.rtextarea.*;
import org.fife.ui.rsyntaxtextarea.*;

public class TextEditorDemo extends JFrame {

   public TextEditorDemo() {

      JPanel cp = new JPanel(new BorderLayout());

      RSyntaxTextArea textArea = new RSyntaxTextArea(20, 60);
      textArea.setSyntaxEditingStyle(SyntaxConstants.SYNTAX_STYLE_JAVA);
      textArea.setCodeFoldingEnabled(true);
      RTextScrollPane sp = new RTextScrollPane(textArea);
      cp.add(sp);

      setContentPane(cp);
      setTitle("Text Editor Demo");
      setDefaultCloseOperation(EXIT_ON_CLOSE);
      pack();
      setLocationRelativeTo(null);

   }

   public static void main(String[] args) {
      // Start all Swing applications on the EDT.
      SwingUtilities.invokeLater(() -> {
        new TextEditorDemo().setVisible(true);
      });
   }

}
```
# Sister Projects

RSyntaxTextArea provides syntax highlighting, code folding, and many other features out-of-the-box, but when building a code editor you often want to go further.  Below is a list of small add-on libraries that add more complex functionality:

* [AutoComplete](https://github.com/bobbylight/AutoComplete) - Adds code completion to RSyntaxTextArea (or any other JTextComponent).
* [RSTALanguageSupport](https://github.com/bobbylight/RSTALanguageSupport) - Code completion for RSTA for the following languages: Java, JavaScript, HTML, PHP, JSP, Perl, C, Unix Shell.  Built on both RSTA and AutoComplete.
* [SpellChecker](https://github.com/bobbylight/SpellChecker) - Adds squiggle-underline spell checking to RSyntaxTextArea.
* [RSTAUI](https://github.com/bobbylight/RSTAUI) - Common dialogs needed by text editing applications: Find, Replace, Go to Line, File Properties.

# Getting Help

* Add an issue on GitHub
* Peruse [the wiki](https://github.com/bobbylight/RSyntaxTextArea/wiki)
* Check the project's [home page](http://bobbylight.github.io/RSyntaxTextArea/)

