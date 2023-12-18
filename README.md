# leo-wallet 
// Este es un ejemplo simple para una aplicación de wallet en Rust
struct LeoWallet {
    private_key: String,
    public_address: String,
    balance: u64,
}

impl LeoWallet {
    fn new() -> LeoWallet {
        // Generar claves públicas y privadas (esto es un ejemplo simple, no es seguro)
        let private_key = "mi_clave_privada";
        let public_address = "mi_direccion_publica";
        LeoWallet {
            private_key: private_key.to_string(),
            public_address: public_address.to_string(),
            balance: 0,
        }
    }

    fn send(&mut self, recipient: &str, amount: u64) -> Result<(), &str> {
        // Simular el envío de criptomonedas a la dirección del destinatario
        // En una aplicación real, aquí se realizaría la interacción con la red blockchain
        if self.balance < amount {
            return Err("Fondos insuficientes");
        }
        self.balance -= amount;
        Ok(())
    }

    fn receive(&mut self, amount: u64) {
        // Simular la recepción de criptomonedas
        self.balance += amount;
    }

    fn get_balance(&self) -> u64 {
        self.balance
    }
}

fn main() {
    let mut wallet = LeoWallet::new();
    println!("Dirección pública: {}", wallet.public_address);
    println!("Saldo actual: {}", wallet.get_balance());

    wallet.receive(100);
    println!("Saldo después de recibir: {}", wallet.get_balance());

    if let Err(err) = wallet.send("direccion_destino", 50) {
        println!("Error al enviar: {}", err);
    } else {
        println!("Transacción enviada con éxito");
        println!("Saldo después del envío: {}", wallet.get_balance());
    }
}
APrivateKey1zkp5Jcj4kAeySHZqcYZy8tSQBEJeKyw9XkYDGYZaBMN7Bq7
