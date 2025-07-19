# WordPress Disable Gutenberg

This straightforward code snippet allows you to **completely disable the Gutenberg block editor** for both posts/pages and widgets in WordPress. While Gutenberg is the default editor, some users or developers prefer the classic editor experience or rely on page builders that conflict with Gutenberg. This solution gives you full control over disabling it site-wide.

## Why disable Gutenberg?

* **Preference for Classic Editor:** Many users are accustomed to and prefer the simpler, more traditional WordPress classic editor.
* **Compatibility Issues:** Some older themes or plugins might not be fully compatible with Gutenberg, causing display or functionality issues.
* **Page Builder Integration:** If you're heavily reliant on a specific page builder (e.g., Elementor, Beaver Builder, Divi Builder), you might prefer to disable Gutenberg to avoid conflicts or streamline your content creation workflow.
* **Simplicity:** For very basic sites, the block editor might introduce unnecessary complexity.

## Features

* **Disables Gutenberg for Posts and Pages:** Reverts the post and page editing experience back to the Classic Editor.
* **Disables Gutenberg for Widgets:** Restores the traditional widget management interface (found under Appearance > Widgets).
* **Site-wide Application:** Disables Gutenberg globally across your WordPress installation.

## Installation

There are two primary methods to implement this code:

### Method 1: As a Standalone Plugin (Recommended)

Creating a small, dedicated plugin is the most robust way to add this functionality. It ensures your modification remains active regardless of theme changes.

1.  Create a new folder named `wp-no-gutenberg` inside your WordPress site's `wp-content/plugins/` directory.
2.  Inside this new folder, create a file named `wp-no-gutenberg.php`.
3.  Copy and paste the following code into `wp-no-gutenberg.php`:

    ```php
    <?php
    /**
     * Plugin Name: WordPress Disable Gutenberg
     * Description: Disables the Gutenberg block editor for posts/pages and widgets.
     * Version: 1.0
     * Author: Your Name (Optional)
     * License: GPL-2.0-or-later
     */

    if ( ! defined( 'ABSPATH' ) ) {
        exit; // Exit if accessed directly.
    }

    // Disable Gutenberg for posts and pages
    add_filter('use_block_editor_for_post', '__return_false');

    // Disable Gutenberg for widgets
    add_filter('use_widgets_block_editor', '__return_false');
    ?>
    ```

4.  Go to your WordPress admin dashboard, navigate to **"Plugins"**, and **activate** the "WordPress Disable Gutenberg" plugin.

### Method 2: Adding to your Theme's functions.php File

You can add this code directly to your active theme's `functions.php` file. **Before doing so, it's highly recommended to back up your `functions.php` file.**

1.  Navigate to `wp-content/themes/YourThemeName/` (replace `YourThemeName` with the actual name of your active theme).
2.  Open the `functions.php` file.
3.  Add the following code to the end of the file (before the closing `?>` tag, if one exists):

    ```php
    // Disable Gutenberg for posts and pages
    add_filter('use_block_editor_for_post', '__return_false');

    // Disable Gutenberg for widgets
    add_filter('use_widgets_block_editor', '__return_false');
    ```

## Important Considerations

* **Reversibility:** To re-enable Gutenberg, simply deactivate or remove this plugin/code.
* **Future WordPress Updates:** While `__return_false` is generally robust, major WordPress updates might occasionally introduce changes that require a review of such filters.
* **Alternatives:** If you only want to disable Gutenberg for *specific* post types or users, there are more granular solutions or plugins available that offer such control. This snippet provides a complete site-wide disablement.

## Contributing

Contributions are welcome! If you have suggestions or improvements for this code, feel free to open a "Pull Request" or report an "Issue."

## License

This project is licensed under the GPL-2.0-or-later License.

# غیرفعال‌سازی گوتنبرگ در وردپرس

این قطعه کد ساده به شما امکان می‌دهد تا **ویرایشگر بلوک گوتنبرگ** را هم برای نوشته‌ها/صفحات و هم برای ابزارک‌ها (widgets) در وردپرس به طور کامل غیرفعال کنید. اگرچه گوتنبرگ ویرایشگر پیش‌فرض است، برخی از کاربران یا توسعه‌دهندگان تجربه ویرایشگر کلاسیک را ترجیح می‌دهند یا به صفحه سازهایی متکی هستند که با گوتنبرگ تداخل دارند. این راه حل کنترل کاملی را برای غیرفعال کردن آن در سطح سایت به شما می‌دهد.

## چرا گوتنبرگ را غیرفعال کنیم؟

