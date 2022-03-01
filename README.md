# 08131604

#Week02

##Step01:
1.下載範例:https://jsyeh.org/3dcg10

2.載入:data.zip,windows.zip,glut32.dll

3.點Shape.exe

4.左半邊:加大頂點

    右半邊:point,polygon,triangles[t]




##Step02:
1.安裝 freeglut，改檔名 lib\libglut32.a
2.在CodeBlocks File-Open week01_GLUT專案執行

##Step03:
1.把week02_color main.cpp內部程式刪除
2.導入外掛#include<GL/glut.h>
3.建立主程式main()
4.寫入
```C++
    int main(int argc,char** argv{
      glutInit(&argc,argv); //參數傳回 初始化
      glutInitDisplayMode(GLUT_DOUBLE|GLUT_DEPTH);  //雙緩衝區 | 3D深度功能   
      glutCreateWindow("week02_color");  //開啟視窗    
      glutDisplayFunc(Display);    //顯示Display()函式
      glutMainLoop(); //主要程式迴圈
      }
 ```
 
5.建立Display()函式
```C++
    void Display(){
        glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);    //清除畫面
        glcolor3f(1,1,0);  //顏色修改
        glutSolidTeapot(0.3);    //實心
    
        glutSwapBuffers();
}
```



##Step04:
1.延續Step04程式，在Display()加入程式如下:
```C++
void Display(){
    glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
    glColor3f(1,1,0);
    ///glutSolidTeapot(0.3);

    glBegin(GL_POLYGON);
        glColor3f(1,0,0);    //紅色
        glVertex2f(-1,-1);

        glColor3f(0,1,0);    //綠色
        glVertex2f(+1,-1);

        glColor3f(0,0,1);    //藍色
        glVertex2f(0,+1);
    glEnd();

    glutSwapBuffers();
}
```












