
```qt
#include "MainWindow.h"
 
#include <QApplication>
#include <QLocale>
#include <QTranslator>
 
int main(int argc, char *argv[])
{
    QApplication a(argc, argv);
 
    QTranslator translator;
    QLocale loc = QLocale::system();
    if (loc.language() == QLocale::Chinese) {
        translator.load("./vclhg_zh_CN.qm");
        a.installTranslator(&translator);
    }
 
    MainWindow w;
    w.show();
    return a.exec();
}
```