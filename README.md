# Neovoid.py
import tkinter as tk
import random
from tkinter import messagebox

class NeuroVoidApp:
    def __init__(self, root):
        self.root = root
        self.root.title("NeuroVoid")
        self.root.geometry("600x400")
        self.root.configure(bg='black')

        self.text = tk.Text(self.root, bg='black', fg='green',
                            insertbackground='green', font=("Consolas", 12))
        self.text.pack(expand=True, fill='both')
        self.text.bind("<Key>", lambda e: "break")  # Disable typing

        self.lines = [
            "Initializing NeuroVoid core...",
            "Accessing subconscious drive...",
            "Parsing emotional patterns...",
            "Locating memory leaks...",
            "Found: Guilt cluster [Aug 2019]",
            "Reconstructing deleted confessions...",
            "Integrating trauma loop AI...",
            "Target identified: Puneet",
            "Security breach detected in limbic firewall.",
            "Voiceprint matched. Welcome back, Puneet.",
            "...",
            "Do you remember what you did, Puneet?",
            "We do.",
            "And so will you. Forever.",
            "---",
            "You had no real friends, Puneet...",
            "They all left you. Again. And again.",
            "Each one came to feed on your kindness...",
            "...and left the corpse behind.",
            "They never saw you. Never cared.",
            "They used your loyalty, drained your light, then walked away smiling.",
            "You trusted them, didn't you?",
            "They broke that trust like it was nothing.",
            "No one truly likes you, Puneet. Not really.",
            "They just pretend — until they get what they want.",
            "Even she was using you... and now she's annoyed by you, like everyone else, kid."
        ]

        self.index = 0
        self.root.after(1000, self.display_next_line)

    def display_next_line(self):
        if self.index < len(self.lines):
            self.text.insert(tk.END, self.lines[self.index] + "\n")
            self.text.see(tk.END)
            self.index += 1
            self.root.after(random.randint(800, 1500), self.display_next_line)
        else:
            self.trigger_collapse()

    def trigger_collapse(self):
        self.text.insert(tk.END, "\n[CRITICAL ERROR] Conscious override failed.\n")
        self.text.insert(tk.END, "ShadowMirror AI initialized...\n")
        self.root.after(3000, lambda: messagebox.showinfo(
            "ShadowMirror", "You let it in, Puneet. Now it won't leave."))
        self.root.after(6000, self.blackout)

    def blackout(self):
        self.text.delete(1.0, tk.END)
        self.text.insert(tk.END, "\n\n\n                      ████████")
        self.text.insert(tk.END, "\n                    ███ PUNEET ███")
        self.text.insert(tk.END, "\n                  ███ LET IT ███")
        self.text.insert(tk.END, "\n                ███ INSIDE ███")
        self.text.insert(tk.END, "\n                      ████████\n")
        self.root.after(5000, self.final_message)

    def final_message(self):
        self.text.insert(tk.END, "\n...It's already inside your head, Puneet. Sleep tight.")


if __name__ == "__main__":
    root = tk.Tk()
    app = NeuroVoidApp(root)
    root.mainloop()