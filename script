document.addEventListener('DOMContentLoaded', function() {
    // Mobile menu toggle
    const mobileMenuBtn = document.querySelector('.mobile-menu');
    const navMenu = document.querySelector('nav ul');
    
    mobileMenuBtn.addEventListener('click', function() {
        navMenu.classList.toggle('active');
        this.querySelector('i').classList.toggle('fa-times');
        this.querySelector('i').classList.toggle('fa-bars');
    });
    
    // Smooth scrolling for navigation links
    document.querySelectorAll('nav a').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            
            const targetId = this.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            
            window.scrollTo({
                top: targetElement.offsetTop - 80,
                behavior: 'smooth'
            });
            
            // Close mobile menu if open
            if (navMenu.classList.contains('active')) {
                navMenu.classList.remove('active');
                mobileMenuBtn.querySelector('i').classList.remove('fa-times');
                mobileMenuBtn.querySelector('i').classList.add('fa-bars');
            }
        });
    });
    
    // Header scroll effect
    window.addEventListener('scroll', function() {
        const header = document.querySelector('header');
        if (window.scrollY > 100) {
            header.classList.add('scrolled');
        } else {
            header.classList.remove('scrolled');
        }
    });
    
    // Contact form submission
    const contactForm = document.getElementById('contactForm');
    if (contactForm) {
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // Here you would typically send the form data to a server
            // For this example, we'll just show an alert
            alert(`Thank you, ${name}! Your message has been received. We'll get back to you soon at ${email}.`);
            
            // Reset the form
            contactForm.reset();
        });
    }
    
    // Gallery lightbox (would need additional HTML/CSS for full implementation)
    const galleryItems = document.querySelectorAll('.gallery-item');
    galleryItems.forEach(item => {
        item.addEventListener('click', function() {
            // In a full implementation, this would open a lightbox
            // For now, we'll just log which image was clicked
            const imgSrc = this.querySelector('img').src;
            console.log('Image clicked:', imgSrc);
        });
    });
    
    // Animation on scroll
    // This would require additional setup with a library like AOS (Animate On Scroll)
    // For now, we'll just add a simple fade-in effect
    const animateOnScroll = function() {
        const elements = document.querySelectorAll('.service-card, .gallery-item, .about-content, .contact-container');
        
        elements.forEach(element => {
            const elementPosition = element.getBoundingClientRect().top;
            const screenPosition = window.innerHeight / 1.3;
            
            if (elementPosition < screenPosition) {
                element.style.opacity = '1';
                element.style.transform = 'translateY(0)';
            }
        });
    };
    
    // Set initial state for animated elements
    document.querySelectorAll('.service-card, .gallery-item').forEach(element => {
        element.style.opacity = '0';
        element.style.transform = 'translateY(20px)';
        element.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    });
    
    document.querySelector('.about-content').style.opacity = '0';
    document.querySelector('.about-content').style.transform = 'translateY(20px)';
    document.querySelector('.about-content').style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    
    document.querySelector('.contact-container').style.opacity = '0';
    document.querySelector('.contact-container').style.transform = 'translateY(20px)';
    document.querySelector('.contact-container').style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    
    // Run once on page load
    animateOnScroll();
    
    // Run on scroll
    window.addEventListener('scroll', animateOnScroll);
});
