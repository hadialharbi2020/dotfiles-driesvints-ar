<p align="center"><img src="art/banner-2x.png"></p>

## المقدمة

يعتبر هذا المستودع وسيلتي لمساعدتي في إعداد وصيانة نظام macOS على جهازي. يقوم هذا المستودع بتسهيل عملية التثبيت عن طريق القيام بكل شيء يدويًا. يتم تفصيل كل ما يلزم لتثبيت نظام macOS بالإعدادات المفضلة بالنسبة لي في هذا الوثيقة. لا تتردد في استكشاف المحتوى والتعلم منه ونسخ أجزاء منه لاستخدامها في ملفات تكوين النظام الخاصة بك. استمتع!

📖 - [اقرأ مقال المدوّنة](https://driesvints.com/blog/getting-started-with-dotfiles)  
📺 - [شاهد الفيديو على Laracasts](https://laracasts.com/series/guest-spotlight/episodes/1)  
💡 - [تعلم كيف تقوم ببناء ملفات تكوين النظام الخاصة بك](https://github.com/driesvints/dotfiles#your-own-dotfiles)

إذا وجدت هذا المستودع مفيدًا، [فكّر في دعمي بمبلغ بسيط](https://github.com/sponsors/driesvints) (حتى قليلاً)! ❤️ 

## إعداد نظام macOS الجديد

هذه التعليمات مخصصة لإعداد أجهزة Mac جديدة. إذا كنت ترغب في البدء بإعداد ملفات تكوين النظام الخاصة بك، فيمكنك [العثور على تلك التعليمات أدناه](#your-own-dotfiles).

### قم بعمل نسخ احتياطية لبياناتك

إذا كنت تقوم بالانتقال من جهاز Mac قديم، يجب عليك التأكد أولاً من عمل نسخ احتياطية لجميع بياناتك الحالية. قم بالتحقق من القائمة أدناه للتأكد من أنك لم تنسى شيئًا قبل الانتقال.

- هل قمت بتأكيد ورفع أي تغييرات/فروع على مستودعات git الخاصة بك؟
- هل تذكرت أن تحفظ جميع المستندات الهامة من المجلدات التي ليست على iCloud؟
- هل قمت بحفظ جميع أعمالك من التطبيقات التي لا تتم مزامنتها عبر iCloud؟
- هل تذكرت أن تقوم بتصدير البيانات الهامة من قاعدة البيانات المحلية؟
- هل قمت بتحديث [mackup](https://github.com/lra/mackup) إلى أحدث إصدار وقمت بتشغيل `mackup backup`؟

### إعداد Mac الخاص بك

بعد نسخ احتياطي لجهاز Mac القديم، يمكنك الآن اتباع هذه التعليمات لإعداد جهاز جديد.

1. قم بتحديث macOS إلى أحدث إصدار من خلال تفضيلات النظام
2. [قم بإنشاء مفتاح SSH عام وخاص جديد](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) عن طريق تشغيل الأمر التالي:

   ```zsh
   curl https://raw.githubusercontent.com/driesvints/dotfiles/HEAD/ssh.sh | sh -s "<your-email-address>"
   ```

3. استنسخ هذا المستودع إلى `~/.dotfiles` باستخدام الأمر:

    ```zsh
    git clone --recursive git@github.com:driesvints/dotfiles.git ~/.dotfiles
    ```

4. قم بتشغيل عملية التثبيت باستخدام الأمر:

    ```zsh
    cd ~/.dotfiles && ./fresh.sh
    ```

5. قم بتشغيل `Herd.app` وقم بتشغيل عملية التثبيت الخاصة به
6. بعد مزامنة mackup مع تخزين السحابة الخاص بك، استعد الإعدادات باستخدام الأمر `mackup restore`
7. أعد تشغيل جهاز الكمبيوتر الخاص بك لإتمام العملية

أصبح جهاز Mac الخاص بك جاهز للاستخدام الآن!

> 💡 يمكنك استخدام موقع آخر للموقع من `~/.dotfiles` إذا كنت ترغب. تأكد أيضًا من تحديث المرجع في ملف [`.zshrc`](./.zshrc#L2).

### تنظيف جهاز Mac القديم (اخت

ياريًا)

بعد إعداد جهاز Mac الجديد، قد ترغب في مسح وإعادة تثبيت جهاز Mac القديم. قم باتباع [هذا المقال](https://support.apple.com/guide/mac-help/erase-and-reinstall-macos-mh27903/mac) للقيام بذلك. تذكر أن تقوم بعمل [نسخ احتياطي لبياناتك](#backup-your-data) أولاً!

## ملفات تكوين النظام الخاصة بك

**يرجى ملاحظة أن التعليمات أدناه تفترض أنك قد قمت بإعداد Oh My Zsh بالفعل، لذلك تأكد من تثبيت Oh My Zsh أولاً [من هنا](https://github.com/robbyrussell/oh-my-zsh#getting-started) قبل المتابعة.**

إذا كنت ترغب في البدء بملفات تكوين النظام الخاصة بك باستخدام هذه المجموعة، فمن السهل فعل ذلك. أولاً وقبل كل شيء، ستحتاج إلى عمل نسخة شخصية من هذا المستودع (fork). بعد ذلك، يمكنك ضبطها كما تريد.

تفقد محتوى الملف [`.macos`](./.macos) وقم بضبط الإعدادات حسب تفضيلاتك. يمكنك العثور على المزيد من الإعدادات في [النص البرمجي الأصلي لمؤلفه Mathias Bynens](https://github.com/mathiasbynens/dotfiles/blob/master/.macos) وفي [مشروع Kevin Suttle للإعدادات الافتراضية لنظام macOS](https://github.com/kevinSuttle/MacOS-Defaults).

تفقد ملف [`Brewfile`](./Brewfile) وقم بتعديل التطبيقات التي ترغب في تثبيتها على جهازك. استخدم [صفحة البحث](https://formulae.brew.sh/cask/) للتحقق مما إذا كان التطبيق الذي ترغب في تثبيته متاحًا.

تفقد ملف [`aliases.zsh`](./aliases.zsh) وأضف الأوامر المخصصة الخاصة بك. إذا كنت بحاجة إلى تعديل `$PATH` الخاص بك، تفقد ملف [`path.zsh`](./path.zsh). يتم تحميل هذه الملفات لأن إعداد `$ZSH_CUSTOM` يشير إلى دليل `.dotfiles`. يمكنك ضبط ملف [`.zshrc`](./.zshrc) حسب تفضيلاتك لتعديل إعدادات Oh My Zsh الخاصة بك. يمكن العثور على معلومات إضافية حول كيفية تخصيص Oh My Zsh [هنا](https://github.com/robbyrussell/oh-my-zsh/wiki/Customization).

عند تثبيت ملفات تكوين النظام هذه للمرة الأولى، ستحتاج إلى نسخ جميع إعداداتك باستخدام Mackup. قم بتثبيت Mackup واحتفظ بنسخ احتياطي للإعدادات باستخدام الأوامر أدناه. ستتم مزامنة إعداداتك مع iCloud حتى تتمكن من استخدامها لمزامنة بين الأجهزة واستعادتها عند إعادة تثبيت نظامك. إذا كنت ترغب في حفظ إعداداتك في مجلد أو تخزين مختلف عن iCloud، [شاهد الوثائق](https://github.com/lra/mackup/blob/master/doc/README.md#storage). تأكد أيضًا من ربط ملف `.zshrc` الخاص بك من مستودع ملفات تكوين النظام بمجلد المستخدم الخاص بك.

```zsh
brew install mackup
mackup backup
```

يمكنك تعديل سمة الشيل وإعدادات Oh My Zsh والمزيد بشكل كامل. تفقد محتوى هذا المستودع وقم بتعديل كل شيء بحسب تفضيلاتك.

تمتع بملفات تكوين النظام الخاصة بك!

## الشكر ل...

لقد حصلت لأول مرة على فكرة بدء هذا المشروع من خلال زيارة مشروع [GitHub does dotfiles](https://dotfiles.github.io/). كلاً من [Zach Holman](https://github.com/holman/dotfiles) و [Mathias Bynens](https://github.com/mathiasbynens/dotfiles) كانا مصدر إلهام كبير. أثبتت [دليل إعداد Mac OS X](http://sourabhbajaj.com/mac-setup/) لـ [Sourabh Bajaj](https://twitter.com

/sb2nov/) جدواه الفعلية. شكراً لـ [@subnixr](https://github.com/subnixr) لـ [سمته الرائعة للشيل](https://github.com/subnixr/minimal)! شكراً لـ [Caneco](https://twitter.com/caneco) لتصميم العنوان في هذا الوثيقة. وأخيرًا، أود أن أشكر [Emma Fabre](https://twitter.com/anahkiasen) على [عرضها الممتاز عن Homebrew](https://speakerdeck.com/anahkiasen/a-storm-homebrewin) الذي دفعني إلى الانتقال إلى [`Brewfile`](./Brewfile) و[Mackup](https://github.com/lra/mackup).

وبشكل عام، أود أن أشكر كل شخص يشارك ملفات تكوين النظام الخاصة به في مشروع مفتوح المصدر لجهودهم في المساهمة في المجتمع ذو الشفافية.
