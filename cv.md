# Konstantin Tarasov

## Junior Frontend Developer

### Contacts

* **Country of residence:** Russia, Moscow
* **E-Mail:** [madsok25@gmail.com](https://github.com/madsok "GitHub link") 
* **GitHub:** [madsok](https://github.com/madsok "GitHub link") 
* **Codewars:** [madsok](https://www.codewars.com/users/madsok "Codewars link")

### About me

I've been working for 9 years as education manager and some time ago had decided to change my job. I chose web development, because it's modern, creative industry and it's easy by self-education to get in. I love programming for one thing. Like soviet actor Anatoly Papanov said: 
> I like the garden work. You digged a garden and at once can see the result of work.    

So the same in the programming. 

### Skills

* **HTML5**
* **CSS3 (SASS, BEM)**
* **JavaScript**
* **Git**
* **Gulp**
* **Figma**

### Code examples

Code for validating form inputs on the website.  

```
export function valid (form) {
    let inputs = form.querySelectorAll('.form__input');

    let validityChecks = [
            [
                {
                    isValid (input) {
                        return input.value.length > 1;
                    },
                    langMessage: {
                        el: 'Το όνομα πρέπει να περιέχει τουλάχιστον 2 χαρακτήρες',
                        ru: 'Имя должно содержать минимум 2 символа',
                        en: 'Name must contain at least 2 characters'
                    }
                },
                {
                    isValid (input) {
                        const REG_EXP = new RegExp(/^[A-Za-zА-яа-яΑ-Ωα-ωίϊΐόάέύϋΰήώ]+$/i);
                        let illegalCharacters = REG_EXP.test(input.value);
                        return illegalCharacters ? true : false;
                    },
                    langMessage: {
                        el: 'Το όνομα πρέπει να περιέχει μόνο γράμματα',
                        ru: 'Имя должно состоять только из букв',
                        en: 'Name must contain only letters'
                    }
                }
            ],
            [
                {
                    isValid (input) {
                        return input.value.length > 0;
                    },
                    langMessage: {
                        el: 'Το email πρέπει να περιέχει τουλάχιστον 1 χαρακτήρα',
                        ru: 'Email должен содержать минимум 1 символ',
                        en: 'Email must contain at least 1 character'
                    }
                },
                {
                    isValid (input) {
                        const REG_EXP = new RegExp(/^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i);                    
                        let illegalCharacters = REG_EXP.test(input.value);
                        return illegalCharacters ? true : false;
                    },
                    langMessage: {
                        el: 'Λανθασμένη μορφή email',
                        ru: 'Неправильный формат email',
                        en: 'Incorrect email format'
                    }
                }
            ],
            [
                {
                    isValid (input) {
                        return input.value.length > 0;
                    },
                    langMessage: {
                        el: 'Εισαγάγετε το μήνυμά σας',
                        ru: 'Введите сообщение',
                        en: 'Enter the message'
                    }
                }
            ]
        ]

    function validate (input, checks) {
        let language = navigator.language || navigator.userLanguage;
            language = language.substr(0, 2).toLowerCase();

        let error = input.nextElementSibling;
            error.textContent = '';

        let valids = [];

        for (let i = 0; i < checks.length; i++) {  
            let isValid = checks[i].isValid(input);

            if (isValid) {
                valids.push(isValid);
            } else {
                for (let key in checks[i].langMessage) {
                    if (key == language) {
                        let message = document.createElement('p');
                        message.textContent = `${checks[i].langMessage[key]}.`;  
                        error.append(message);                      
                    }
                }
            }
        }
        
        if (valids.every(valid => valid === true) && valids.length == checks.length) {
            error.previousElementSibling.classList.remove('invalid');
            error.previousElementSibling.classList.add('valid');
            return true;
        } else {
            error.previousElementSibling.classList.remove('valid');
            error.previousElementSibling.classList.add('invalid');
            return false;
        }
    }
        
    function validateOnSubmit() {
        let valids = [];

        for (let i = 0; i < inputs.length; i++) {
            validate(inputs[i], validityChecks[i]);
            valids.push(validate(inputs[i], validityChecks[i]));
        }

        if (valids.every(valid => valid === true) && valids.length == inputs.length) {
            return true;
        } else {
            return false;
        }
    }

    for (let i = 0; i < inputs.length; i++) {
            inputs[i].addEventListener('keyup', function() {
                validate(inputs[i], validityChecks[i]);
            });
        }

    return validateOnSubmit();
}
```
#### My works

1. [Petrovich Medical Center Website](https://www.petrovichmc.com/ "Website link") 
2. [Hadjistyllis Garage](http://shgarage.com/ "Website link") 

### Languages

* **Russian** (First language)
* **English** (Intermediate)