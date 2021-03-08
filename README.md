# Week03-2021.03.08
1. 參數
```  #include <stdio.h>
  int main(int argc,char**argv)
  {
      printf("現在的 argc 是：%d\n",argc);
     for(int i=0;i<argc;i++)
     {
          printf("argv[%d]是：%s\n",i,argv[i]);
      }
  }
 ``` 
2. 黃色茶壺
```  #include <GL/glut.h>

  void display()
  {
      glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);

      glutSolidTeapot(0.3);

     glutSwapBuffers();
  }

  int main(int argc,char **argv)
  {
     glutInit(&argc,argv);
     glutInitDisplayMode(GLUT_DOUBLE | GLUT_DEPTH);
     glutCreateWindow("08160130");

     glutDisplayFunc(display);

     glutMainLoop();
  }
```
3. 畫統神(失敗)
```  #include <GL/glut.h> ///GLUT外掛

  static void display(void)
  {
      glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);

     glColor3ub(181,212,148); ///unsigned byte 是 0~255
     glBegin(GL_TRIANGLES);

         glColor2f((223-150)/150.0,-(250-150)/150.0);
          glColor2f((320-150)/150.0,-(237-150)/150.0);
          glColor2f((296-150)/150.0,-(313-150)/150.0);
         glEnd();

     glutSwapBuffers();
  }

  int main(int argc, char *argv[])
  {
     glutInit(&argc, argv); ///設定GLUT的初始化

     glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE | GLUT_DEPTH); ///顯示模式
     glutCreateWindow("GLUT Shapes"); ///開GLUT視窗
     glutDisplayFunc(display); ///顯示的函式

     glutMainLoop();  ///GLUT主要的迴圈,卡住不要結束
  }
```
