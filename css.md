Add background color to text
----------------------------
```css
box-shadow: 8px 0 0 #000, -8px 0 0 #000;
background-color: #000;
```
Use line-height and padding to adjust the height of the background for each row to your liking.

Rotating spinner
----------------
```css
#spinner{
  position: absolute;
  left: 50%;
  top: 50%;
  margin-left: -30px;
  margin-top: -30px;
  width: 60px;
  height: 60px;
  background: url("../images/sodio-spinner@2x.png");
  background-size: 60px 60px;
  -webkit-animation:spin 0.6s linear infinite;
  -moz-animation:spin 0.6s linear infinite;
  animation:spin 0.6s linear infinite;
}

@-moz-keyframes spin { 100% { -moz-transform: rotate(360deg); } }
@-webkit-keyframes spin { 100% { -webkit-transform: rotate(360deg); } }
@keyframes spin { 100% { -webkit-transform: rotate(360deg); transform:rotate(360deg); } }

```
