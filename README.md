ᕕ( ᐛ )ᕗ
Zadanie polega na utworzeniu baz danych w MySQL z tabelami, a także dodaniu po 10 rekordów do każdej z nich. Możemy napisać odpowiednie skrypty SQL, które wykonasz w XAMPP, by utworzyć bazy danych i tabele. Oto jak mogłoby to wyglądać:

1. Baza danych "Biblioteka"

Tabela "Ksiazki"

CREATE DATABASE Biblioteka;
USE Biblioteka;

CREATE TABLE Ksiazki (
    id_ksiazki INT PRIMARY KEY AUTO_INCREMENT,
    tytul VARCHAR(100),
    autor VARCHAR(100),
    rok_wydania YEAR
);

INSERT INTO Ksiazki (tytul, autor, rok_wydania) VALUES
('Pan Tadeusz', 'Adam Mickiewicz', 1834),
('Lalka', 'Bolesław Prus', 1890),
('Krzyżacy', 'Henryk Sienkiewicz', 1900),
('Dziady', 'Adam Mickiewicz', 1823),
('Potop', 'Henryk Sienkiewicz', 1886),
('W pustyni i w puszczy', 'Henryk Sienkiewicz', 1911),
('Chłopi', 'Władysław Reymont', 1904),
('Faraon', 'Bolesław Prus', 1897),
('Zbrodnia i kara', 'Fiodor Dostojewski', 1866),
('Ojciec Goriot', 'Honoré de Balzac', 1835);

2. Baza danych "Szkola"

Tabela "Uczniowie"

CREATE DATABASE Szkola;
USE Szkola;

CREATE TABLE Uczniowie (
    id_ucznia INT PRIMARY KEY AUTO_INCREMENT,
    imie VARCHAR(50),
    nazwisko VARCHAR(50),
    klasa VARCHAR(10)
);

INSERT INTO Uczniowie (imie, nazwisko, klasa) VALUES
('Jan', 'Kowalski', '1A'),
('Anna', 'Nowak', '2B'),
('Piotr', 'Wiśniewski', '3C'),
('Maria', 'Kowalczyk', '1D'),
('Tomasz', 'Lewandowski', '2E'),
('Magdalena', 'Zielińska', '3A'),
('Krzysztof', 'Szymański', '1B'),
('Aleksandra', 'Dąbrowska', '2C'),
('Michał', 'Wojciechowski', '3D'),
('Katarzyna', 'Kozłowska', '1E');

3. Baza danych "Pracownicy"

Tabela "Pracownicy" i "Departamenty"

CREATE DATABASE Pracownicy;
USE Pracownicy;

CREATE TABLE Pracownicy (
    id_pracownika INT PRIMARY KEY AUTO_INCREMENT,
    imie VARCHAR(50),
    stanowisko VARCHAR(50)
);

CREATE TABLE Departamenty (
    id_departamentu INT PRIMARY KEY AUTO_INCREMENT,
    nazwa VARCHAR(50),
    lokalizacja VARCHAR(100)
);

INSERT INTO Pracownicy (imie, stanowisko) VALUES
('Marek', 'Kierownik'),
('Ewa', 'Asystent'),
('Jakub', 'Inżynier'),
('Paweł', 'Specjalista'),
('Agnieszka', 'HR'),
('Grzegorz', 'Dyrektor'),
('Joanna', 'Sekretarka'),
('Mateusz', 'IT'),
('Sylwia', 'Marketing'),
('Patryk', 'Logistyka');

INSERT INTO Departamenty (nazwa, lokalizacja) VALUES
('HR', 'Warszawa'),
('IT', 'Kraków'),
('Marketing', 'Gdańsk'),
('Logistyka', 'Poznań'),
('Finanse', 'Wrocław');

4. Baza danych "Zakupy"

Tabele: "Klienci", "Zamowienia", "Produkty"

CREATE DATABASE Zakupy;
USE Zakupy;

CREATE TABLE Klienci (
    id_klienta INT PRIMARY KEY AUTO_INCREMENT,
    imie VARCHAR(50),
    email VARCHAR(100)
);

CREATE TABLE Zamowienia (
    id_zamowienia INT PRIMARY KEY AUTO_INCREMENT,
    id_klienta INT,
    data_zamowienia DATE,
    FOREIGN KEY (id_klienta) REFERENCES Klienci(id_klienta)
);

CREATE TABLE Produkty (
    id_produktu INT PRIMARY KEY AUTO_INCREMENT,
    nazwa VARCHAR(100),
    cena DECIMAL(10, 2)
);

INSERT INTO Klienci (imie, email) VALUES
('Adam', 'adam@example.com'),
('Ewa', 'ewa@example.com'),
('Jan', 'jan@example.com'),
('Anna', 'anna@example.com'),
('Piotr', 'piotr@example.com'),
('Maria', 'maria@example.com'),
('Tomasz', 'tomasz@example.com'),
('Agnieszka', 'agnieszka@example.com'),
('Jakub', 'jakub@example.com'),
('Katarzyna', 'katarzyna@example.com');

INSERT INTO Zamowienia (id_klienta, data_zamowienia) VALUES
(1, '2023-01-10'),
(2, '2023-02-15'),
(3, '2023-03-20'),
(4, '2023-04-05'),
(5, '2023-05-25'),
(6, '2023-06-30'),
(7, '2023-07-12'),
(8, '2023-08-18'),
(9, '2023-09-22'),
(10, '2023-10-03');

INSERT INTO Produkty (nazwa, cena) VALUES
('Telefon', 1500.00),
('Laptop', 3500.00),
('Tablet', 1200.00),
('Monitor', 800.00),
('Myszka', 50.00),
('Klawiatura', 100.00),
('Drukarka', 600.00),
('Router', 200.00),
('Słuchawki', 250.00),
('Kamera', 500.00);

Dla zadania dodatkowego ("Zakupy" - relacje między tabelami):

-- Utworzenie relacji pomiędzy Zamowienia i Klienci już jest zrobione (foreign key).
-- Możemy dodać jeszcze relację między Zamowienia a Produkty, ale trzeba utworzyć tabelę pośrednią dla relacji wiele-do-wielu:

CREATE TABLE Zamowienia_Produkty (
    id_zamowienia INT,
    id_produktu INT,
    FOREIGN KEY (id_zamowienia) REFERENCES Zamowienia(id_zamowienia),
    FOREIGN KEY (id_produktu) REFERENCES Produkty(id_produktu)
);

-- Przykładowe dane:
INSERT INTO Zamowienia_Produkty (id_zamowienia, id_produktu) VALUES
(1, 1),
(1, 2),
(2, 3),
(3, 4),
(4, 5),
(5, 6),
(6, 7),
(7, 8),
(8, 9),
(9, 10);

To są gotowe skrypty SQL do wykonania w XAMPP, aby stworzyć bazy danych, tabele oraz dodać rekordy.


<!---
ButcheredPossum/ButcheredPossum is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
