# SQLite-inmemory-Database
import sqlite3
try:
    conn = sqlite3.connect(':memory:')
    cursor = conn.cursor()
    print("\nMemory database created and connected to SQLite.")

    cursor.execute("SELECT sqlite_version();")
    version = cursor.fetchone()

    print("\nSQLite Database Version is:", version[0])

except sqlite3.Error as error:
    print("\nError while connecting to SQLite:", error)

finally:
    if conn:
        conn.close()
        print("\nThe SQLite connection is closed.")
        
OUTPUT:
Memory database created and connected to SQLite.
SQLite Database Version is: 3.50.4
The SQLite connection is closed.

