# Project Responsive Web Design using Bootstrap
# Date:22/12/2025
# AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

## Step 5:
Create a HTML file and include the needed Bootstrap components.

## Step 6:
Publish the website in the LocalHost.

# PROGRAM :

views.py
from django.shortcuts import render
def pharm(request):
    return render(request, 'pharm.html')
urls.py
from django.contrib import admin
from django.urls import path
from pharmapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.pharm, name='pharm')
]
pharm.html
{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>HealthFirst Pharmacy</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

    <style>
        body {
            font-family: 'Segoe UI', sans-serif;
            background: #eef6f9;
            margin: 0;
            color: #2c3e50;
        }

        .navbar {
            background-color: #ffffff;
            border-bottom: 1px solid #dde5ea;
            box-shadow: 0 4px 14px rgba(0,0,0,0.08);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar-brand {
            font-weight: 700;
            color: #0d6efd !important;
            font-size: 22px;
        }

        .nav-link {
            color: #333;
            font-weight: 500;
        }

        .nav-link:hover {
            color: #0d6efd;
        }


        .hero {
            height: 260px;
            background: linear-gradient(135deg, #0d6efd, #4facfe);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
        }

        .hero h2 {
            font-size: 34px;
            font-weight: 700;
        }

        .hero p {
            font-size: 16px;
            opacity: 0.95;
            margin-bottom: 15px;
        }

        .hero button:hover {
            transform: scale(1.05);
        }

       
        .product-card {
            border: none;
            border-radius: 16px;
            overflow: hidden;
            background-color: #ffffff;
            transition: 0.3s;
            box-shadow: 0 6px 18px rgba(0,0,0,0.12);
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 32px rgba(13,110,253,0.35);
        }

        .product-card img {
            width: 100%;
            height: 150px;
            object-fit: cover;
        }

        .badge-cat {
            position: absolute;
            top: 10px;
            left: 10px;
            background: #0d6efd;
            color: white;
            padding: 4px 10px;
            font-size: 11px;
            border-radius: 20px;
        }

        .card-body {
            text-align: center;
            padding: 14px 10px;
        }

        .card-body b {
            font-size: 15px;
            display: block;
        }

        .card-body p {
            font-size: 12px;
            color: #6c757d;
            margin: 0;
        }

       
        footer {
            background-color: #0d6efd;
            color: white;
            text-align: center;
            padding: 14px;
            margin-top: 40px;
            font-size: 14px;
        }
    </style>
</head>

<body>

<nav class="navbar navbar-expand-lg px-4">
    <a class="navbar-brand" href="#">HealthFirst Pharmacy</a>

    <ul class="navbar-nav flex-row ms-4">
        <li class="nav-item me-3"><a class="nav-link" href="#">Medicines</a></li>
        <li class="nav-item me-3"><a class="nav-link" href="#">Medical Devices</a></li>
        <li class="nav-item me-3"><a class="nav-link" href="#">Prescription</a></li>
        <li class="nav-item me-3"><a class="nav-link" href="#">Contact</a></li>
    </ul>

    <form class="d-flex ms-auto">
        <input class="form-control me-2" type="search" placeholder="Search products">
        <button class="btn btn-primary">Search</button>
    </form>
</nav>


<section class="hero">
    <h2>Because Your Health Matters</h2>
    <p>Trusted medicines • Modern care • Everyday wellness</p>
    <button class="btn btn-light px-4">View Products</button>
</section>


<div class="container my-5">
    <h4 class="mb-4 text-center fw-bold">Popular Pharmacy Products</h4>

    <div class="row row-cols-1 row-cols-md-3 row-cols-lg-6 g-4">

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">Monitoring</span>
                <img src="{% static 'thermo.jpg' %}">
                <div class="card-body">
                    <b>Digital Thermometer</b>
                    <p>Body Temperature</p>
                </div>
            </div>
        </div>

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">Respiratory</span>
                <img src="{% static 'oxi.jpg' %}">
                <div class="card-body">
                    <b>Pulse Oximeter</b>
                    <p>Oxygen Level</p>
                </div>
            </div>
        </div>

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">Therapy</span>
                <img src="{% static 'neb.jpg' %}">
                <div class="card-body">
                    <b>Nebulizer Machine</b>
                    <p>Asthma Care</p>
                </div>
            </div>
        </div>

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">Hygiene</span>
                <img src="{% static 'hs.jpg' %}">
                <div class="card-body">
                    <b>Hand Sanitizer</b>
                    <p>Germ Protection</p>
                </div>
            </div>
        </div>

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">First Aid</span>
                <img src="{% static 'fa.jpg' %}">
                <div class="card-body">
                    <b>First Aid Kit</b>
                    <p>Emergency</p>
                </div>
            </div>
        </div>

        <div class="col">
            <div class="card product-card">
                <span class="badge-cat">medicine</span>
                <img src="{% static 'tab.jpg' %}">
                <div class="card-body">
                    <b>pain killers</b>
                    <p>Medical Use</p>
                </div>
            </div>
        </div>

    </div>
</div>


<footer>
    © 2025 HealthFirst Pharmacy | Caring Beyond Medicine 
</footer>
</body>
</html>

# OUTPUT:
<img width="1891" height="914" alt="image" src="https://github.com/user-attachments/assets/ab8c07be-5523-4d8c-be7b-36e465d0e379" />

# RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
