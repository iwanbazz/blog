---
title: Membuat persegi OpenGL
date: 2018-04-29 21:20:47
tags: grafika
---

Melanjutkan tugas pada mata kuliah grafika komputer di semester 6 ini, sekarang kita akan membuat bentuk persegi 2 dimensi opengl dengan menggunakan xcode.
untuk tahap membuat project baru serta menghubungkan library opengl ke dalam project bisa diliat pada post sebelumnya [disini](https://iwanbazz.github.io/2018/04/28/Membuat-objek-titik-OpenGL-dengan-menggunakan-Xcode/).

Coding untuk membuat bentuk persegi 2 dimensi opengl seperti berikut:
``` bash
#include <GLUT/glut.h>
void display() {
    
    glClear(GL_COLOR_BUFFER_BIT);
    glBegin(GL_QUADS);
        glVertex2f(-0.75, 0.75);
        glVertex2f(-0.75, -0.75);
        glVertex2f(0.75, -0.75);
        glVertex2f(0.75, 0.75);
    glEnd();
    glFlush();
}

int main(int argc, char** argv) {
    
    
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
    glutInitWindowSize(500, 500);
    glutCreateWindow("Persegi");
    glutDisplayFunc(display);
    glutMainLoop();
}
```

Setelah kita jalankan, maka akan tampil hasil pada console app seperti berikut:
![Hasil](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/persegi.png?raw=true)

Demikian coding dan hasil pada console app untuk membuat bentuk persegi 2 dimensi pada xcode di macos, semoga bermanfaat.