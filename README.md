
Menggunakan Intent

Memanggil Intent
Intent intent = new Intent(getApplicationContext(), Main2Activity.class);
intent.putExtra("pertama","activity pertama");
startActivityForResult(intent, REQUEST_CODE);

Mendapatkan nilai intent
Intent intent = getIntent.getExtras();
String username = intent.getString("pertama");

ResultIntent
static final int REQUEST_CODE = 1;
startActivityForResult(intent, REQUEST_CODE);

@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
if (requestCode == REQUEST_CODE){
    if (resultCode == RESULT_OK){
        String result = data.getStringExtra("returnData");
        Toast.makeText(getApplicationContext(), result, Toast.LENGTH_SHORT).show();
        }
    }
}

Intent retIntent = getIntent();
retIntent.putExtra("returnData","From Second Activity");
retIntent.putExtra("somethingselse", "This is something else");
setResult(RESULT_OK, retIntent);
finish();

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

