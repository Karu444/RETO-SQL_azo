###  Bloque 1

##### Consultas

1. Listar los nombres de los usuarios

   ```sql :3
   SELECT nombre  FROM tblUsuarios;
   ```

2. Calcular el saldo máximo de los usuarios de sexo “Mujer”

     ```sql
     SELECT * FROM tblUsuarios WHERE sexo = 'M' AND saldo = (SELECT MAX(saldo) FROM tblUsuarios);
     ```

3. Listar nombre y teléfono de los usuarios con teléfono NOKIA, BLACKBERRY o SONY

     ```sql
      SELECT nombre, telefono FROM tblUsuarios WHERE (marca = "NOKIA") OR (marca="BLACKBERRY")or (marca="SONY");
     
     ```

4. Contar los usuarios sin saldo o inactivos

     ```sql
     SELECT COUNT(idx) AS sin_saldo_inactivos FROM tblUsuarios WHERE (saldo=0) or (activo=0);
     ```
     
5. Listar el login de los usuarios con nivel 1, 2 o 3

     ```sql
      SELECT usuario, email  FROM tblUsuarios WHERE (nivel="1") or (nivel="2") or (nivel="3");
     ```

6. Listar los números de teléfono con saldo menor o igual a 300

     ```sql
     SELECT telefono  FROM tblUsuarios WHERE (saldo<=300);
     ```

7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL

     ```sql
      SELECT SUM(saldo) FROM tblUsuarios WHERE (compañia="NEXTEL");
     ```

8. Contar el número de usuarios por compañía telefónica

     ```sql
     SELECT compañia, COUNT(idx) AS cantidad FROM tblUsuarios GROUP BY compañia;
     ```

9. Contar el número de usuarios por nivel

     ```sql
     SELECT nivel, COUNT(idx) AS cantidad FROM tblUsuarios GROUP BY nivel;
     ```

10. Listar el login de los usuarios con nivel 2

      ```sql
      SELECT usuario, email FROM tblUsuarios WHERE (nivel=2);
      ```

11. Mostrar el email de los usuarios que usan gmail

      ```sql
      SELECT usuario, email FROM tblUsuarios WHERE email LIKE ("%gmail%");
      ```

12. Listar nombre y teléfono de los usuarios con teléfono LG, SAMSUNG o MOTOROLA

      ```sql
      SELECT nombre, telefono FROM tblUsuarios WHERE (marca = "LG") OR (marca="SAMSUNG")or (marca="MOTOROLA");
      ```

------

### Bloque 2

##### Consultas

1. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG o SAMSUNG

     ```sql
     SELECT nombre, telefono FROM tblUsuarios WHERE marca NOT IN ("LG","SAMSUNG");
     ```

2. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL

     ```sql
     SELECT nombre, telefono, usuario, email FROM tblUsuarios WHERE (compañia="IUSACELL");
     ```

3. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL

     ```sql
     SELECT nombre, telefono, usuario, email FROM tblUsuarios WHERE compañia NOT IN ("TELCEL");
     ```

4. Calcular el saldo promedio de los usuarios que tienen teléfonmarca NOKIA

     ```sql
     SELECT AVG(saldo) AS promedio_saldo_NOKIA FROM tblUsuarios WHERE (marca= "NOKIA");
     ```

5. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL

     ```sql
     SELECT telefono, usuario, email FROM tblUsuarios WHERE (compañia="IUSACELL") or (compañia="AXEL");
     ```

6. Mostrar el email de los usuarios que no usan yahoo

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE email NOT LIKE ("%yahoo%");
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL

     ```sql
     SELECT nombre, telefono, usuario, email FROM tblUsuarios WHERE compañia NOT IN ("TELCEL", "IUSASEL");
     ```

8. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON

     ```sql
     SELECT nombre, telefono, usuario, email FROM tblUsuarios WHERE (compañia="UNEFON");
     ```

9. Listar las diferentes marcas de celular en orden alfabético descendentemente

     ```sql
     SELECT marca FROM tblUsuarios ORDER BY marca DESC; 
     ```

10. Listar las diferentes compañias en orden alfabético aleatorio

      ```sql
      SELECT marca FROM tblUsuarios GROUP BY marca;
      ```