* **ترجیح ویرایشگر کلاسیک:** بسیاری از کاربران به ویرایشگر کلاسیک وردپرس، که ساده‌تر و سنتی‌تر است، عادت کرده‌اند و آن را ترجیح می‌دهند.
* **مشکلات سازگاری:** برخی از قالب‌ها یا افزونه‌های قدیمی ممکن است به طور کامل با گوتنبرگ سازگار نباشند و باعث مشکلات نمایش یا عملکرد شوند.
* **ادغام با صفحه ساز:** اگر به شدت به یک صفحه ساز خاص (مانند المنتور، Beaver Builder، دیوی بیلدر) متکی هستید، ممکن است ترجیح دهید گوتنبرگ را برای جلوگیری از تداخل یا ساده‌سازی گردش کار ایجاد محتوای خود غیرفعال کنید.
* **سادگی:** برای سایت‌های بسیار ابتدایی، ویرایشگر بلوک ممکن است پیچیدگی غیرضروری ایجاد کند.

## قابلیت‌ها

* **غیرفعال کردن گوتنبرگ برای نوشته‌ها و صفحات:** تجربه ویرایش نوشته و صفحه را به ویرایشگر کلاسیک بازمی‌گرداند.
* **غیرفعال کردن گوتنبرگ برای ابزارک‌ها:** رابط مدیریت سنتی ابزارک‌ها را (که در بخش نمایش > ابزارک‌ها یافت می‌شود) بازمی‌گرداند.
* **اعمال در سراسر سایت:** گوتنبرگ را به صورت جهانی در سراسر نصب وردپرس شما غیرفعال می‌کند.

## نصب

برای پیاده‌سازی این کد، دو روش اصلی وجود دارد:

### روش ۱: به عنوان یک افزونه مستقل (توصیه شده)

ایجاد یک افزونه کوچک و اختصاصی، قوی‌ترین راه برای افزودن این قابلیت است. این تضمین می‌کند که تغییر شما صرف‌نظر از تغییر قالب، فعال باقی بماند.

1.  یک پوشه جدید با نام `wp-no-gutenberg` در مسیر `wp-content/plugins/` سایت وردپرسی خود ایجاد کنید.
2.  در داخل این پوشه جدید، یک فایل با نام `wp-no-gutenberg.php` ایجاد کنید.
3.  کد زیر را در `wp-no-gutenberg.php` کپی و جایگذاری کنید:

    ```php
    <?php
    /**
     * Plugin Name: WordPress Disable Gutenberg
     * Description: Disables the Gutenberg block editor for posts/pages and widgets.
     * Version: 1.0
     * Author: Your Name (Optional)
     * License: GPL-2.0-or-later
     */

    if ( ! defined( 'ABSPATH' ) ) {
        exit; // Exit if accessed directly.
    }

    // Disable Gutenberg for posts and pages
    add_filter('use_block_editor_for_post', '__return_false');

    // Disable Gutenberg for widgets
    add_filter('use_widgets_block_editor', '__return_false');
    ?>
    ```

4.  وارد پنل مدیریت وردپرس خود شوید، به بخش **"افزونه‌ها"** بروید و افزونه **"غیرفعال‌سازی گوتنبرگ در وردپرس"** را **فعال کنید**.

### روش ۲: اضافه کردن به فایل functions.php قالب شما

می‌توانید این کد را مستقیماً به فایل `functions.php` قالب فعال خود اضافه کنید. **پیشنهاد اکید می‌شود قبل از انجام این کار، از فایل `functions.php` خود یک پشتیبان (backup) تهیه کنید.**

1.  به مسیر `wp-content/themes/YourThemeName/` بروید (به جای `YourThemeName` نام واقعی قالب فعال خود را قرار دهید).
2.  فایل `functions.php` را باز کنید.
3.  کد زیر را به انتهای فایل (قبل از تگ بستن `?>`، در صورت وجود) اضافه کنید:

    ```php
    // Disable Gutenberg for posts and pages
    add_filter('use_block_editor_for_post', '__return_false');

    // Disable Gutenberg for widgets
    add_filter('use_widgets_block_editor', '__return_false');
    ```

## ملاحظات مهم

* **قابلیت بازگشت:** برای فعال‌سازی مجدد گوتنبرگ، کافیست این افزونه/کد را غیرفعال یا حذف کنید.
* **به‌روزرسانی‌های آینده وردپرس:** اگرچه `__return_false` به طور کلی قوی است، ممکن است به‌روزرسانی‌های اصلی وردپرس گاهی تغییراتی را معرفی کنند که نیاز به بررسی مجدد چنین فیلترهایی داشته باشند.
* **جایگزین‌ها:** اگر فقط می‌خواهید گوتنبرگ را برای *انواع پست خاص* یا *کاربران خاص* غیرفعال کنید، راه‌حل‌ها یا افزونه‌های دقیق‌تری در دسترس هستند که چنین کنترلی را ارائه می‌دهند. این قطعه کد یک غیرفعال‌سازی کامل در سطح سایت را فراهم می‌کند.

## مشارکت (Contributing)

مشارکت شما خوشایند است! اگر پیشنهاد یا بهبودهایی برای این کد دارید، می‌توانید یک "Pull Request" ایجاد کنید یا "Issue" جدیدی را گزارش دهید.

## مجوز (License)

این پروژه تحت مجوز GPL-2.0-or-later منتشر شده است.
