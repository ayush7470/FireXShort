# FireXShort
A URL shortner
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FireXShort - Premium URL Shortener</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary: #ff6b35;
            --secondary: #004e89;
            --dark: #292929;
            --light: #f7f7f7;
            --success: #2ecc71;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--primary);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--primary);
        }
        
        .hero {
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .hero p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 40px;
            color: var(--dark);
        }
        
        .shortener-box {
            background-color: white;
            border-radius: 10px;
            padding: 40px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            margin: 0 auto;
        }
        
        .input-group {
            display: flex;
            margin-bottom: 20px;
        }
        
        .input-group input {
            flex: 1;
            padding: 15px;
            border: 2px solid #ddd;
            border-radius: 5px 0 0 5px;
            font-size: 16px;
            outline: none;
            transition: border-color 0.3s;
        }
        
        .input-group input:focus {
            border-color: var(--primary);
        }
        
        .input-group button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 0 25px;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .input-group button:hover {
            background-color: #e05a2b;
        }
        
        .result {
            display: none;
            margin-top: 20px;
            padding: 15px;
            background-color: #f0f8ff;
            border-radius: 5px;
            border-left: 4px solid var(--primary);
        }
        
        .result.show {
            display: block;
        }
        
        .result p {
            margin-bottom: 10px;
        }
        
        .result a {
            color: var(--primary);
            font-weight: 600;
            word-break: break-all;
            text-decoration: none;
        }
        
        .result a:hover {
            text-decoration: underline;
        }
        
        .copy-btn {
            background-color: var(--secondary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            margin-left: 10px;
            transition: background-color 0.3s;
        }
        
        .copy-btn:hover {
            background-color: #003b6b;
        }
        
        .copy-btn.copied {
            background-color: var(--success);
        }
        
        .features {
            padding: 80px 0;
            background-color: white;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 36px;
            color: var(--secondary);
            margin-bottom: 15px;
        }
        
        .section-title p {
            max-width: 700px;
            margin: 0 auto;
            color: #666;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background-color: var(--light);
            border-radius: 10px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
        }
        
        .feature-icon {
            font-size: 40px;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            font-size: 22px;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .feature-card p {
            color: #666;
        }
        
        .about {
            padding: 80px 0;
            background-color: var(--light);
        }
        
        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .about-content h2 {
            font-size: 36px;
            color: var(--secondary);
            margin-bottom: 20px;
        }
        
        .about-content p {
            margin-bottom: 20px;
            color: #555;
        }
        
        footer {
            background-color: var(--dark);
            color: white;
            padding: 40px 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .footer-logo {
            font-size: 24px;
            font-weight: 700;
            color: white;
            margin-bottom: 20px;
            text-decoration: none;
        }
        
        .footer-links {
            display: flex;
            margin-bottom: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .footer-links a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: var(--primary);
        }
        
        .social-icons {
            margin-bottom: 20px;
        }
        
        .social-icons a {
            color: white;
            font-size: 20px;
            margin: 0 10px;
            transition: color 0.3s;
        }
        
        .social-icons a:hover {
            color: var(--primary);
        }
        
        .copyright {
            color: #aaa;
            font-size: 14px;
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }
            
            nav ul {
                margin-top: 20px;
            }
            
            nav ul li {
                margin: 0 10px;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .input-group {
                flex-direction: column;
            }
            
            .input-group input {
                border-radius: 5px;
                margin-bottom: 10px;
            }
            
            .input-group button {
                border-radius: 5px;
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">
                    <i class="fas fa-fire"></i>
                    FireXShort
                </a>
                <nav>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#">API</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
    
    <section class="hero">
        <div class="container">
            <h1>Shorten Your Links with FireXShort</h1>
            <p>Create short, memorable links in seconds. Track clicks and grow your brand with our powerful URL shortener.</p>
            
            <div class="shortener-box">
                <div class="input-group">
                    <input type="url" id="url-input" placeholder="Paste your long URL here..." required>
                    <button id="shorten-btn">Shorten</button>
                </div>
                
                <div class="result" id="result">
                    <p>Your shortened URL:</p>
                    <a href="#" id="short-url" target="_blank"></a>
                    <button class="copy-btn" id="copy-btn">Copy</button>
                </div>
            </div>
        </div>
    </section>
    
    <section class="features" id="features">
        <div class="container">
            <div class="section-title">
                <h2>Powerful Features</h2>
                <p>FireXShort offers everything you need to create, manage, and track your shortened URLs</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-tachometer-alt"></i>
                    </div>
                    <h3>Lightning Fast</h3>
                    <p>Our servers deliver your shortened URLs instantly, ensuring minimal latency for your users.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Analytics</h3>
                    <p>Track clicks, geographic locations, and referral sources to understand your audience better.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-lock"></i>
                    </div>
                    <h3>Secure Links</h3>
                    <p>All links are encrypted and protected against spam and malicious activities.</p>
                </div>
            </div>
        </div>
    </section>
    
    <section class="about" id="about">
        <div class="container">
            <div class="about-content">
                <h2>About FireXShort URL Shortener</h2>
                <p>FireXShort is a premium URL shortening service designed to help businesses and individuals create memorable, trackable links that drive engagement and growth.</p>
                <p>Our platform combines cutting-edge technology with an intuitive interface, making it easy for anyone to shorten links while providing powerful analytics for marketers and developers.</p>
                <p>Whether you're sharing links on social media, in emails, or in print materials, FireXShort ensures your audience gets where they need to go quickly and securely.</p>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <a href="#" class="footer-logo">
                    <i class="fas fa-fire"></i>
                    FireXShort
                </a>
                
                <div class="footer-links">
                    <a href="#">Home</a>
                    <a href="#features">Features</a>
                    <a href="#about">About</a>
                    <a href="#">API</a>
                    <a href="#">Privacy</a>
                    <a href="#">Terms</a>
                </div>
                
                <div class="social-icons">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                </div>
                
                <p class="copyright">&copy; 2023 FireXShort. All rights reserved.</p>
            </div>
        </div>
    </footer>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const shortenBtn = document.getElementById('shorten-btn');
            const urlInput = document.getElementById('url-input');
            const resultDiv = document.getElementById('result');
            const shortUrl = document.getElementById('short-url');
            const copyBtn = document.getElementById('copy-btn');
            
            // Function to validate URL
            function isValidUrl(url) {
                try {
                    new URL(url);
                    return true;
                } catch (e) {
                    return false;
                }
            }
            
            // Function to add http:// if missing
            function normalizeUrl(url) {
                if (!url.match(/^https?:\/\//)) {
                    return 'http://' + url;
                }
                return url;
            }
            
            shortenBtn.addEventListener('click', function() {
                let longUrl = urlInput.value.trim();
                
                if (!longUrl) {
                    alert('Please enter a URL to shorten');
                    return;
                }
                
                // Normalize URL
                longUrl = normalizeUrl(longUrl);
                
                // Validate URL
                if (!isValidUrl(longUrl)) {
                    alert('Please enter a valid URL (e.g., https://example.com)');
                    return;
                }
                
                // In a real application, you would send this to your backend
                // For demo purposes, we'll simulate a response
                setTimeout(() => {
                    // Generate a random short code
                    const shortCode = Math.random().toString(36).substring(2, 8);
                    const shortenedUrl = `https://firexshort.com/${shortCode}`;
                    
                    // Store the mapping in localStorage for demo purposes
                    localStorage.setItem(shortenedUrl, longUrl);
                    
                    shortUrl.textContent = shortenedUrl;
                    shortUrl.href = longUrl; // Link to original URL
                    resultDiv.classList.add('show');
                    
                    // Scroll to the result
                    resultDiv.scrollIntoView({ behavior: 'smooth', block: 'center' });
                }, 800);
            });
            
            // Handle click on shortened links (for demo purposes)
            shortUrl.addEventListener('click', function(e) {
                const storedUrl = localStorage.getItem(this.textContent);
                if (storedUrl) {
                    // In a real app, this would be handled by your backend
                    // For demo, we'll just confirm navigation
                    if (!confirm(`This demo link would redirect to: ${storedUrl}\n\nContinue?`)) {
                        e.preventDefault();
                    }
                }
            });
            
            copyBtn.addEventListener('click', function() {
                const textToCopy = shortUrl.textContent;
                
                navigator.clipboard.writeText(textToCopy).then(() => {
                    copyBtn.textContent = 'Copied!';
                    copyBtn.classList.add('copied');
                    setTimeout(() => {
                        copyBtn.textContent = 'Copy';
                        copyBtn.classList.remove('copied');
                    }, 2000);
                }).catch(err => {
                    console.error('Failed to copy: ', err);
                    // Fallback for browsers that don't support clipboard API
                    const textArea = document.createElement('textarea');
                    textArea.value = textToCopy;
                    document.body.appendChild(textArea);
                    textArea.select();
                    try {
                        document.execCommand('copy');
                        copyBtn.textContent = 'Copied!';
                        copyBtn.classList.add('copied');
                        setTimeout(() => {
                            copyBtn.textContent = 'Copy';
                            copyBtn.classList.remove('copied');
                        }, 2000);
                    } catch (err) {
                        console.error('Fallback copy failed: ', err);
                        alert('Failed to copy URL. Please try again or copy manually.');
                    }
                    document.body.removeChild(textArea);
                });
            });
        });
    </script>
</body>
</html>
