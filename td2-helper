import tkinter as tk

class TrainDriver2Helper:
    def __init__(self):
        # Spracheinstellungen
        self.current_language = "Deutsch"
        
        self.root = tk.Tk()
        self.root.title("Train Driver 2 Helper")

        # Zugnummer und Anschluss Eingabefelder
        self.zugnummer_label = tk.Label(self.root, text="Zugnummer:")
        self.zugnummer_label.grid(row=0, column=0, padx=5, pady=5)

        self.zugnummer_entry = tk.Entry(self.root)
        self.zugnummer_entry.grid(row=0, column=1, padx=5, pady=5)

        self.anschluss_label = tk.Label(self.root, text="Anschluss:")
        self.anschluss_label.grid(row=1, column=0, padx=5, pady=5)

        self.anschluss_entry = tk.Entry(self.root)
        self.anschluss_entry.grid(row=1, column=1, padx=5, pady=5)

        # Anfrage Dropdown-Menü
        self.anfrage_label = tk.Label(self.root, text="Anfrage:")
        self.anfrage_label.grid(row=2, column=0, padx=5, pady=5)

        self.anfrage_options = {"Deutsch": ["Anfrage pünktlich", "Anfrage verspätet", "Anfrage linkes Gleis"],
                                "Englisch": ["Request on time", "Request delayed", "Request left track"],
                                "Polnisch": ["Zapytanie o czas", "Zapytanie o opóźnienie", "Zapytanie o lewy tor"]}


        self.anfrage_var = tk.StringVar(self.root)
        self.anfrage_var.set(self.anfrage_options["Deutsch"][0])

        self.anfrage_menu = tk.OptionMenu(self.root, self.anfrage_var, *self.anfrage_options[self.current_language])
        self.anfrage_menu.grid(row=2, column=1, padx=5, pady=5)

        # Sprachauswahl Buttons
        self.language_frame = tk.Frame(self.root)
        self.language_frame.grid(row=3, column=0, columnspan=2, padx=5, pady=5)

        self.german_button = tk.Button(self.language_frame, text="Deutsch", command=lambda: self.set_language("Deutsch"))
        self.german_button.pack(side="left", padx=5)

        self.english_button = tk.Button(self.language_frame, text="Englisch", command=lambda: self.set_language("Englisch"))
        self.english_button.pack(side="left", padx=5)

        self.polish_button = tk.Button(self.language_frame, text="Polski", command=lambda: self.set_language("Polnisch"))
        self.polish_button.pack(side="left", padx=5)

        # Text generieren Button
        self.generate_button = tk.Button(self.root, text="Text generieren", command=self.generate_text)
        self.generate_button.grid(row=4, column=0, columnspan=2, padx=5, pady=5)

        # Status Label
        self.status_label = tk.Label(self.root, text="")
        self.status_label.grid(row=5, column=0, columnspan=2, padx=5, pady=5)



    def set_language(self, language):
        if language == "Englisch":
            self.zugnummer_label.config(text="Train number:")
            self.anschluss_label.config(text="Connection:")
            self.anfrage_label.config(text="Request:")
            self.anfrage_options = {"Englisch": ["Request on time", "Request delayed", "Request left track"]}
            self.anfrage_var.set(self.anfrage_options["Englisch"][0])
            self.generate_button.config(text="Generate Text")
            self.german_button.config(text="German")
            self.english_button.config(text="English")
            self.polish_button.config(text="Polish")

        elif language == "Polnisch":
            self.zugnummer_label.config(text="Numer pociągu:")
            self.anschluss_label.config(text="Połączenie:")
            self.anfrage_label.config(text="Zapytanie:")
            self.anfrage_options = {"Polnisch": ["Zapytanie o czas", "Zapytanie o opóźnienie", "Zapytanie o lewy tor"]}
            self.anfrage_var.set(self.anfrage_options["Polnisch"][0])
            self.generate_button.config(text="Wygeneruj tekst")
            self.german_button.config(text="Niemiecki")
            self.english_button.config(text="Angielski")
            self.polish_button.config(text="Polski")

        elif language == "Deutsch":
            self.zugnummer_label.config(text="Zugnummer:")
            self.anschluss_label.config(text="Anschluss:")
            self.anfrage_label.config(text="Anfrage:")
            self.anfrage_options = {"Deutsch": ["Anfrage pünktlich", "Anfrage verspätet", "Anfrage linkes Gleis"],
                                    "Englisch": ["Request on time", "Request delayed", "Request left track"],
                                    "Polnisch": ["Zapytanie o czas", "Zapytanie o opóźnienie", "Zapytanie o lewy tor"]}
            self.anfrage_var.set(self.anfrage_options["Deutsch"][0])
            self.generate_button.config(text="Text generieren")
            self.german_button.config(text="Deutsch")
            self.english_button.config(text="Englisch")
            self.polish_button.config(text="Polnisch")

        self.current_language = language


    def generate_text(self):
        zugnummer = self.zugnummer_entry.get()
        anschluss = self.anschluss_entry.get()
        anfrage = self.anfrage_var.get()

        if self.current_language == "Deutsch":
            if anfrage == self.anfrage_options["Deutsch"][0]:
                text = f"Ist der Anschluss {anschluss} für den Zug {zugnummer} frei?"
            elif anfrage == self.anfrage_options["Deutsch"][1]:
                text = f"Ist der Anschluss {anschluss} für den verspäteten Zug {zugnummer} frei?"
            elif anfrage == self.anfrage_options["Deutsch"][2]:
                text = f"Kann ich den Zug {zugnummer} beim Anschluss {anschluss} auf dem linken Gleis schicken?"
        elif self.current_language == "Englisch":
            if anfrage == self.anfrage_options["Englisch"][0]:
                text = f"Is the connection {anschluss} free for train {zugnummer}?"
            elif anfrage == self.anfrage_options["Englisch"][1]:
                text = f"Is the connection {anschluss} free for the delayed train {zugnummer}?"
            elif anfrage == self.anfrage_options["Englisch"][2]:
                text = f"Can I send train {zugnummer} to connection {anschluss} on the left track?"
        elif self.current_language == "Polnisch":
            if anfrage == self.anfrage_options["Polnisch"][0]:
                text = f"Czy połączenie {anschluss} jest wolne dla pociągu {zugnummer}?"
            elif anfrage == self.anfrage_options["Polnisch"][1]:
                text = f"Czy połączenie {anschluss} jest wolne dla pociągu {zugnummer} z opóźnieniem?"
            elif anfrage == self.anfrage_options["Polnisch"][2]:
                text = f"Czy mogę wysłać pociąg {zugnummer} do połączenia {anschluss} na lewym torze?"

        self.copy_to_clipboard(text)
        self.status_label.config(text="Text in Zwischenablage kopiert.")


    def copy_to_clipboard(self, text):
        self.root.clipboard_clear()
        self.root.clipboard_append(text)
    def run(self):
        self.root.mainloop()


if __name__ == "__main__":
    app = TrainDriver2Helper()
    app.run()
