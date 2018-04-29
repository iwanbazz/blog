---
title: Membuat bangun dasar grafik OpenGL
date: 2018-04-29 22:25:38
tags:
---

Pada post ini kita akan membuat bangun dasar grafik opengl, untuk tahap membuat project baru serta menghubungkan library opengl ke dalam project bisa diliat pada post sebelumnya [disini](https://iwanbazz.github.io/2018/04/28/Membuat-objek-titik-OpenGL-dengan-menggunakan-Xcode/).

Coding untuk membuat bangun dasar grafik opengl dengan bentuk segitiga didalamnya pada xcode seperti berikut:
```bash
#include <GLUT/glut.h>

void init (void) {
    glClearColor (1.0, 1.0, 1.0, 0.0);
    glLineWidth (1.0);
    glColor3f (1.0,0.0,0.0);
    glOrtho (-6,6, -6,6, -6,6);
}
void Display (void) {
    glClear (GL_COLOR_BUFFER_BIT);
    glBegin (GL_LINES);
        glVertex2f (-5.5, 0.0);
        glColor3f (1.0, 0.0, 0.0);
        glVertex2f (5.5, 0.0);
    glEnd ();
    glBegin (GL_LINES);
        glVertex2f (0.0, -5.5);
        glColor3f (1.0, 0.0, 0.0);
        glVertex2f (0.0, 5.5); glEnd ();
    glEnd ();
    glBegin (GL_LINE_LOOP);
        glColor3f (-1.0, 0.0, 0.0);
        glVertex2f (1.0, 1.0);
        glColor3f (-1.0, 0.0, 0.0);
        glVertex2f (4.0, 1.0);
        glColor3f (0.0, 1.0, 0.0);
        glVertex2f (1.0, 5.0);
    glEnd ();
    glutSwapBuffers ();
}
int main (int argc, char** argv) {
    glutInit (&argc, argv);
    glutInitDisplayMode (GLUT_DOUBLE | GLUT_RGB);
    glutInitWindowPosition (0, 0);
    glutInitWindowSize (1500, 1500);
    glutCreateWindow ("Latihan 2");
    init ();
    glutDisplayFunc (Display);
    glutMainLoop ();
}
```

Setelah kita jalankan, maka akan tampil hasil pada console app seperti berikut:
![Hasil](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/segitiga.png?raw=true)

Demikian coding dan hasil pada console app untuk membuat bangun dasar grafik opengl dengan bentuk segitiga didalamnya pada xcode di macos, semoga bermanfaat.
