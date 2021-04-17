using System.Data.Entity;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;

namespace travilproject.Entity
{
    public class DataInitializer:DropCreateDatabaseIfModelChanges<DataContext>
    {
        protected override void Seed(DataContext context)
        {
            var kategoriler = new List<category>()
            {
                new category() {Name="kamera" , Desciption="kamera ürünleri"},
                new category() {Name="Telefon" , Desciption="Telefon ürünleri"},
                new category() {Name="Bilgisayar" , Desciption="Bilgisayar ürünleri"},

            };
            foreach (var kategori in kategoriler)
            {
                context.categories.Add(kategori);
            }
            context.SaveChanges();
            var urunler = new List<product>()
            {
                new product(){Name="canon",Desciption="kamera ürünleri", price=2500 ,stock=150,IsHome=true,IsApproved=true,Isfeatured=false,slider=true,categoryId=1 ,image="1.jpg"
               },
                 new product(){Name="sony",Desciption="Telefon ürünleri", price=2000 ,stock=100,IsHome=true,IsApproved=true,Isfeatured=true,slider=true,categoryId=1 ,image="4.jpg"
               },
                
                new product(){Name="Asuz",Desciption="Bilgisayar ürünleri", price =6500 ,stock=100,IsHome=true,IsApproved=true,Isfeatured=true,slider=true,categoryId=3 ,image="2.jpg" },
                new product(){Name="lenovo",Desciption="Bilgisayar ürünleri", price=3000 ,stock=150,IsHome=true ,IsApproved=true,Isfeatured=false,slider=true,categoryId=3 ,image="3.jpg" },
                
            
            };
            foreach (var urun in urunler)
            {
                context.products.Add(urun);

            }
            context.SaveChanges();
            base.Seed(context);

        }
    }
}# E-Commerce-web-site
 online E-Commerce web site
