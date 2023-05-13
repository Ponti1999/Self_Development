# Some useful tricks and good practices

During my Self Development Journey I have found some useful tricks and good practices about markdown documentation writing.

## If we want a secondary heading: ```##```
### If we want a tertiary heading: ```###```

If we want a new line we can use ```<br/>```. <br/>
(I usually use it at the end of a line or depends on the formatting to remain readable). <br/>

If we want to write in **bold** we can use ```**TextHere**```. <br/>
If we want to write in *italic* we can use ```*TextHere*```. <br/>
If we want to write in ***bold and italic*** we can use ```***TextHere***```. <br/>

If we want to write a code snippet we can use three backticks (```) <br/>
following with the name of the language and then the code snippet three backticks again. <br/>

<a id="Bullet-points"></a>
If we want to list it in bullet points we can use ```-``` or ```*``` <br/>
- Parent bullet point ```-```
  - Child bullet point ```  -```
    - Grandchild bullet point ```       -```

If we want to reference to a part of the documentation we can use ```[TextHere](#TextHere)``` <br/>
e.g. [Bullet points](#Bullet-points)  <br/>

If we want to reference to an external link we can use ```[TextHere](https://www.google.com)``` <br/>
e.g. [Google](https://www.google.com)  <br/>

If we want to reference to an image we can use ```![TextHere](https://www.google.com)``` <br/>
(Also with the same with our uploaded images.) <br/>
e.g. ![Google](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)  <br/>

To insert image from our local machine / repository we can use ```<img src="PATH" alt="NAME" style="height: XXX px; width:YYY px;"/>``` <br/>
