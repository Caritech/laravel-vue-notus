# Laravel Vue Notus 

This project is integrated https://demos.creative-tim.com/vue-notus/?_ga=2.267092621.20072000.1612621955-745088644.1610175099#/admin/dashboard into frontend

To demonstrate how to integrate third party vue frontend into Laravel project.

Currently, testable path:
- ***/admin/dashboard***


# How To Test
```
git clone https://github.com/Caritech/laravel-vue-notus.git
```

```
npm install
composer install
```

create .env file (you may copy from .env.example)
```
php artisan config：cache
php artisan migrate
npm run hot
php artisan serve
```

*need to start MySQL xampp*

access the demo page at http://127.0.0.1:8000/admin/dashboard
 
you should see this page

![Image](https://i.ibb.co/g4tzTwD/Captu22re.png)


# Tutorial & Things to Take Care
### public/..
For standalone vue project, the assets file like image is put in src/assets, 
In Laravel assets file is put in public folder. (so that, the image file can access through url)

### Resources/scss 
Any css file in vue project need to put in resources/scss, and use app.scss to import

(resources/css is use by postCss, however postCss dont have tutorial on import fontawesome, so use Scss)

(if you know how to use postCss, you may use it)

### Resources/js
Components and vue related files can put in resources/js,

In Laravel: suggested directory structure are:
- **resources/js/Pages** (same like Laravel views, use by Inertia::render(...) )
- **resources/js/Components** (global components, such as button, input field, select box)
- **resources/js/Layouts** (layouts such as Admin Dashboard Layout, User Dashboard Layout)

### Package.json
Need to manual validate and copy required pacakge from vue project to Laravel.

### webpack.mix.js
postCss do not have fontawsome integration sample, so using back sass (previous Laravel css compiler)
```
mix.js('resources/js/app.js', 'public/js').vue()
    .sass('resources/sass/app.scss', 'public/css') //add this line
    .options({ //chnage this line
        postCss: [
            require('postcss-import'),
            require('tailwindcss'),
            require('autoprefixer'),
        ]
    })
    .webpackConfig(require('./webpack.config'));

if (mix.inProduction()) {
    mix.version();
}
```

