<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بلو تيك | شركة تصميم مواقع احترافية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #0066ff;
            --primary-dark: #003366;
            --secondary-color: #000000;
            --accent-color: #00ccff;
            --text-color: #ffffff;
            --text-secondary: #cccccc;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--secondary-color);
            color: var(--text-color);
            overflow-x: hidden;
            scroll-behavior: smooth;
            line-height: 1.6;
        }
        
        /* شريط التنقل */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.5s ease;
            border-bottom: 1px solid rgba(0, 102, 255, 0.3);
        }
        
        .navbar.scrolled {
            padding: 15px 5%;
            background: rgba(0, 0, 0, 0.95);
            box-shadow: 0 10px 30px rgba(0, 102, 255, 0.1);
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo img {
            height: 40px;
            margin-left: 10px;
            filter: drop-shadow(0 0 5px var(--primary-color));
        }
        
        .logo h1 {
            font-size: 1.8rem;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin: 0 15px;
            position: relative;
        }
        
        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 1.1rem;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 5px 0;
        }
        
        .nav-links a:hover {
            color: var(--primary-color);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            transition: width 0.3s ease;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .menu-toggle {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
            color: var(--text-color);
        }
        
        /* القسم الرئيسي */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 10%;
            position: relative;
            overflow: hidden;
            margin-top: 80px;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 70% 50%, rgba(0, 102, 255, 0.1) 0%, transparent 50%);
            z-index: -1;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: textGlow 3s infinite alternate;
        }
        
        @keyframes textGlow {
            0% {
                text-shadow: 0 0 10px rgba(0, 102, 255, 0.5);
            }
            100% {
                text-shadow: 0 0 20px rgba(0, 102, 255, 0.8), 0 0 30px rgba(0, 204, 255, 0.5);
            }
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: var(--text-secondary);
            line-height: 1.6;
        }
        
        .cta-button {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 102, 255, 0.4);
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        
        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 102, 255, 0.6);
        }
        
        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        .cta-button:hover::before {
            left: 100%;
        }
        
        .hero-image {
            position: absolute;
            right: 10%;
            width: 500px;
            height: 500px;
            background: url('https://cdn.dribbble.com/users/1787323/screenshots/14139382/media/042a19a5f5c98a5001a3c8f9d5a6b925.png') no-repeat center center;
            background-size: contain;
            filter: drop-shadow(0 0 20px rgba(0, 102, 255, 0.5));
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        /* خدماتنا */
        .services {
            padding: 100px 10%;
            background: linear-gradient(to bottom, rgba(0, 0, 0, 0.9), rgba(0, 0, 0, 0.95));
            position: relative;
        }
        
        .services::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(0,102,255,0.03)" d="M0,0 L100,0 L100,100 Q50,80 0,100 L0,0 Z"></path></svg>');
            background-size: 100% 100%;
            background-repeat: no-repeat;
            z-index: -1;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--text-color);
            position: relative;
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
        }
        
        .section-title p {
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.6;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.5s ease;
            border: 1px solid rgba(0, 102, 255, 0.1);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 102, 255, 0.2);
            border-color: rgba(0, 102, 255, 0.3);
        }
        
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 102, 255, 0.05) 0%, transparent 100%);
            z-index: -1;
        }
        
        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--primary-color);
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--text-color);
        }
        
        .service-card p {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .service-link {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 500;
            display: flex;
            align-items: center;
            transition: all 0.3s ease;
        }
        
        .service-link i {
            margin-right: 5px;
            transition: all 0.3s ease;
        }
        
        .service-link:hover {
            color: var(--accent-color);
        }
        
        .service-link:hover i {
            transform: translateX(5px);
        }
        
        /* أعمالنا */
        .portfolio {
            padding: 100px 10%;
            background-color: var(--secondary-color);
            position: relative;
        }
        
        .portfolio::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(0,0,0,0.9)" d="M0,0 L100,0 L100,100 Q50,80 0,100 L0,0 Z"></path></svg>');
            background-size: 100% 100%;
            background-repeat: no-repeat;
            z-index: -1;
        }
        
        .portfolio-filter {
            display: flex;
            justify-content: center;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }
        
        .filter-btn {
            padding: 10px 20px;
            margin: 0 10px;
            background: transparent;
            border: none;
            color: var(--text-secondary);
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .filter-btn.active, .filter-btn:hover {
            color: var(--primary-color);
        }
        
        .filter-btn::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            transition: width 0.3s ease;
        }
        
        .filter-btn.active::after, .filter-btn:hover::after {
            width: 100%;
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }
        
        .portfolio-item {
            position: relative;
            border-radius: 15px;
            overflow: hidden;
            height: 250px;
            transition: all 0.5s ease;
        }
        
        .portfolio-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: all 0.5s ease;
        }
        
        .portfolio-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(0, 51, 102, 0.8), rgba(0, 102, 255, 0.8));
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: all 0.5s ease;
            padding: 20px;
            text-align: center;
        }
        
        .portfolio-item:hover .portfolio-overlay {
            opacity: 1;
        }
        
        .portfolio-item:hover img {
            transform: scale(1.1);
        }
        
        .portfolio-overlay h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--text-color);
            transform: translateY(20px);
            transition: all 0.5s ease;
        }
        
        .portfolio-overlay p {
            color: var(--text-secondary);
            margin-bottom: 20px;
            transform: translateY(20px);
            transition: all 0.5s ease 0.1s;
        }
        
        .portfolio-overlay a {
            color: var(--text-color);
            font-size: 1.2rem;
            transform: translateY(20px);
            transition: all 0.5s ease 0.2s;
        }
        
        .portfolio-item:hover .portfolio-overlay h3,
        .portfolio-item:hover .portfolio-overlay p,
        .portfolio-item:hover .portfolio-overlay a {
            transform: translateY(0);
        }
        
        /* فريق العمل */
        .team {
            padding: 100px 10%;
            background: linear-gradient(to bottom, rgba(0, 0, 0, 0.95), rgba(0, 0, 0, 0.9));
            position: relative;
        }
        
        .team::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(0,102,255,0.03)" d="M0,0 L100,0 L100,100 Q50,80 0,100 L0,0 Z"></path></svg>');
            background-size: 100% 100%;
            background-repeat: no-repeat;
            z-index: -1;
        }
        
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .team-member {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.5s ease;
            border: 1px solid rgba(0, 102, 255, 0.1);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
        }
        
        .team-member:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 102, 255, 0.2);
            border-color: rgba(0, 102, 255, 0.3);
        }
        
        .member-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 20px;
            overflow: hidden;
            border: 3px solid rgba(0, 102, 255, 0.3);
            position: relative;
        }
        
        .member-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: all 0.5s ease;
        }
        
        .team-member:hover .member-image img {
            transform: scale(1.1);
        }
        
        .member-social {
            position: absolute;
            bottom: -20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            opacity: 0;
            transition: all 0.5s ease;
        }
        
        .team-member:hover .member-social {
            bottom: 10px;
            opacity: 1;
        }
        
        .member-social a {
            width: 35px;
            height: 35px;
            background: var(--primary-dark);
            color: var(--text-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 5px;
            transition: all 0.3s ease;
        }
        
        .member-social a:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        .team-member h3 {
            font-size: 1.5rem;
            margin-bottom: 5px;
            color: var(--text-color);
        }
        
        .team-member p {
            color: var(--primary-color);
            margin-bottom: 15px;
            font-weight: 500;
        }
        
        .team-member .member-desc {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        /* اتصل بنا */
        .contact {
            padding: 100px 10%;
            background-color: var(--secondary-color);
            position: relative;
        }
        
        .contact::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(0,0,0,0.9)" d="M0,0 L100,0 L100,100 Q50,80 0,100 L0,0 Z"></path></svg>');
            background-size: 100% 100%;
            background-repeat: no-repeat;
            z-index: -1;
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }
        
        .contact-info {
            margin-bottom: 40px;
        }
        
        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--text-color);
            position: relative;
            display: inline-block;
        }
        
        .contact-info h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 3px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
        }
        
        .contact-info p {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 30px;
        }
        
        .contact-details {
            margin-bottom: 30px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .contact-item i {
            width: 40px;
            height: 40px;
            background: rgba(0, 102, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 15px;
            color: var(--primary-color);
            font-size: 1.2rem;
        }
        
        .contact-item span {
            color: var(--text-secondary);
        }
        
        .contact-social {
            display: flex;
        }
        
        .contact-social a {
            width: 40px;
            height: 40px;
            background: rgba(0, 102, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
            color: var(--text-color);
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }
        
        .contact-social a:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        .contact-form {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            padding: 30px;
            border: 1px solid rgba(0, 102, 255, 0.1);
            backdrop-filter: blur(5px);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-color);
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(0, 102, 255, 0.3);
            border-radius: 8px;
            color: var(--text-color);
            font-family: 'Tajawal', sans-serif;
            transition: all 0.3s ease;
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 10px rgba(0, 102, 255, 0.3);
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* التذييل */
        .footer {
            background: linear-gradient(to right, var(--primary-dark), var(--secondary-color));
            padding: 50px 10% 20px;
            position: relative;
        }
        
        .footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(0,0,0,0.8)" d="M0,0 L100,0 L100,100 Q50,80 0,100 L0,0 Z"></path></svg>');
            background-size: 100% 100%;
            background-repeat: no-repeat;
            z-index: -1;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-logo {
            margin-bottom: 20px;
        }
        
        .footer-logo img {
            height: 40px;
            filter: drop-shadow(0 0 5px var(--primary-color));
        }
        
        .footer-about p {
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .footer-links h3, .footer-newsletter h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--text-color);
            position: relative;
            display: inline-block;
        }
        
        .footer-links h3::after, .footer-newsletter h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 40px;
            height: 3px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .footer-links a:hover {
            color: var(--primary-color);
            transform: translateX(5px);
        }
        
        .footer-newsletter p {
            color: var(--text-secondary);
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .newsletter-form {
            display: flex;
        }
        
        .newsletter-input {
            flex: 1;
            padding: 12px 15px;
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(0, 102, 255, 0.3);
            border-radius: 8px 0 0 8px;
            color: var(--text-color);
            font-family: 'Tajawal', sans-serif;
        }
        
        .newsletter-input:focus {
            outline: none;
            border-color: var(--primary-color);
        }
        
        .newsletter-btn {
            padding: 0 20px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            color: white;
            border: none;
            border-radius: 0 8px 8px 0;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .newsletter-btn:hover {
            background: linear-gradient(to right, var(--primary-dark), var(--primary-color));
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(0, 102, 255, 0.1);
        }
        
        .footer-bottom p {
            color: var(--text-secondary);
        }
        
        /* تأثيرات عامة */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }
        
        .particle {
            position: absolute;
            background: rgba(0, 102, 255, 0.5);
            border-radius: 50%;
            pointer-events: none;
        }
        
        @keyframes float-up {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
        
        /* التكيف مع الجوال */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .hero-image {
                width: 400px;
                height: 400px;
                right: 5%;
            }
        }
        
        @media (max-width: 768px) {
            .navbar {
                padding: 15px 5%;
            }
            
            .nav-links {
                position: fixed;
                top: 80px;
                right: -100%;
                width: 80%;
                height: calc(100vh - 80px);
                background: rgba(0, 0, 0, 0.95);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 40px;
                transition: all 0.5s ease;
                backdrop-filter: blur(10px);
                border-left: 1px solid rgba(0, 102, 255, 0.3);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .nav-links li {
                margin: 15px 0;
            }
            
            .menu-toggle {
                display: block;
            }
            
            .hero {
                flex-direction: column;
                text-align: center;
                padding-top: 120px;
                height: auto;
                padding-bottom: 80px;
            }
            
            .hero-content {
                max-width: 100%;
                margin-bottom: 50px;
            }
            
            .hero-image {
                position: relative;
                right: auto;
                margin: 0 auto;
                width: 300px;
                height: 300px;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .cta-button {
                padding: 12px 25px;
                font-size: 1rem;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-input {
                border-radius: 8px;
                margin-bottom: 10px;
            }
            
            .newsletter-btn {
                border-radius: 8px;
                padding: 12px;
            }
        }
    </style>
</head>
<body>
    <!-- جسيمات متحركة -->
    <div class="particles" id="particles"></div>
    
    <!-- شريط التنقل -->
    <nav class="navbar">
        <div class="logo">
            <img src="https://via.placeholder.com/40x40/003366/ffffff?text=BT" alt="بلو تيك">
            <h1>بلو تيك</h1>
        </div>
        
        <ul class="nav-links">
            <li><a href="#home">الرئيسية</a></li>
            <li><a href="#services">خدماتنا</a></li>
            <li><a href="#portfolio">أعمالنا</a></li>
            <li><a href="#team">فريقنا</a></li>
            <li><a href="#contact">اتصل بنا</a></li>
        </ul>
        
        <div class="menu-toggle">
            <i class="fas fa-bars"></i>
        </div>
    </nav>
    
    <!-- القسم الرئيسي -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>تصميم مواقع احترافية تلهم عملائك</h1>
            <p>نحن نبتكر حلولًا رقمية مذهلة تساعد عملك على النمو والازدهار في العالم الرقمي. بفضل فريقنا المبدع وأساليبنا الحديثة، نضمن لك موقعًا فريدًا يجذب الزوار ويعزز علامتك التجارية.</p>
            <a href="#contact" class="cta-button">ابدأ مشروعك الآن</a>
        </div>
        
        <div class="hero-image"></div>
    </section>
    
    <!-- خدماتنا -->
    <section class="services" id="services">
        <div class="section-title">
            <h2>خدماتنا</h2>
            <p>نقدم مجموعة شاملة من خدمات تصميم وتطوير المواقع التي تلبي جميع احتياجاتك الرقمية</p>
        </div>
        
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-code"></i>
                </div>
                <h3>تصميم مواقع متكاملة</h3>
                <p>تصميم مواقع احترافية بتقنيات حديثة تتوافق مع جميع الأجهزة وتضمن تجربة مستخدم ممتازة.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-mobile-alt"></i>
                </div>
                <h3>تطبيقات الجوال</h3>
                <p>تطوير تطبيقات جوال مبتكرة لنظامي iOS و Android تعزز تواجدك الرقمي وتصل بعملك إلى جمهور أوسع.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-shopping-cart"></i>
                </div>
                <h3>متاجر إلكترونية</h3>
                <p>إنشاء متاجر إلكترونية متكاملة بكل ما تحتاجه لبدء بيع منتجاتك عبر الإنترنت بسهولة وأمان.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-search-dollar"></i>
                </div>
                <h3>تحسين محركات البحث</h3>
                <p>تحسين موقعك لمحركات البحث لزيادة ظهورك في النتائج الأولى وجذب المزيد من الزوار المؤهلين.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-ad"></i>
                </div>
                <h3>إعلانات ممولة</h3>
                <p>إدارة حملات إعلانية مدروسة على منصات التواصل الاجتماعي ومحركات البحث لزيادة مبيعاتك.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <h3>تحليل البيانات</h3>
                <p>تحليل أداء موقعك وتقديم تقارير مفصلة تساعدك على اتخاذ القرارات الصحيحة لتحسين نتائجك.</p>
                <a href="#" class="service-link">المزيد <i class="fas fa-arrow-left"></i></a>
            </div>
        </div>
    </section>
    
    <!-- أعمالنا -->
    <section class="portfolio" id="portfolio">
        <div class="section-title">
            <h2>أعمالنا</h2>
            <p>بعض المشاريع التي نفخر بها والتي تعكس مستوى احترافيتنا وإبداعنا</p>
        </div>
        
        <div class="portfolio-filter">
            <button class="filter-btn active">الكل</button>
            <button class="filter-btn">مواقع شركات</button>
            <button class="filter-btn">متاجر إلكترونية</button>
            <button class="filter-btn">تطبيقات ويب</button>
        </div>
        
        <div class="portfolio-grid">
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/003366/ffffff?text=Project+1" alt="مشروع 1">
                <div class="portfolio-overlay">
                    <h3>موقع شركة تقنية</h3>
                    <p>تصميم حديث ومتجاوب لشركة تقنية متخصصة في حلول الأعمال</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/0066ff/ffffff?text=Project+2" alt="مشروع 2">
                <div class="portfolio-overlay">
                    <h3>متجر إلكتروني</h3>
                    <p>متجر إلكتروني متكامل بخصائص دفع وتوصيل متقدمة</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/00ccff/ffffff?text=Project+3" alt="مشروع 3">
                <div class="portfolio-overlay">
                    <h3>منصة تعليمية</h3>
                    <p>نظام إدارة تعلم متكامل مع خاصية البث المباشر</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/003366/ffffff?text=Project+4" alt="مشروع 4">
                <div class="portfolio-overlay">
                    <h3>تطبيق ويب</h3>
                    <p>تطبيق ويب لإدارة المشاريع بخصائص تعاونية متقدمة</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/0066ff/ffffff?text=Project+5" alt="مشروع 5">
                <div class="portfolio-overlay">
                    <h3>موقع سياحي</h3>
                    <p>منصة سياحية تفاعلية مع نظام حجوزات متكامل</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
            
            <div class="portfolio-item">
                <img src="https://via.placeholder.com/600x400/00ccff/ffffff?text=Project+6" alt="مشروع 6">
                <div class="portfolio-overlay">
                    <h3>بوابة حكومية</h3>
                    <p>بوابة إلكترونية متكاملة لجهة حكومية بخاصية الخدمات الذاتية</p>
                    <a href="#"><i class="fas fa-external-link-alt"></i></a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- فريق العمل -->
    <section class="team" id="team">
        <div class="section-title">
            <h2>فريقنا</h2>
            <p>فريق من المحترفين المبدعين الذين يعملون بجد لتحقيق رؤيتك</p>
        </div>
        
        <div class="team-grid">
            <div class="team-member">
                <div class="member-image">
                    <img src="https://via.placeholder.com/300x300/003366/ffffff?text=Ahmed" alt="أحمد">
                    <div class="member-social">
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                    </div>
                </div>
                <h3>أحمد محمد</h3>
                <p>مدير تقني</p>
                <p class="member-desc">خبرة أكثر من 10 سنوات في تطوير الويب وإدارة المشاريع التقنية</p>
            </div>
            
            <div class="team-member">
                <div class="member-image">
                    <img src="https://via.placeholder.com/300x300/0066ff/ffffff?text=Sara" alt="سارة">
                    <div class="member-social">
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-dribbble"></i></a>
                    </div>
                </div>
                <h3>سارة عبدالله</h3>
                <p>مصممة واجهات</p>
                <p class="member-desc">متخصصة في تصميم تجارب المستخدم والواجهات التفاعلية</p>
            </div>
            
            <div class="team-member">
                <div class="member-image">
                    <img src="https://via.placeholder.com/300x300/00ccff/ffffff?text=Khalid" alt="خالد">
                    <div class="member-social">
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-stack-overflow"></i></a>
                    </div>
                </div>
                <h3>خالد علي</h3>
                <p>مطور ويب</p>
                <p class="member-desc">خبير في تطوير تطبيقات الويب باستخدام أحدث التقنيات</p>
            </div>
            
            <div class="team-member">
                <div class="member-image">
                    <img src="https://via.placeholder.com/300x300/003366/ffffff?text=Noura" alt="نورة">
                    <div class="member-social">
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-linkedin"></i></a>
                        <a href="#"><i class="fab fa-behance"></i></a>
                    </div>
                </div>
                <h3>نورة سعيد</h3>
                <p>مسوقة رقمية</p>
                <p class="member-desc">خبيرة في التسويق الرقمي وتحسين محركات البحث</p>
            </div>
        </div>
    </section>
    
    <!-- اتصل بنا -->
    <section class="contact" id="contact">
        <div class="section-title">
            <h2>اتصل بنا</h2>
            <p>نحن هنا لمساعدتك في أي استفسار أو لبدء مشروعك الجديد</p>
        </div>
        
        <div class="contact-container">
            <div class="contact-info">
                <h3>تواصل معنا</h3>
                <p>لديك استفسار أو ترغب في مناقشة مشروعك؟ لا تتردد في التواصل معنا عبر أي من الوسائل التالية:</p>
                
                <div class="contact-details">
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>الرياض، المملكة العربية السعودية</span>
                    </div>
                    
                    <div class="contact-item">
                        <i class="fas fa-phone-alt"></i>
                        <span>+966 12 345 6789</span>
                    </div>
                    
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <span>info@bluetech.com</span>
                    </div>
                </div>
                
                <div class="contact-social">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </div>
            </div>
            
            <div class="contact-form">
    <form action="send-email.php" method="POST">
        <div class="form-group">
            <label for="name">الاسم الكامل</label>
            <input type="text" id="name" name="name" class="form-control" required>
        </div>
        
        <div class="form-group">
            <label for="email">البريد الإلكتروني</label>
            <input type="email" id="email" name="email" class="form-control" required>
        </div>
        
        <div class="form-group">
            <label for="phone">رقم الهاتف</label>
            <input type="tel" id="phone" name="phone" class="form-control">
        </div>
        
        <div class="form-group">
            <label for="message">الرسالة</label>
            <textarea id="message" name="message" class="form-control" required></textarea>
        </div>
        
        <button type="submit" class="cta-button">إرسال الرسالة</button>
    </form>
</div>
        </div>
    </section>
    
    <!-- التذييل -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-about">
                <div class="footer-logo">
                    <img src="https://via.placeholder.com/40x40/003366/ffffff?text=BT" alt="بلو تيك">
                </div>
                <p>شركة متخصصة في تقديم حلول الويب والتطبيقات الذكية التي تساعد أعمالك على النمو والازدهار في العالم الرقمي.</p>
            </div>
            
            <div class="footer-links">
                <h3>روابط سريعة</h3>
                <ul>
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#services">خدماتنا</a></li>
                    <li><a href="#portfolio">أعمالنا</a></li>
                    <li><a href="#team">فريقنا</a></li>
                    <li><a href="#contact">اتصل بنا</a></li>
                </ul>
            </div>
            
            <div class="footer-links">
                <h3>خدماتنا</h3>
                <ul>
                    <li><a href="#">تصميم مواقع</a></li>
                    <li><a href="#">تطبيقات الجوال</a></li>
                    <li><a href="#">متاجر إلكترونية</a></li>
                    <li><a href="#">تحسين محركات البحث</a></li>
                    <li><a href="#">إعلانات ممولة</a></li>
                </ul>
            </div>
            
            <div class="footer-newsletter">
                <h3>النشرة البريدية</h3>
                <p>اشترك في نشرتنا البريدية لتصلك آخر أخبارنا وعروضنا الخاصة.</p>
                <form class="newsletter-form">
                    <input type="email" class="newsletter-input" placeholder="بريدك الإلكتروني" required>
                    <button type="submit" class="newsletter-btn"><i class="fas fa-paper-plane"></i></button>
                </form>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2023 بلو تيك. جميع الحقوق محفوظة.</p>
        </div>
    </footer>
    
    <script>
        // تأثير الجسيمات
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // تحديد حجم عشوائي للجسيم
                const size = Math.random() * 5 + 2;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                // تحديد موقع عشوائي للجسيم
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                
                // تحديد مدة الحركة العشوائية
                const duration = Math.random() * 20 + 10;
                particle.style.animation = `float-up ${duration}s linear infinite`;
                
                // تحديد تأخير عشوائي
                particle.style.animationDelay = `${Math.random() * 10}s`;
                
                // تحديد شفافية عشوائية
                particle.style.opacity = Math.random() * 0.5 + 0.1;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // شريط التنقل عند التمرير
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });
        
        // قائمة الجوال
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');
        
        menuToggle.addEventListener('click', function() {
            navLinks.classList.toggle('active');
            menuToggle.classList.toggle('fa-times');
        });
        
        // إغلاق القائمة عند النقر على رابط
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', function() {
                navLinks.classList.remove('active');
                menuToggle.classList.remove('fa-times');
            });
        });
        
        // تصفية أعمالنا
        const filterButtons = document.querySelectorAll('.filter-btn');
        
        filterButtons.forEach(button => {
            button.addEventListener('click', function() {
                // إزالة الفعال من جميع الأزرار
                filterButtons.forEach(btn => btn.classList.remove('active'));
                
                // إضافة الفعال للزر المحدد
                this.classList.add('active');
                
                // هنا يمكنك إضافة كود تصفية المشاريع حسب الفئة
            });
        });
        
        // تهيئة الجسيمات عند تحميل الصفحة
        window.addEventListener('load', createParticles);
    </script>
</body>
</html>
