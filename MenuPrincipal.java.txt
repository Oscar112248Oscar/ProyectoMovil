package com.example.proyectomovil;

import androidx.appcompat.app.AppCompatActivity;
import androidx.cardview.widget.CardView;

import android.content.Intent;
import android.os.Bundle;
import android.os.CountDownTimer;
import android.view.View;
import android.widget.Toast;

public class MenuPrincipal extends AppCompatActivity {

CardView peliculas;
    int contador=0;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_menu_principal);

// Busco la por el id del elemento
        peliculas=(CardView)findViewById(R.id.peliculas);
    }

    public  void peliculas(View view){

        Intent miIntent= new Intent(getApplicationContext(),Productos.class);
        getApplicationContext().startActivity(miIntent);

    }

    public  void estrenos(View view){

        Intent miIntent= new Intent(getApplicationContext(),Estrenos.class);
        getApplicationContext().startActivity(miIntent);


    }

    public  void mapa(View view){

        Intent miIntent= new Intent(getApplicationContext(),Ubicacion.class);
        getApplicationContext().startActivity(miIntent);

    }

    public void reservar(View v){
        Intent miIntent=new Intent( getApplicationContext(), Reserva.class );
        getApplicationContext()startActivity( miIntent );
    }

    @Override
    public void onBackPressed() {

		///// Sirve para tener el control de la tecla hacia atras del propio telefono

        if(contador==0){
            Toast.makeText(this,"PRESIONE DE NUEVO PARA SALIR!!", Toast.LENGTH_SHORT).show();
            contador=contador+1;
        } else {

            super.onBackPressed();
            finish();
        }
        new CountDownTimer(3000,1000){


            @Override
            public void onTick(long millisUntilFinished) {

            }

            @Override
            public void onFinish() {
                contador=0;


            }
        }.start();

    }
}
