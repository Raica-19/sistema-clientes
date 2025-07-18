import tkinter as tk
from tkinter import messagebox

class TelaLogin:
    def __init__(self, master):
        self.master = master
        master.title("Login")
        master.geometry("300x180")
        master.resizable(False, False)

        # Rótulo e entrada do usuário
        self.label_usuario = tk.Label(master, text="Usuário:")
        self.label_usuario.pack(pady=5)
        self.entry_usuario = tk.Entry(master)
        self.entry_usuario.pack(pady=5)

        # Rótulo e entrada da senha
        self.label_senha = tk.Label(master, text="Senha:")
        self.label_senha.pack(pady=5)
        self.entry_senha = tk.Entry(master, show="*")
        self.entry_senha.pack(pady=5)

        # Botão acessar
        self.botao_acessar = tk.Button(master, text="Acessar", command=self.verificar_login)
        self.botao_acessar.pack(pady=10)

    def verificar_login(self):
        usuario = self.entry_usuario.get()
        senha = self.entry_senha.get()

        # Simples verificação (pode ser trocada por uma base de dados)
        if usuario == "admin" and senha == "123":
            messagebox.showinfo("Login", "Acesso permitido!")
        else:
            messagebox.showerror("Login", "Usuário ou senha incorretos.")

# Execução da interface
if __name__ == "__main__":
    root = tk.Tk()
    app = TelaLogin(root)
    root.mainloop()# sistema-clientes
