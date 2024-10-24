import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold( //temel düzen için
        appBar: AppBar( //uygulama çubuğu
          title: Text("Firmalar", style:TextStyle(color:Colors.white),),//firmalar yazısı ve özellikleri
          backgroundColor: Colors.blueAccent,
          centerTitle: true, 
          leading: IconButton( //sol kısma buton ekliyoruz
            icon: Icon(Icons.arrow_back, color:Colors.white), //butonun özellikleri
            onPressed: () {
              Navigator.pop(context); 
            },
          ),
        ),
        body: CompanyScreen(),//appbarın altını full companyscreen olarak alacağım
      ),
    );
  }
}

class CompanyScreen extends StatelessWidget {
  final List<String> companyNames = ["Firma A", "Firma B", "Firma C", "Firma D", "Firma E"]; // Firma isimleri dizisi

  @override
  Widget build(BuildContext context) {
    return Column( //satırsal olarak sıralamak için
      children: [
        Container(
          padding: EdgeInsets.all(16),//kenarlardan boşluk
          color: Colors.blueAccent,
          child: Row( //sütunsal olarak sıralamak için
            children: [
              Icon(Icons.local_hospital, color: Colors.white),//sağlık simgesi ve özellikleri
              SizedBox(width: 10),
              Text(
                "Sağlık",
                style: TextStyle(color: Colors.white, fontSize: 18),//sağlık yazısı özellikleri
                
              ),
            ],
          ),
        ),
        Padding(
          padding: const EdgeInsets.all(16.0),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start, // Yazının soldan başlamasını sağlamak
            children: [
              TextField( //yazı girişi için
                decoration: InputDecoration(
                  hintText: 'Firma Ara',
                  prefixIcon: Icon(Icons.search),//arama iconu
                  border: OutlineInputBorder(
                    borderRadius: BorderRadius.circular(10),//kenarları yuvarlat
                  ),
                ),
              ),
              SizedBox(height: 8), // Arama kutusu ile yazı arasında biraz boşluk bırakıyoruz
              Text(
                "İstediğiniz firmalardan indirim yakalama fırsatı", 
                style: TextStyle(color: Colors.grey[600], fontSize: 16), // Yazı rengi ve boyutu
              ),
            ],
          ),
        ),
        Expanded( //ekranın geri kalanı
          child: ListView.builder(
            itemCount: companyNames.length, // Firma isimlerinin sayısı kadar liste elemanı oluştur
            itemBuilder: (context, index) {
              return CompanyListItem(
                companyName: companyNames[index], // Firma ismini sırayla atıyoruz
                discount: "%10",
              );
            },
          ),
        ),
      ],
    );
  }
}

class CompanyListItem extends StatelessWidget {
  final String companyName;
  final String discount;

  CompanyListItem({required this.companyName, required this.discount});

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.symmetric(horizontal: 16.0, vertical: 8.0),//her elemanın yatay dikey boşluk
      child: Container(
        decoration: BoxDecoration(
          borderRadius: BorderRadius.circular(10),
          color: Colors.grey[200],//kutuların belli olması için arka planı  gri yaptım
          
        ),
        child: ListTile(
          title: Text(companyName),
          trailing: Container(
            padding: EdgeInsets.symmetric(horizontal: 12, vertical: 8),
            decoration: BoxDecoration(
              color: Colors.blueAccent, // indirim oranları için arka plan rengini mavi yaptık
              borderRadius: BorderRadius.circular(10),
            ),
            child: Text(
              discount,
              style: TextStyle(color: Colors.white, fontSize: 16),
            ),
          ),
        ),
      ),
    );
  }
}
