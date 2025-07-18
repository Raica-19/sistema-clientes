import tkinter as tk
from tkinter import messagebox

# Classe da tela de Login
class TelaLogin:
    def __init__(self, master):
        self.master = master
        master.title("Login")
        master.geometry("300x200")

        self.label_usuario = tk.Label(master, text="Usuário:")
        self.label_usuario.pack(pady=5)
        self.entry_usuario = tk.Entry(master)
        self.entry_usuario.pack(pady=5)

        self.label_senha = tk.Label(master, text="Senha:")
        self.label_senha.pack(pady=5)
        self.entry_senha = tk.Entry(master, show="*")
        self.entry_senha.pack(pady=5)

        self.botao_acessar = tk.Button(master, text="Acessar", command=self.fazer_login)
        self.botao_acessar.pack(pady=10)

    def fazer_login(self):
        usuario = self.entry_usuario.get()
        senha = self.entry_senha.get()

        if usuario == "admin" and senha == "123":
            self.master.destroy()
            abrir_tela_home()
        else:
            messagebox.showerror("Erro", "Usuário ou senha incorretos.")

# Classe da tela Home
class TelaHome:
    def __init__(self, master):
        self.master = master
        master.title("Home")
        master.geometry("300x200")

        self.label_bem_vindo = tk.Label(master, text="Bem-vindo ao sistema!", font=("Arial", 12))
        self.label_bem_vindo.pack(pady=20)

        self.botao_cadastro = tk.Button(master, text="Ir para Cadastro", command=self.ir_para_cadastro)
        self.botao_cadastro.pack(pady=10)

    def ir_para_cadastro(self):
        messagebox.showinfo("Cadastro", "Aqui abriria a tela de cadastro.")
        # Aqui você poderia abrir uma nova janela ou carregar outra classe (Cadastro)

# Funções para abrir janelas
def abrir_tela_login():
    root = tk.Tk()
    app = TelaLogin(root)
    root.mainloop()

def abrir_tela_home():
    home = tk.Tk()
    app = TelaHome(home)
    home.mainloop()

# Início da aplicação
if __name__ == "__main__":
    abrir_tela_login()

