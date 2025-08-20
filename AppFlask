from flask import Flask

app = Flask(__name__)

# Base de datos simple en memoria
tareas = {}

# Crear tarea (POST)
@app.post("/tareas/<int:id>/<titulo>")
def crear_tarea(id, titulo):
    tareas[id] = titulo
    return f"Tarea creada: {id} - {titulo}"

# Leer todas las tareas (GET)
@app.get("/tareas")
def leer_tareas():
    return str(tareas)

# Actualizar tarea (PUT)
@app.put("/tareas/<int:id>/<nuevo_titulo>")
def actualizar_tarea(id, nuevo_titulo):
    if id in tareas:
        tareas[id] = nuevo_titulo
        return f"Tarea {id} actualizada a: {nuevo_titulo}"
    return f"Tarea {id} no encontrada"

# Eliminar tarea (DELETE)
@app.delete("/tareas/<int:id>")
def eliminar_tarea(id):
    if id in tareas:
        tareas.pop(id)
        return f"Tarea {id} eliminada"
    return f"Tarea {id} no encontrada"

if __name__ == "__main__":
    app.run(debug=True)
