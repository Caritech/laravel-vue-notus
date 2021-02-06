# Laravel Vue Notus 

This project is integrated https://demos.creative-tim.com/vue-notus/?_ga=2.267092621.20072000.1612621955-745088644.1610175099#/admin/dashboard into frontend

To demonstrate how to integrate third party vue frontend into Laravel project.

Currently, testable path:
- ***/admin/dashboard***


# Tutorial & Things to Take Care
### public/..
For standalone vue project, the assets file like image is put in src/assets, 
In Laravel assets file is put in public folder. (thus, can access through url)

### Resources/css   OR Resources/scss 
Any css file in vue project need to put in resources/css or resources/scss, and use app.css / app.scss to important

### Resources/js
Components and vue related files can put in resources/js,
In Laravel: suggested directory structure are:
**resources/js/Pages** (all pages, may have custom components)
**resources/js/Components** (global components)
**resources/js/Layouts** (layouts such as Admin Dashboard Layout, User Dashboard Layout)

### Package.json
Need to manual validate and copy required pacakge from vue project to Laravel.

