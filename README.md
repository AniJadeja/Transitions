# Transitions



    If you want to apply the animation on "activity" start. then write below code.

startActivity(intent);
overridePendingTransition(R.anim.opening_anim, R.anim.closing_anim);

    If you want to apply the animation on "dialog" then firstly add below code in styles.xml file

<style name="my_style”> 
 <item 
  name="@android:windowEnterAnimation">@anim/opening_anim</item> 
 <item 
 name="@android:windowExitAnimation">@anim/closing_anim</item>
</style>

Use this style as I defined below.

final Dialog dialog = new Dialog(activity);
dialog.getWindow().getAttributes().windowAnimations = R.style.my_style;

    If you want to apply the animation on "view" then write below code

txtMessage = (TextView) findViewById(R.id.txtMessage);
     
// load the animation
Animation animFadein = AnimationUtils.loadAnimation(getApplicationContext(),R.anim.animation); 

// start the animation
txtMessage.startAnimation(animFadein);

    Below, I have mentioned most of the animation .xml code.
```
appear - make it just appear.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="1"
           android:fromAlpha="1.0"
           android:toAlpha="1.0"/>
</set>

```
make it slowly fades into view.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha
        android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator" 
        android:duration="300"
        android:repeatCount="0" />
</set>

```
fadeout - make it slowly fade out of view.xml
```
<?xml version="1.0" encoding="UTF-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha
        android:fromAlpha="1.0"
        android:toAlpha="0.0"
        android:interpolator="@android:anim/accelerate_interpolator" 
        android:duration="300"
        android:repeatCount="0" />
</set>
                               
```
push_down_in.xml
                               
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromYDelta="-100%p" android:toYDelta="0" android:duration="400"/>
</set>
```

push_down_out.xml
                                                                                      
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromYDelta="0" android:toYDelta="100%p" android:duration="400"/>
</set>
```

push_left_in.xml
                                                                                     
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="100%p" android:toXDelta="0" android:duration="300"/>
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0" android:duration="300" />
</set>

```
push_left_out.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="0" android:toXDelta="-100%p" android:duration="300"/>
    <alpha android:fromAlpha="1.0" android:toAlpha="0.0" android:duration="300" />
</set>

```
push_right_in.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="-100%p" android:toXDelta="0" android:duration="300"/>
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0" android:duration="300" />
</set>

```
push_right_out.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="0" android:toXDelta="100%p" android:duration="300"/>
    <alpha android:fromAlpha="1.0" android:toAlpha="0.0" android:duration="300" />
</set>

```
push_up_in.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromYDelta="100%p" android:toYDelta="0" android:duration="300"/>
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0" android:duration="300" />
</set>

```
push_up_out.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromYDelta="0" android:toYDelta="-100%p" android:duration="300"/>
    <alpha android:fromAlpha="1.0" android:toAlpha="0.0" android:duration="300" />
</set>
```

rotation.xml
```
<?xml version="1.0" encoding="utf-8"?>
<rotate
 xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="-90"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="0" android:fillAfter="true">
</rotate>
```

scale_from_corner.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale android:fromYScale="0" android:toYScale="1.0"
        android:fromXScale="0" android:toXScale="1.0" 
        android:duration="500" android:pivotX="100%"
        android:pivotY="100%" />
</set>
```
scale_torwards_corner.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale android:fromYScale="1.0" android:toYScale="0"
        android:fromXScale="1.0" android:toXScale="0" 
        android:duration="500"/>
</set>

```
shrink_and_rotate_a(exit).xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
<scale
    android:fromXScale="1.0" android:toXScale="0.8"
    android:fromYScale="1.0" android:toYScale="0.8"
    android:pivotX="50%p" android:pivotY="50%p"
    android:interpolator="@android:anim/accelerate_interpolator"
    android:duration="100"
/>
<scale
    android:fromXScale="1.0" android:toXScale="0.0"
    android:fromYScale="1.0" android:toYScale="1.0"
    android:pivotX="50%p" android:pivotY="50%p"
    android:interpolator="@android:anim/accelerate_interpolator"
    android:duration="150"
    android:startOffset="100"
/>

```
shrink_and_rotate_b(entrance).xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
<scale
    android:fromXScale="0.0" android:toXScale="1.0"
    android:fromYScale="1.0" android:toYScale="1.0"
    android:pivotX="50%p" android:pivotY="50%p"
    android:interpolator="@android:anim/accelerate_interpolator"
    android:duration="150"
    android:startOffset="250"
/>

<scale
    android:fromXScale="0.8" android:toXScale="1.0"
    android:fromYScale="0.8" android:toYScale="1.0"
    android:pivotX="50%p" android:pivotY="50%p"
    android:interpolator="@android:anim/accelerate_interpolator"
    android:duration="100"
    android:startOffset="400"
/>


```
blink.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0"
      android:toAlpha="1.0"
      android:interpolator="@android:anim/accelerate_interpolator"
      android:duration="800"
      android:repeatMode="reverse"
      android:repeatCount="infinite"/>
</set>

```
ZoomIn.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >
    <scale
       xmlns:android="http://schemas.android.com/apk/res/android"
       android:duration="1000"
       android:fromXScale="1"
       android:fromYScale="1"
       android:pivotX="50%"
       android:pivotY="50%"
       android:toXScale="3"
       android:toYScale="3" >
    </scale>
</set>

```
ZoomOut.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >
    <scale
       xmlns:android="http://schemas.android.com/apk/res/android"
       android:duration="1000"
       android:fromXScale="1.0"
       android:fromYScale="1.0"
       android:pivotX="50%"
       android:pivotY="50%"
       android:toXScale="0.5"
       android:toYScale="0.5" >
    </scale>
</set>

```
FadeIn.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >
    <alpha
       android:duration="1000"
       android:fromAlpha="0.0"
       android:interpolator="@android:anim/accelerate_interpolator"
       android:toAlpha="1.0" />
</set>

```
FadeOut.xml
```
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >
    <alpha
       android:duration="1000"
       android:fromAlpha="1.0"
       android:interpolator="@android:anim/accelerate_interpolator"
       android:toAlpha="0.0" />
</set>

```
Move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set
   xmlns:android="http://schemas.android.com/apk/res/android"
   android:interpolator="@android:anim/linear_interpolator"
   android:fillAfter="true">
   <translate
       android:fromXDelta="0%p"
       android:toXDelta="80%p"
       android:duration="1000" />
</set>

```
SlideDown.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true">
    <scale
       android:duration="800"
       android:fromXScale="1.0"
       android:fromYScale="0.0"
       android:interpolator="@android:anim/linear_interpolator"
       android:toXScale="1.0"
       android:toYScale="1.0" />
</set>
```

SlideUp.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >
    <scale
       android:duration="800"
       android:fromXScale="1.0"
       android:fromYScale="1.0"
       android:interpolator="@android:anim/linear_interpolator"
       android:toXScale="1.0"
       android:toYScale="0.0" />
</set>
```
Bounce.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true"
   android:interpolator="@android:anim/bounce_interpolator">
    <scale
       android:duration="800"
       android:fromXScale="1.0"
       android:fromYScale="0.0"
       android:toXScale="1.0"
       android:toYScale="1.0" />
</set>
```
