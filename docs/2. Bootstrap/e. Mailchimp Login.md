

> [!todo] Desafio
> Criar a página de login do mailchimp

```html
 <!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.3/font/bootstrap-icons.css">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
    <link href="css/styles.css"  rel="stylesheet" />
</head>
  <body>
    <div class="container-fluid">
        <div class="row vh-100">
            <div class="col-lg-4 border-custom">
                <div class="d-flex flex-column vh-100 justify-content-between">
                    <div class="icon-size pt-2">
                        <img src="images/mc-freddie-dark.svg" />
                    </div>
                    <div class="col-12 col-xl-8 align-self-center">
                        <h1>Log In</h1>
                        <div class="d-flex flex-column my-5">
                            <p class="fs-6 m-0">Need a Mailchimp account?</p>
                            <a href="#">Create an account</a>    
                        </div>
                        <form class="d-flex flex-column">
                            <div class="mb-3">
                                <label for="exampleInputEmail1" class="form-label">Username or Email</label>
                                <input type="email" class="form-control rounded-0" id="exampleInputEmail1" aria-describedby="emailHelp">
                              </div>
                              <div class="mb-3">
                                <div class="d-flex justify-content-between align-items-center">
                                    <label for="exampleInputPassword1" class="form-label">Password</label>
                                    <div>
                                        <i class="bi bi-eye-slash"></i>
                                          <span>Hide</span>
                                    </div>
                                </div>
 
                                <input type="password" class="form-control rounded-0" id="exampleInputPassword1">
                              </div>
                              
                              <button type="submit" class="btn btn-primary p-3 rounded-0">Log In</button>

                              <div class="form-check align-self-center my-4">
                                <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
                                <label class="form-check-label" for="flexCheckDefault">
                                  Keep me Logged In
                                </label>
                              </div>
                              <div class="col-11 align-self-center text-center">
                                <a href="#">Forgot username?</a>
                                <span> · </span>
                                <a href="#">Forgot password?</a>
                                <a href="#">Can't Log In?</a>
                              </div>
                        </form>
                    </div>
                    <div class="text-secondary fs-custom py-2">
                        <label>© 2001–2023 All Rights Reserved. Mailchimp® is a registered trademark of The Rocket Science Group, LLC. Cookie Preferences, Privacy, and Terms.</label>
                    </div>
                </div>
            </div>
            <div class="col-lg-8 d-none d-lg-block bck-image"></div>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
  </body>
</html>
```


```css
h1 {
    font-family: Georgia, 'Times New Roman', Times, serif;
}
.fs-custom {
    font-size: 0.75em !important;
}
.bck-image {
    background-image: url(/images/phpza0iJx.jpeg);
    background-size: cover;
}
.icon-size {
    width: 40px;
}
.border-custom {
    border-left: 8px;
    border-color: rgb(232, 204, 28) ;
    border-style: solid;
    border-top: 0;
    border-bottom: 0;
}
```