11. Listar el login de los usuarios con nivel 0 o 2

      ```sql
      	SELECT usuario, email FROM tblUsuarios WHERE (nivel=0) or (nivel=2)
      ```

12. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG

      ```sql
      SELECT AVG(saldo) AS promedio_saldo_LG FROM tblUsuarios WHERE (marca= "LG");
      ```

------

### Bloque 3

##### Consultas

1. Listar el login de los usuarios con nivel 1 o 3

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE (nivel=1) or (nivel=3);
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACKBERRY

     ```sql
     SELECT nombre, telefono FROM tblUsuarios WHERE compañia NOT IN ("BLACKBERRY");
     ```

3. Listar el login de los usuarios con nivel 3

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE (nivel=3);
     ```

4. Listar el login de los usuarios con nivel 0

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE (nivel=0);
     ```

5. Listar el login de los usuarios con nivel 1

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE (nivel=1);
     ```

6. Contar el número de usuarios por sexo

     ```sql
     SELECT sexo, COUNT(idx) AS cantidad FROM tblUsuarios GROUP BY sexo;
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica AT&T

     ```sql
     SELECT usuario, email, telefono FROM tblUsuarios WHERE (compañia="AT&T");
     ```

8. Listar las diferentes compañias en orden alfabético descendentemente

     ```sql
     SELECT compañia FROM tblUsuarios ORDER BY compañia DESC;
     ```

9. Listar el logn de los usuarios inactivos

     ```sql
     SELECT usuario, email FROM tblUsuarios WHERE (activo=0);
     ```

10. Listar los números de teléfono sin saldo

      ```sql
      SELECT telefono FROM tblUsuarios WHERE (saldo=0);
      ```

11. Calcular el saldo mínimo de los usuarios de sexo “Hombre”

      ```sql
      SELECT saldo, usuario FROM tblUsuarios WHERE sexo = 'H' AND saldo = (SELECT MIN(saldo) FROM tblUsuarios);
      ```

12. Listar los números de teléfono con saldo mayor a 300

      ```sql
      SELECT telefono FROM tblUsuarios WHERE (saldo=>300);
      ```

------

### Bloque 4

##### Consultas

1. Contar el número de usuarios por marca de teléfono

     ```sql
     SELECT telefono, COUNT(idx) AS cantidad FROM tblUsuarios GROUP BY telefono;
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG

     ```sql
     SELECT nombre, telefono FROM tblUsuarios WHERE compañia NOT IN ("LG");
     ```

3. Listar las diferentes compañias en orden alfabético ascendentemente

     ```sql
     SELECT compañia FROM tblUsuarios ORDER BY compañia ASC;
     ```

4. Calcular la suma de los saldos de los usuarios de la compañia telefónica UNEFON

     ```sql
      SELECT SUM(saldo) FROM tblUsuarios WHERE (compañia="UNEFON");
     ```

5. Mostrar el email de los usuarios que usan hotmail

     ```sql
     SELECT email FROM tblUsuarios WHERE email LIKE ("%hotmail%");
     ```

6. Listar los nombres de los usuarios sin saldo o inactivos

     ```sql
     SELECT saldo, nombre  FROM tblUsuarios WHERE (saldo="0") or (activo="0");
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónicaIUSACELL o TELCEL

     ```sql
     SELECT usuario, email, telefono FROM tblUsuarios WHERE (compañia="IUSACELL") or (compañia="TELCEL");
     ```

8. Listar las diferentes marcas de celular en orden alfabético ascendentemente

     ```sql
     SELECT marca FROM tblUsuarios ORDER BY marca ASC;
     ```

9. Listar las diferentes marcas de celular en orden alfabético aleatorio

     ```sql
     SELECT marca FROM tblUsuarios GROUP BY marca;
     ```

10. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o UNEFON

      ```sql
      SELECT usuario, email, telefono FROM tblUsuarios WHERE (compañia="IUSACELL") or (compañia="UNEFON");
      ```

11. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca MOTOROLA o NOKIA

      ```sql
      SELECT usuario, email, telefono FROM tblUsuarios WHERE compañia NOT IN ("MOTOROLA", "NOKIA");
      ```

12. Calcular la suma de los saldos de los usuarios de la compañia telefónica TELCEL

      ```sql
       SELECT SUM(saldo) FROM tblUsuarios WHERE (compañia="TELCEL");
      ```
