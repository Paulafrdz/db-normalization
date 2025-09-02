## Instrucciones:

- Descarga el pdf donde encontrarás una tabla de datos sin normalizar
- Normaliza la tabla (se recomienda el uso de Google Sheets)
- Realiza un diagrama ER de Chen
- Realiza un diagrama de tipo patas de gallo
- Crea un repositorio con el Readme
- Inserta en el Readme la descripción del ejercicio así como los diagramas creados (puedes utilizar Mermaid)

## Requisito:

- Normalizar la tabla proporcionada (ver pdf)
- Con diagrams.net realizar un diagrama de entidad-relación (de Chen)
- Con diagrams.net realizar un diagrama uml (Database Schema - Patas de gallo) de la base de datos con sus tablas, campos y relaciones

----
# Tabla normalizada
<img width="2352" height="576" alt="image" src="https://github.com/user-attachments/assets/53872ff6-a598-43ad-a72e-1fd099ca2406" />



# Diagrama ER de Chen
```mermaid

---
config:
  layout: elk
  theme: forest
---
flowchart TD
    A(["id_student"]) --- D["STUDENT"]
    B(["name_student"]) --- D
    C(["classroom"]) --- D
    E{"has"} <-- M --> D
    F["CLASSROOM"] <-- 1 --> E
    I["COURSE"] <-- M --> J{"has"}
    J <-- 1 --> F
    G(["classroom"]) --- F
    H(["classroom_description"]) --- F
    K(["id_course"]) --- I
    L(["classroom"]) --- I
    M(["language"]) --- I

```

# Diagrama tipo patas de gallo 
```mermaid
---
config:
  layout: dagre
  theme: forest
---
erDiagram
	direction TB
	STUDENT {
		int id_student PK ""  
		string name_student  ""  
		string classroom FK ""  
	}
	CLASSROOM {
		string classroom PK ""  
		string classroom_description  ""  
	}
	COURSE {
		int id_course PK ""  
		string classroom FK ""  
		string language  ""  
	}
	STUDENT}|--||CLASSROOM:"has"
	CLASSROOM||--|{COURSE:"has"

```
