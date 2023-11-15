# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as GalleryControl and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create a CustomizedGalleryAdapter file.

Step 7: Set the adapter for the gallery in the MainActivity file.

Step 8: Save and run the application.


## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by: A.Sanjay
Registeration Number : 212221040145
*/
```
```
XML FILE:

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<ImageView
    android:id="@+id/imageView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_marginTop="36dp"
    app:layout_constraintBottom_toTopOf="@+id/languagesGallery"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.466"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    tools:srcCompat="@tools:sample/avatars" />

<Gallery
    android:id="@+id/languagesGallery"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:animationDuration="2000"
    android:padding="10dp"
    android:spacing="5dp"
    android:unselectedAlpha="50"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.0"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"></Gallery>

</androidx.constraintlayout.widget.ConstraintLayout>
```
MAIN CODE:

package com.example.galleryview;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
Gallery simpleGallery;
CustomizedGalleryAdapter customGalleryAdapter;
ImageView selectedImageView;
int[] images = {R.drawable.p1, R.drawable.p2,R.drawable.p3,R.drawable.p4};
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
    selectedImageView = (ImageView) findViewById(R.id.imageView);
    customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);
    simpleGallery.setAdapter(customGalleryAdapter);
    simpleGallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
        @Override
        public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
            selectedImageView.setImageResource(images[position]);
        }
    });
}
}
CustomizedGalleryAdapter Code:

  package com.example.galleryview;

import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class CustomizedGalleryAdapter extends BaseAdapter {
private Context context;
private int[] images;
public CustomizedGalleryAdapter(Context c, int[] images) {
    context = c;
    this.images = images;
}
public int getCount() {
    return images.length;
}
public Object getItem(int position) {
    return position;
}
public long getItemId(int position) {
    return position;
}
public View getView(int position, View convertView, ViewGroup parent) {
    ImageView imageView = new ImageView(context);
    imageView.setImageResource(images[position]);
    imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
    return imageView;
}
}
```
```
## OUTPUT
![241160595-f6eb297d-26cd-4fe4-9cb8-7370731ead7b](https://github.com/MilitantVlr/Exp8/assets/121683193/3a871835-b63f-40b6-8401-6640de1c3fdf)
![241160614-ea00c67a-447b-432e-8c88-084127cc32e5](https://github.com/MilitantVlr/Exp8/assets/121683193/737db1f7-b449-4c1b-aeca-11c083bb503e)
![241160633-75bf214c-ecc7-4795-9251-3bc5920ba0a8](https://github.com/MilitantVlr/Exp8/assets/121683193/c98659fa-b966-44da-9b6a-6d5e30061df2)
![241160678-2da801b4-f67d-4286-852b-46823d155006](https://github.com/MilitantVlr/Exp8/assets/121683193/d98b2e4c-3ade-4e3a-bf9f-ddd261800b3b)
![241160655-8da0e4eb-31cb-4073-a2fd-216138cab42a](https://github.com/MilitantVlr/Exp8/assets/121683193/cc90bf69-73b1-46b2-bb2d-2d627221011f)




## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.
