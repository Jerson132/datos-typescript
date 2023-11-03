// Definición de la interfaz User
interface User {
  getUsername(): string;
  getEmail(): string;
}

// Clase que implementa la interfaz User
class RegularUser implements User {
  private username: string;
  private email: string;

  constructor(username: string, email: string) {
    this.username = username;
    this.email = email;
  }

  getUsername(): string {
    return this.username;
  }

  getEmail(): string {
    return this.email;
  }
}

// Clase Admin que implementa User y agrega funcionalidad adicional
class AdminUser implements User {
  private username: string;
  private email: string;

  constructor(username: string, email: string) {
    this.username = username;
    this.email = email;
  }

  getUsername(): string {
    return this.username;
  }

  getEmail(): string {
    return this.email;
  }

  promoteUser(user: User) {
    // Lógica para promover a un usuario a un rol de administrador
  }
}

// Función para imprimir datos de usuario (acepta tanto User como AdminUser)
function printUserData(user: User) {
  console.log(`Username: ${user.getUsername()}`);
  console.log(`Email: ${user.getEmail()}`);
}

const regularUser = new RegularUser("user123", "user@example.com");
const adminUser = new AdminUser("admin123", "admin@example.com");

printUserData(regularUser);
printUserData(adminUser);
