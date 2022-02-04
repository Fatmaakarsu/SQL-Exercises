#### 1-test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
CREATE TABLE employee (
    id INTEGER,
    name VARCHAR(50),
    birthday DATE,
    email VARCHAR(100) 
);

#### 2-Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
insert into author (name, birthday, email) values ('Rayna', '1946-06-03', 'rwinslow0@house.gov');
insert into author (name, birthday, email) values ('Ancell', '1941-02-17', 'atonsley1@scientificamerican.com');
insert into author (name, birthday, email) values ('Anthiathia', '2002-10-08', 'aloblie2@thetimes.co.uk');

#### 3-Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
UPDATE employee SET name = 'Ali', birthday ='1989-09-04', email = 'ali@gmail.com' WHERE id BETWEEN 1 AND 5;

#### 4-Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
DELETE FROM employee WHERE name LIKE '%n';