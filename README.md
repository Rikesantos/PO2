# PO2

AULA03 AMAZON 

#NEGOCIO
Tipo java

package negocio;

public class Tipo {
	// Propriedades da classe
	private String descricao = "";

	// Métodos contrutores da classe
	public Tipo() {
		
	}

	public Tipo(String descricao) {
		this.descricao = descricao;
	}

	// Métodos de acesso da classe
	public String getDescricao() {
		return descricao;
	}

	public void setDescricao(String descricao) {
		this.descricao = descricao;
	} 
	// FIM
	
}

Produto Java
package negocio;

public class Produto {
	// Propriedades da classe
	private String nome = ""; 
	private Tipo objTipo = null;
	private double preco = 0;
	
	
	
	// Métodos de acessos da classe  
	public Produto() { // VAZIO
	
	}

	public Produto(String nome, Tipo objTipo, double preco) { // CHEIO
		this.nome = nome;
		this.objTipo = objTipo;
		this.preco = preco;
	}
	
	
	// Métodos contrutores da classe
	
	
	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}

	public Tipo getObjTipo() {
		return objTipo;
	}

	public void setObjTipo(Tipo objTipo) {
		this.objTipo = objTipo;
	}

	public double getPreco() {
		return preco;
	}

	public void setPreco(double preco) {
		this.preco = preco;
	}
	
	
	
	
}

Compra java
package negocio;

public class Compra {
	// Propredades da classe
	private Produto objProduto = null; 
	private int quantidade = 0;
	private String data = "";
	private String cartao = "";
	
	// Métodos contrutores da classe
	public Compra() {  // VAZIO
		
	}

	public Compra(Produto objProduto, int quantidade, String data, String cartao) {  // CHEIO
		this.objProduto = objProduto;
		this.quantidade = quantidade;
		this.data = data;
		this.cartao = cartao;
	}
	
	// Métodos de acessos da classe
	
	public Produto getObjProduto() {
		return objProduto;
	}

	public void setObjProduto(Produto objProduto) {
		this.objProduto = objProduto;
	}

	public int getQuantidade() {
		return quantidade;
	}

	public void setQuantidade(int quantidade) {
		this.quantidade = quantidade;
	}

	public String getData() {
		return data;
	}

	public void setData(String data) {
		this.data = data;
	}

	public String getCartao() {
		return cartao;
	}

	public void setCartao(String cartao) {
		this.cartao = cartao;
	}
	
	
	
	
	

}

#APRESENTAÇÃO
VisaoAmazon
package apresentacao;

import java.io.BufferedReader;
import java.io.InputStreamReader;

import negocio.Compra;
import negocio.Produto;
import negocio.Tipo;

public class VisaoAmazon {
	public static void main(String[] args) {
		// Declaração da variável
		BufferedReader leitor = new BufferedReader(
								new InputStreamReader(System.in));
		Produto objProduto = new Produto(); 
		Compra objCompra = new Compra();
		
  // Entrada de dados
	try {
		System.out.print("Digite o nome do produto: " );
		objProduto.setNome(leitor.readLine());
  
		System.out.print("Digite o tipo do produto: ");
		objProduto.setObjTipo(new Tipo(leitor.readLine()));
  
		System.out.print("Digite o preço do produto: ");
		objProduto.setPreco(Double.parseDouble(leitor.readLine()));
		
		objCompra.setObjProduto(objProduto);
		
		System.out.print("Digite a quantidade da compra: ");
		objCompra.setQuantidade(Integer.parseInt(leitor.readLine()));
		
		System.out.print("Digite a data da compra: ");
		objCompra.setData(leitor.readLine());
		
		System.out.print("Digite o número do cartão: ");
		objCompra.setCartao(leitor.readLine());
		
	}catch (Exception erro) {
		System.out.println(erro);
	}
		
	// Saída de dados
	System.out.println("Produto: " +
					objCompra.getObjProduto().getNome());
	System.out.println("Valor total da compra: R$ " +
					(objCompra.getObjProduto().getPreco() * 
					 objCompra.getQuantidade()));
	System.out.println("Data: " + objCompra.getData());
	}
}


