ᕕ( ᐛ )ᕗ
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
<!---
ButcheredPossum/ButcheredPossum is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
