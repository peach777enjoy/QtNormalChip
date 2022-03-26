首先退出应用程序（exe）的方法
方法1：
```c++
QApplication* app;
app->exit(0);
```
方法2：
```c++
QApplication* app;
app->quit();
```
可以将以上方法加入到关闭程序的槽函数中
为了增加应用程序的人性化，在退出之前，应该做一些提示处理
```c++
 if (!(QMessageBox::information(this,tr("exit tip"),tr("Do you really want exit ?"),tr("Yes"),tr("No"))))
      {
            QApplication* app;
            app->exit(0);
      }
```
关闭窗口的方法：
```c++
#include <QCloseEvent>
void mainWindow::closeEvent( QCloseEvent * event )
{
switch( QMessageBox::information( this, tr("exit tip"), tr("Do you really want exit?"), tr("Yes"), tr("No"), 0, 1 ) ) 
   {
     case 0:
          event->accept();
          break;
     case 1:
     default: 
         event->ignore();
         break; 
   }   
}
```
closeEvent（）定义为一般函数即可（不用定义为槽函数）然后实现它的功能即可
