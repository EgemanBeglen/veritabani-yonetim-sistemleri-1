create database galeri

use galeri
create table musteri(
Mno int primary key identity(1,1),
Madi nvarchar(50),
Msoyadi nvarchar(50),
Madres nvarchar(50),
Mtelefon nvarchar(50)
);

create table araclar(
Aracno int identity(1,1) primary key,
yil int,
model nvarchar(50),
marka nvarchar(50),
plaka nvarchar(50),
fiyat float
);

create table satislar(
satisNo int primary key not null,
MNo int foreign key (Mno) references musteri(Mno),
AracNo int foreign key (Aracno) references araclar(Aracno),
SatisTarihi datetime,
Fiyat float
);

create table alislar(
alisNo int primary key not null,
MNo int foreign key (Mno) references musteri(Mno),
AracNo int foreign key (Aracno) references araclar(Aracno),
AlisTarihi datetime,
Fiyat float
);


insert into musteri values('Turgut', 'Özseven', 'Turhal/Tokat',	121646516416)
insert into musteri values('Mustafa', 'Çağlayan', 'Meram/Konya', 465245212323)
insert into musteri values('Ahmet', 'Kara', 'Zile/Tokat', 472376298362)
insert into musteri values('Murat', 'Beyaz', 'Turhal/Tokat', 385235293859)
insert into musteri values('Elif', 'Kurt', 'Beşiktaş/İstanbul',	948752835293)
insert into musteri values('Ayşe', 'Uçar', 'Taşova/Amasya',	487394698292)
insert into musteri values('Bülent', 'Ayar', 'Turhal/Tokat', 232378572352)

insert into araclar values('2004', 'Marea','Fiat', '38 VTYS 3838',	100000)
insert into araclar values('2020', 'Megane','Renault', '38 VTYS 3839',	110000)
insert into araclar values('2010', 'Focus','Ford', '38  VTYS 3840',	120000)
insert into araclar values('2023', 'Golf','Volkswagen', '38  VTYS 3841',	250000)
insert into araclar values('2000', 'Astra','Opel', '38  VTYS 3842',	82000)

insert into satislar values(1, 1, 1, '04.05.2022', 170000)
insert into satislar values(2, 4, 5, '01.06.2020', 115000)
insert into satislar values(3, 7, 4, '05.06.2023', 270000)
insert into satislar values(4, 2, 1, '02.07.2010', 17500)

insert into alislar values(1, 3, 1, '04.05.2022', 190000)
insert into alislar values(2, 6, 1, '01.06.2020', 525000)
insert into alislar values(4, 1, 2, '05.06.2023', 370000)
insert into alislar values(3, 2, 5, '02.07.2010', 17500)
insert into alislar values(5, 5, 3, '02.08.2021', 156800)


