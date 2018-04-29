---
title: Membuat pelangi 7 warna OpenGL
date: 2018-04-29 22:06:39
tags: grafika
---

Setelah sebulumnya kita membuat bentuk persegi dengan opengl, pada post ini kita akan mencoba menambahkan 7 warna pelangi pada bangun persegi yang sudah kita buat sebelumnya.
Untuk tahap membuat project baru serta menghubungkan library opengl ke dalam project bisa diliat pada post sebelumnya [disini](https://iwanbazz.github.io/2018/04/28/Membuat-objek-titik-OpenGL-dengan-menggunakan-Xcode/).

Coding untuk menambahkan 7 warna pelangi pada bentuk persegi yang sudah kita buat sebelumnya adalah dengan merubah coding-nya seperti berikut:
``` bash
#include <GLUT/glut.h>
void display() {
    
    glClear(GL_COLOR_BUFFER_BIT);
    glBegin(GL_QUADS);
            glColor3f(1.0,0.0,1.0);
            glVertex2f(-0.75, 0.75);
            glColor3f(0.0,1.0,0.0);
            glVertex2f(-0.75, -0.75);
            glColor3f(0.0,0.0,1.0);
            glVertex2f(0.75, -0.75);
            glColor3f(1.0,0.0,0.0);
            glVertex2f(0.75, 0.75);
    glEnd();
    glFlush();
}

int main(int argc, char** argv) {
    

    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_RGB);
    glutInitWindowSize(500, 500);
    glutCreateWindow("Pelangi");
    glutDisplayFunc(display);
    glutMainLoop();
}
```

Setelah kita jalankan, maka akan tampil hasil pada console app seperti berikut:
![Hasil](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/pelangi.png?raw=true)

Demikian coding dan hasil pada console app untuk menambahkan 7 warna pelangi pada bentuk persegi yang sudah kita buat sebelumnya pada xcode di macos, semoga bermanfaat.