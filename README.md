nome = $nome;
    // seta conta
    $this -> conta = $conta;
    // seta valor
    $this -> valor = $valor;

}

// faz depósito através do número da conta
function deposito($conta, $valor) {

    // verifica se a conta existe
    if ($this -> conta == $conta) {
        
        // incrementa o deposito ao saldo
        $this -> valor = $this -> valor + $valor;
        echo "Depósito Efetuado Com Sucesso.";
    
    }
    else
        // conta errada
        echo "Conta Errada";


}

// faz saque tendo como parâmetro o numero da conta
function saque($conta, $valor) {
    
    // verifica se a conta existe
    if ($this -> conta == $conta) {
        // verifica se o saldo é suficiente
        if ($valor > $this -> valor) {  
            
            echo "Saldo Insuficiente.";
        
        }  
        else
        {
            // reduz o valor sacado do saldo
            $this -> valor = $this -> valor - $valor;
            echo "Saque Efetuado Com Sucesso";
        }
    }
    else
        // conta errada
        echo "Conta Errada";
}


// imprime os dados do cliente
function imprime() {
    
    // nome, conta e saldo
    echo "
--------------------------------------------------
";
    echo "Nome: ".$this -> nome."
";
    echo "Conta: ".$this -> conta."
";
    echo "Saldo: ".$this -> valor;
    echo "
--------------------------------------------------
";



}


}

// exemplo 
// cria o objeto

$bancoteste = new banco();
// imprime o cliente que é vazio
$bancoteste -> imprime();
echo "Cria Conta";
// cria uma conta
$bancoteste -> criaConta("Tonho","011-1406",200);
// imprime
$bancoteste -> imprime();
// realiza saque de 300
echo "Faz Saque de 300
";
$bancoteste -> saque("011-1406",300);
// realiza saque de 150
echo "
Faz Saque de 150
";
$bancoteste -> saque("011-1406",150);
// imprime
$bancoteste -> imprime();
// faz deposito em conta errada
echo "
Faz Depósito Com Numero da Conta Errado
";
$bancoteste -> deposito("011-1407",234);
// faz depósito em conta certa
echo "
Faz Depósito Com Numero da Conta Certo
";
$bancoteste -> deposito("011-1406",234);
// imprime
$bancoteste -> imprime();



