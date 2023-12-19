# leo-wallet
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


wallet.receive(100);
println!("Saldo después de recibir: {}", wallet.get_balance());

if let Err(err) = wallet.send("direccion_destino", 50) {
    println!("Error al enviar: {}", err);
} else {
    println!("Transacción enviada con éxito");
    println!("Saldo después del envío: {}", wallet.get_balance());
}
