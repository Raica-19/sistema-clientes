import tkinter as tk
from tkinter import messagebox

class TelaObrigado:
    def __init__(self, master):
        self.master = master
        master.title("Obrigado pelo Cadastro")
        master.geometry("300x250")
        master.resizable(False, False)

        # Mensagem de agradecimento
        self.label_obrigado = tk.Label(master, text="Obrigado pelo cadastro!", font=("Arial", 14))
        self.label_obrigado.pack(pady=15)

        # Usuário
        tk.Label(master, text="Usuário:").pack(pady=5)
        self.entry_usuario = tk.Entry(master)
        self.entry_usuario.pack(pady=5)

        # Senha
        tk.Label(master, text="Senha:").pack(pady=5)
        self.entry_senha = tk.Entry(master, show="*")
        self.entry_senha.pack(pady=5)

        # Botão Acessar
        self.botao_acessar = tk.Button(master, text="Acessar", command=self.acessar)
        self.botao_acessar.pack(pady=15)

    def acessar(self):
        usuario = self.entry_usuario.get()
        senha = self.entry_senha.get()

        # Exemplo simples de validação
        if usuario == "" or senha == "":
            messagebox.showwarning("Aviso", "Por favor, preencha usuário e senha.")
        else:
            messagebox.showinfo("Login", f"Bem-vindo, {usuario}!")
            # Aqui poderia abrir a próxima tela ou fechar a janela

if __name__ == "__main__":
    root = tk.Tk()
    app = TelaObrigado(root)
    root.mainloop()
