# GmailLogo
Library for dynamically creating user logos on PHP, based on Laravel. This lib may be used with another framework or event without, just change input class type from Laravel Model App\User to another. You event may not use models at all, simpty give the text that should be putted into the image.
<br/>
**Installation**:<br/>
```
composer require gmail-logo/generator
```
<br/>
<br/>

**Usage**:<br/>
<br/>
Lib has two main classes: Generator.php and Painter.php.
Painter is using methods of generators to generate custom images with color and text you like.

Also Painter contains first example of generating gmail logo: method typical().
Using this method you may just generate typical gmail logo. 
You just need to do so:
```
echo (new \GmailLogo\Painter())->typical();
```

This will output <img /> with necessary image.

If you need to generate some custom images, you may create new class which will extend Painter
and you code may look like this:

```
class CustomPainter extends \GmailLogo\Painter
{
    public function customImage()
    {
    }
}

echo (new CustomPainter())->customImage();
```


That is!!
<br/>
<br/>
<br/>
Using this package you can do things like this:
```
        $temporaryLogo = new Generator('John Doe', [75, 175], Font::ROBOTO_REGULAR);

        return $temporaryLogo
            ->setSizes(300,300)
            ->setRandomBackgroundColor()
            ->setTextColor(255,255,255)
            ->setTextSize(110)
            ->png()
            ->html();
```
This will create typical gmail logo for John Doe :D

This video will help you to understand how to use tha package:
https://youtu.be/LcNiCNdjUZI
