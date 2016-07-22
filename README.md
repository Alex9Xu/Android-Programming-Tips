Resolve Android Apps crash on Samsung with Android 5.0 and above:

If your app only crash on Samsung with Android 5.0/5.1, but runs well on other phones with Android 5.0/5.1, check this file: app/src/main/res/vales/styles.xml:

at this line <style name="YourProjectTheme" parent="...">, check if your code is such as

<style name="YourProjectTheme" parent="Base.ThemeOverlay.AppCompat.Light">

Samsung phones with Android 5.0/5.1 will crash on Base.ThemeOverlay... themes.

To deal with this bug, use Anroid Styles theme, such as:

<style name="YourProjectTheme" parent="@android:style/Theme.Holo.Light">

The bug is very difficult to find, because Android Studio is unable to show where this happens, it will show you that

"android.view.InflateException: Binary XML file line #7"

or

crash at com.android.internal.widget.ActionBarContextView

And both of them has nothing to do with the real reason.

I use almost four days to check where the bug is in a large project. (I am alex9xu@hotmail.com)

I searched with google and bing, and found nothing useful. So, am I the first one encounter this problem?

To help others deal with such bug, I write this.
