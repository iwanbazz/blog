---
title: Membuat objek titik OpenGL dengan menggunakan Xcode
date: 2018-04-28 00:13:08
tags:
---

Sebagai bagian dari tugas ke-1 pada mata kuliah Grafika Komputer di Semester 6 ini, saya akan memberikan tutorial membuat objek titik OpenGL dengan menggunakan Xcode.
Berikut Langkah-Langkahnya :

1. Pastikan software xcode sudah terinstall pada perangkat Macbook/Hackintosh anda.

2. Buka xcode dan buat project baru dengan memilih menu **File > New > Project**.
![New Project](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/new_project.png?raw=true)

3. Setelah memilih new project maka akan tampil pilihan template yang akan digunakan, pilih **MacOS > Command Line Tools**.
![Command Line Tools](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/command_line_tools.png?raw=true)

4. Setelah project sudah tergenerate, library opengl harus dihubungkan dengan project yang dibuat. pilih tab **Build Phases** kemudian buka item **Link Binary With Libraries** lalu klik ikon **+** untuk menambahkan library opengl yang akan digunakan.
![Link OpenGL](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/link_opengl.png?raw=true)
![Library OpenGL](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/lib_opengl.png?raw=true)

5. Secara default coding pada main.cpp akan men-generate code untuk menampilkan hello world pada console.
![Default Main](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/default_main.png?raw=true)

6. untuk membuat objek titik dengan library opengl maka main.cpp harus diubah dengan memanggil library opengl yang sudah kita hubungkan sebelumnya.

``` bash
#include <GLUT/glut.h>
void userdraw () {
    
    glBegin (GL_POINTS);
    glVertex2i (150,0);
    glVertex2i (150,200);
    glVertex2i (370,200);
    
    glEnd ();
}

void display (void) {
    glClear (GL_COLOR_BUFFER_BIT);
    userdraw ();
    glutSwapBuffers ();
}
int main (int argc, char **argv) {
    glutInit (&argc,argv);
    glutInitDisplayMode (GLUT_DOUBLE|GLUT_RGB);
    glutInitWindowSize (640,480);
    glutCreateWindow ("Membuat Objek Titik");
    glClearColor (0.0, 0.0, 0.0, 0.0);
    gluOrtho2D (0.,640.,-240.,240.);
    glutIdleFunc (display);
    glutDisplayFunc (display);
    glutMainLoop ();
    return 0;
    }
```

7. Setelah kita jalankan, maka akan tampil hasil pada console app seperti berikut:
![Hasil](https://github.com/iwanbazz/iwanbazz.github.io/blob/master/img/result.png?raw=true)

Demikian cara untuk membuat objek titik OpenGL dengan menggunakan XCode di Macbook/Hackintosh, semoga bermanfaat.