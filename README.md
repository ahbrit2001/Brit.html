# Brit.html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>شمس الروايات - أكبر مكتبة روايات عربية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }

        :root {
            --primary: #8e44ad;
            --secondary: #9b59b6;
            --accent: #3498db;
            --light: #f5f5f5;
            --dark: #2c3e50;
            --gray: #7f8c8d;
            --success: #27ae60;
        }

        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
            direction: rtl;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo i {
            margin-left: 10px;
            color: #f1c40f;
        }

        .search-bar {
            flex: 1;
            max-width: 500px;
            margin: 0 20px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 12px 20px;
            border-radius: 30px;
            border: none;
            font-size: 1rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .search-bar button {
            position: absolute;
            left: 10px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            color: var(--primary);
            font-size: 1.2rem;
            cursor: pointer;
        }

        .user-actions a {
            color: white;
            margin-left: 15px;
            font-size: 1.2rem;
            text-decoration: none;
        }

        /* Navigation */
        nav {
            background-color: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            padding: 10px 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
        }

        .main-nav {
            display: flex;
            list-style: none;
        }

        .main-nav li {
            margin-left: 20px;
        }

        .main-nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            padding: 8px 0;
            position: relative;
            transition: color 0.3s;
        }

        .main-nav a:hover {
            color: var(--primary);
        }

        .main-nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .main-nav a:hover::after {
            width: 100%;
        }

        .category-nav {
            display: flex;
            list-style: none;
        }

        .category-nav li {
            margin-right: 15px;
        }

        .category-nav a {
            text-decoration: none;
            color: var(--gray);
            font-size: 0.9rem;
        }

        .category-nav a:hover {
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1507842217343-583bb7270b66?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1153&q=80');
            background-size: cover;
            background-position: center;
            height: 400px;
            display: flex;
            align-items: center;
            color: white;
            margin-bottom: 40px;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: var(--primary);
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Sections */
        section {
            margin-bottom: 50px;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary);
        }

        .section-title {
            font-size: 1.8rem;
            color: var(--dark);
        }

        .view-all {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
        }

        .view-all:hover {
            text-decoration: underline;
        }

        /* Books Grid */
        .books-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 25px;
        }

        .book-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .book-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .book-cover {
            height: 250px;
            overflow: hidden;
        }

        .book-cover img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .book-card:hover .book-cover img {
            transform: scale(1.05);
        }

        .book-info {
            padding: 15px;
        }

        .book-title {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 5px;
            color: var(--dark);
        }

        .book-author {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 10px;
        }

        .book-meta {
            display: flex;
            justify-content: space-between;
            color: var(--gray);
            font-size: 0.85rem;
        }

        .rating {
            color: #f1c40f;
        }

        .completed {
            color: var(--success);
            font-weight: 600;
        }

        /* Categories Section */
        .categories {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
        }

        .category-card {
            background: white;
            border-radius: 10px;
            padding: 20px 15px;
            text-align: center;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.08);
            transition: all 0.3s;
            cursor: pointer;
        }

        .category-card:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-5px);
        }

        .category-card i {
            font-size: 2rem;
            margin-bottom: 10px;
            display: block;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 50px 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 50px;
            height: 2px;
            background: var(--primary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #bdc3c7;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            text-decoration: none;
            transition: background 0.3s;
        }

        .social-links a:hover {
            background: var(--primary);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bdc3c7;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-bar {
                margin: 10px 0;
                max-width: 100%;
            }
            
            .nav-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .main-nav {
                flex-wrap: wrap;
            }
            
            .hero {
                height: 300px;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .books-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }

        @media (max-width: 480px) {
            .hero {
                height: 250px;
            }
            
            .hero h1 {
                font-size: 1.7rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .books-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-sun"></i>
                <span>شمس الروايات</span>
            </div>
            
            <div class="search-bar">
                <input type="text" placeholder="ابحث عن رواية أو كاتب...">
                <button><i class="fas fa-search"></i></button>
            </div>
            
            <div class="user-actions">
                <a href="#"><i class="fas fa-user"></i></a>
                <a href="#"><i class="fas fa-bell"></i></a>
                <a href="#"><i class="fas fa-bookmark"></i></a>
            </div>
        </div>
    </header>
    
    <!-- Navigation -->
    <nav>
        <div class="container nav-container">
            <ul class="main-nav">
                <li><a href="#">الرئيسية</a></li>
                <li><a href="#">الروايات</a></li>
                <li><a href="#">الكتّاب</a></li>
                <li><a href="#">المكتبة</a></li>
                <li><a href="#">المفضلة</a></li>
                <li><a href="#">المسابقات</a></li>
                <li><a href="#">المدونة</a></li>
            </ul>
            
            <ul class="category-nav">
                <li><a href="#">رومانسي</a></li>
                <li><a href="#">خيال علمي</a></li>
                <li><a href="#">تاريخي</a></li>
                <li><a href="#">غموض</a></li>
                <li><a href="#">فانتازيا</a></li>
            </ul>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>استمتع بأفضل الروايات العربية</h1>
                <p>اكتشف آلاف الروايات المثيرة من أفضل الكتاب العرب في مختلف التصنيفات والأنواع الأدبية</p>
                <a href="#" class="btn">استكشف المكتبة</a>
            </div>
        </div>
    </section>
    
    <!-- Main Content -->
    <main class="container">
        <!-- Latest Novels Section -->
        <section>
            <div class="section-header">
                <h2 class="section-title">أحدث الروايات</h2>
                <a href="#" class="view-all">عرض الكل</a>
            </div>
            
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1544947950-fa07a98d237f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80" alt="رواية قلب الليل">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">قلب الليل</h3>
                        <p class="book-author">سارة أحمد</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.7
                            </span>
                            <span>الفصل 24</span>
                        </div>
                    </div>
                </div>
                
                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1495640388908-05fa85288e61?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="رواية ظلال الماضي">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">ظلال الماضي</h3>
                        <p class="book-author">محمد حسن</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.9
                            </span>
                            <span>الفصل 18</span>
                        </div>
                    </div>
                </div>
                
                <!-- Book 3 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1506880018603-83d5b814b5a6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1074&q=80" alt="رواية أسرار القصر">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">أسرار القصر</h3>
                        <p class="book-author">نورا خالد</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.8
                            </span>
                            <span class="completed">مكتملة</span>
                        </div>
                    </div>
                </div>
                
                <!-- Book 4 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1531346878377-a5be20888e57?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80" alt="رواية طريق النور">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">طريق النور</h3>
                        <p class="book-author">عمر فاروق</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.6
                            </span>
                            <span>الفصل 32</span>
                        </div>
                    </div>
                </div>
                
                <!-- Book 5 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1629992101753-56d196c8aabb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="رواية زهرة الصحراء">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">زهرة الصحراء</h3>
                        <p class="book-author">لمى سامي</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.5
                            </span>
                            <span>الفصل 15</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Most Popular Section -->
        <section>
            <div class="section-header">
                <h2 class="section-title">الأكثر شعبية</h2>
                <a href="#" class="view-all">عرض الكل</a>
            </div>
            
            <div class="books-grid">
                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1532012197267-da84d127e765?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80" alt="رواية عرش الأقدار">
                    </div>
                    <div class="book-info">
                        <h3 class="book-title">عرش الأقدار</h3>
                        <p class="book-author">فارس عبدالله</p>
                        <div class="book-meta">
                            <span class="rating">
                                <i class="fas fa-star"></i> 4.9
                            </span>
                            <span>الفصل 45</span>
                        </div>
                    </div>
                </div>
                
                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-cover">
                        <img src="https://images.unsplash.com/photo-1512820790803-83ca734da794?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1198&q=80" alt="رواية أحلام اليقظة">
                    </div>
                    <div class="boo
