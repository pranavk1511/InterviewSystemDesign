# Dependency Inversion 

This focuses on decoupling software modules.
- High-level modules should not depend on low-level modules. Both should depend on abstractions (e.g., interfaces).
- Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.

```python 
# Abstractions
class DataStore:
    def store_data(self, data):
        raise NotImplementedError

# Low-level modules
class DatabaseStore(DataStore):
    def store_data(self, data):
        print(f"Storing data in the database: {data}")

class FileStore(DataStore):
    def store_data(self, data):
        print(f"Storing data in the file system: {data}")

# High-level module
class DataHandler:
    def __init__(self, storage: DataStore):
        self.storage = storage

    def save_data(self, data):
        self.storage.store_data(data)

# Client code
database_store = DatabaseStore()
file_store = FileStore()

data_handler = DataHandler(database_store)
data_handler.save_data("Some data")  # Storing in the database

data_handler = DataHandler(file_store)
data_handler.save_data("Some data")  # Storing in the file system

```