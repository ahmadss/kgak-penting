
Menggunakan SharedPreferences

MODE _PRIVATE: mode normal, dimana SharedPreferences hanya bisa diakses dari aplikasi tempat ia di deklarasi saja.
MODE_WORLD_READABLE: mode dimana SharedPreferences dapat dibaca oleh aplikasi lain, namun aplikasi lain tidak dapat mengubah isinya (Read Only).
MODE_WORLD_WRITEABLE: mode dimana SharedPreferences dapat dibaca oleh aplikasi lain, dan aplikasi lain juga dapat mengubah isinya.

Sintak untuk mengubah nilai 

SharedPreferences prefs = getSharedPreferences("myData", MODE_PRIVATE);
Editor mEditor = prefs.edit();
mEditor.putString("username", "ahmad saifuddin");
mEditor.commit();

Sintak untuk membaca nilai

SharedPreferences prefs = getSharedPreferences("myData", Context.MODE_PRIVATE);
String username = prefs.getString("username", null);

