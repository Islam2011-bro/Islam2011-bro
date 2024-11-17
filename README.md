<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Форма с обратой связью </title>
    <style>
        html {
            font-size: 16px;
        }
        body {
            margin: 0;
            font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        }
        .form-container {
            max-width: 450px;
            width: 95%;
            margin: auto;
            padding: 40px;
            box-shadow: 0 0 10px 1px rgba(0, 0, 0, 0.2);
            margin-top: 50px;
        }
        #form {

        }
        input {
            display: block;
            width: 100%;
            margin: 0.5rem 0;
            padding: 0.4rem 0;
            outline: none;
            font-size: 1rem;
            letter-spacing: 0.75px;
            border: none;
            border-bottom: 1.5px solid rgb(200, 200, 200);
            border-radius: 0;
            transition: 0.2s ease;
            -webkit-appearance: none;
        }
        input:focus {
            border-color: gray;
            border-color: rgb(95 158 160);
        }
        form-heading {
            margin-top: 0;
            font-size: 1.5rem;
            font-weight: 500;
            letter-spacing: 0.75px;
        }
        #submit {
            border: none;
            background-color: rgb(95 158 160);;
            color: white;
            text-shadow: 0 0 2px rgba(0, 0, 0, 0.2);
            border-radius: 3px;
            padding: 0.6rem 0;
            width: 150px;
            margin-left: calc(100% - 150px);
            box-shadow: 2px 2px 10px 0 rgba(0, 0, 0, 0.2);
            cursor: pointer;
            transition: 0.2s ease;
            margin-top: 1.5rem;
        }
        #sumbit:active {
            transform: translate(2px, 2px);
            box-shadow: none;
        }
        label {
            display: block;
            font-size: 0.9rem;
            letter-spacing: 0.75px;
            color: black;
        }
        input:-webkit-autofill {
            -webkit-box-shadow: 0 0 0px 1000px #fff inset;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h3 class="form heading">Формочка</h3>
        <form action="" id="form">
            <div class="field">
                <label for="name">Имя</label>
                <input type="text" id="name"    
            </div>
            <div class="field">
                <label for="email">EMAIL</label>
                <input type="email" id="email"
            </div>
            <input type="submit" id="submit"
        </form> 
    </div>

    <script>
        var inputs = [].slice.call(document.querySelectorAll('input'));
        inputs.forEach(function(input) {
            if(input.getAttribute('type') !=='sublit') {
                console.log(input);
                if(input.value != '') {
                    var label = document.querySelector('label[for="' +input.id +'"]');
                    label.classList.add('focused');

                }
                input.addEventListener('focusin', focusinInputHandler, false);
                input.addEventListener('focusin', focusinInputHandler, false);
            }
        });

        function focusinInputHandler () {
            var label =document.querySelector('lable[for="'  + this.id + '"]');
            label.classList.add('focused')
           // console.log(label);
           // console.log(this.id + ' focus in');
        }
        function focusinInputHandler () {
            var label =document.querySelector('lable[for="'  + this.id + '"]');
            if(this.value == '') {
                label.classList.remove('focused');
            }
          
           // console.log(this.id + 'focus out');
        }
    </script>
</body>
</html>
