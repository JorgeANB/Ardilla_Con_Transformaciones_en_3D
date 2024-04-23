# Ardilla_Con_Transformaciones_en_3D
Aún tiene problemas con el Resize utilizando la tecla ´p´ y ´l´

#include <GL/glut.h>
#include <iostream>
#include <stdlib.h>
#include <math.h>

// Tamaño de la escala de triangulo
float rotate_y = 0;
float rotate_x = 0;
float translate_x = 0.0f;
float translate_y = 0.0f;
float translate_z = 0.0f;
float scale = 400.0f;
// Función para dibujar en la pantalla
void display() {
	// Establecemos el color de fondo y limpiamos la pantalla
	glClearColor(1.0, 1.0, 1.0, 1.0);
	glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
	// Cargamos la matriz de identidad
	glLoadIdentity();
	// Aplicamos las transformaciones
	glTranslatef(translate_x, translate_y, -5.0f + translate_z); // Traslación
	glScalef(scale / 400.0f, scale / 400.0f, scale / 400.0f); // Escalamiento
	glRotatef(rotate_x, 1.0, 0.0, 0.0); // Rotación del eje x
	glRotatef(rotate_y, 0.0, 1.0, 0.0); // Rotación del eje y

	// Particion para el coloreado de los objetos en 3D
	glColor3f(0.2, 0.2, 1.0);
	glBegin(GL_TRIANGLES);
	glVertex3f(50.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(58.00 / scale, 25.00 / scale, 8.00 / scale);

	glVertex3f(65.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 40.00 / scale, 8.00 / scale);

	glVertex3f(65.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, 8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(65.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(28.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, 8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(15.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(23.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(15.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(13.00 / scale, 83.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 100.00 / scale, 8.00 / scale);

	glVertex3f(23.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 118.00 / scale, 8.00 / scale);
	glVertex3f(28.00 / scale, 110.00 / scale, 8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, 8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, 8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(35.00 / scale, 140.00 / scale, 8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);

	glVertex3f(35.00 / scale, 140.00 / scale, 8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, 8.00 / scale);

	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 165.00 / scale, 8.00 / scale);

	//Color de modelo secundario de imagen
	glColor3f(0.2, 0.2, 0.1);
	glBegin(GL_TRIANGLES);
	glVertex3f(50.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(58.00 / scale, 25.00 / scale, -8.00 / scale);

	glVertex3f(65.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);

	glVertex3f(65.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, -8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(65.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, -8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);
	glVertex3f(15.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(23.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(15.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(13.00 / scale, 83.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 100.00 / scale, -8.00 / scale);

	glVertex3f(23.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 118.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 110.00 / scale, -8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, -8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, -8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(35.00 / scale, 140.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);

	glVertex3f(35.00 / scale, 140.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, -8.00 / scale);

	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 165.00 / scale, -8.00 / scale);

	//Color de vision lateral
	glColor3f(1.0, 0.2, 0.3);
	glBegin(GL_QUADS);
	glVertex3f(50.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(58.00 / scale, 23.00 / scale, -8.00 / scale);
	glVertex3f(58.00 / scale, 23.00 / scale, 8.00 / scale);

	glVertex3f(58.00 / scale, 23.00 / scale, -8.00 / scale);
	glVertex3f(58.00 / scale, 23.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);

	glVertex3f(50.00 / scale, 40 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 40.00 / scale, 8.00 / scale);

	glVertex3f(28.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);

	glVertex3f(33.00 / scale, 63.00 / scale, 8.00 / scale);
	glVertex3f(33.00 / scale, 63.00 / scale, -8.00 / scale);
	glVertex3f(15.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(15.00 / scale, 65.00 / scale, 8.00 / scale);

	glVertex3f(15.00 / scale, 65.00 / scale, -8.00 / scale);
	glVertex3f(15.00 / scale, 65.00 / scale, 8.00 / scale);
	glVertex3f(13.00 / scale, 83.00 / scale, 8.00 / scale);
	glVertex3f(13.00 / scale, 83.00 / scale, -8.00 / scale);

	glVertex3f(13.00 / scale, 83.00 / scale, 8.00 / scale);
	glVertex3f(13.00 / scale, 83.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 100.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 100.00 / scale, 8.00 / scale);

	glVertex3f(20.00 / scale, 100.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 100.00 / scale, 8.00 / scale);
	glVertex3f(23.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(23.00 / scale, 105.00 / scale, -8.00 / scale);

	glVertex3f(23.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(23.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 110.00 / scale, 8.00 / scale);

	glVertex3f(20.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(20.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 118.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 118.00 / scale, -8.00 / scale);

	glVertex3f(20.00 / scale, 118.00 / scale, 8.00 / scale);
	glVertex3f(20.00 / scale, 118.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 110.00 / scale, 8.00 / scale);

	glVertex3f(28.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(28.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, -8.00 / scale);

	glVertex3f(30.00 / scale, 110.00 / scale, 8.00 / scale);
	glVertex3f(30.00 / scale, 110.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(48.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(48.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(35.00 / scale, 140.00 / scale, 8.00 / scale);
	glVertex3f(35.00 / scale, 140.00 / scale, -8.00 / scale);

	glVertex3f(35.00 / scale, 140.00 / scale, 8.00 / scale);
	glVertex3f(35.00 / scale, 140.00 / scale, -8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, -8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, 8.00 / scale);

	glVertex3f(45.00 / scale, 180.00 / scale, -8.00 / scale);
	glVertex3f(45.00 / scale, 180.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 165.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 165.00 / scale, -8.00 / scale);

	glVertex3f(65.00 / scale, 165.00 / scale, 8.00 / scale);
	glVertex3f(65.00 / scale, 165.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);

	glVertex3f(55.00 / scale, 145.00 / scale, -8.00 / scale);
	glVertex3f(55.00 / scale, 145.00 / scale, 8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, 8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, -8.00 / scale);

	glVertex3f(70.00 / scale, 120.00 / scale, 8.00 / scale);
	glVertex3f(70.00 / scale, 120.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, 8.00 / scale);

	glVertex3f(83.00 / scale, 105.00 / scale, -8.00 / scale);
	glVertex3f(83.00 / scale, 105.00 / scale, 8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, -8.00 / scale);

	glVertex3f(80.00 / scale, 40.00 / scale, 8.00 / scale);
	glVertex3f(80.00 / scale, 40.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 10.00 / scale, 8.00 / scale);

	glVertex3f(65.00 / scale, 10.00 / scale, -8.00 / scale);
	glVertex3f(65.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 10.00 / scale, 8.00 / scale);
	glVertex3f(50.00 / scale, 10.00 / scale, -8.00 / scale);

	glEnd();
	glutSwapBuffers();
}

// Función para manejar las teclas especiales (flechas) 
void specialKeys(int key, int x, int y) {
	// Detectamos que la tecla especial fue presionada y realizamos la acción correspondiente
	switch (key)
	{
	case GLUT_KEY_RIGHT:
		translate_x += 0.1f; // Incrementar la traslación en el eje X
		break;
	case GLUT_KEY_LEFT:
		translate_x -= 0.1f; // Decrementar la traslación en el eje X
		break;
	case GLUT_KEY_UP:
		translate_y += 0.1f; // Incrementar la traslación en el eje Y
		break;
	case GLUT_KEY_DOWN:
		translate_y -= 0.1f; // Decrementar la traslación en el eje Y
		break;
	}

	// Le decimos a GLUT que redibuje la escena
	glutPostRedisplay();
}
// Función para manejar las teclas normales (no especiales)
void keyboard(unsigned char key, int x, int y) {
	switch (key){
	case 'p':
		scale *= 1.1f; // Incrementar el factor de escala
		break;
	case 'l':
		scale *= 0.9f; // Decrementar el factor de escala
		break;
	case 'w':
		rotate_x += 5.0f; // Incrementar el ángulo de rotación en el eje X
		break;
	case 's':
		rotate_x -= 5.0f; // Decrementar el ángulo de rotación en el eje X
		break;
	case 'a':
		rotate_y += 5.0f; // Incrementar el ángulo de rotación en el eje Y
		break;
	case 'd':
		rotate_y -= 5.0f; // Decrementar el ángulo de rotación en el eje Y
		break;
	}
	glutPostRedisplay(); // Solicitar redibujar la escena
}

// Función para manejar el redimensionamiento de la ventan;a
void resize(int width, int height) {
	// Establecemos el viewport y la proyección
	glViewport(0, 0, width, height); // Establecemos la visualización
	glMatrixMode(GL_PROJECTION); // Seleccionamos la matriz de proyección
	glLoadIdentity(); // Cargamos la matriz de identidad

	// Definimos la proyección perspectiva
	gluPerspective(45.0f, (GLfloat)width / (GLfloat)height, 0.1f, 100.0f);

	// Seleccionamos la matriz de modelo-vista y cargamos la matriz identidad
	glMatrixMode(GL_MODELVIEW);
	glLoadIdentity();
}
// Función principal
int main(int argc, char* argv[]) {
	// Inicializamos GLUT y configuramos la ventana
	glutInit(&argc, argv);
	glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB | GLUT_DEPTH); // Configuramos el modo de visualización
	int screenWidth = glutGet(GLUT_SCREEN_WIDTH);
	int screenHeight = glutGet(GLUT_SCREEN_HEIGHT);
	glutInitWindowSize(screenWidth, screenHeight); // Tamaño de la ventana
	glutCreateWindow("Ardilla 3D"); // Titulo de la ventana
	glEnable(GL_DEPTH_TEST); // Habilitamos el buffer de profundidad
	glutDisplayFunc(display); // Función para dibujar
	glutSpecialFunc(specialKeys); // Función para manejar teclas especiales
	glutKeyboardFunc(keyboard); // Función para manejar teclas normales
	glutReshapeFunc(resize); // Función para manejar redimencionamiento de ventana
	glutMainLoop(); // Bucle principal de GLUT
	return 0; // Salimos del programa
}
