// تغيير لون الخلفية عند تحميل الصفحة
window.onload = function () {
    document.body.style.backgroundColor = "#f0f0f0";
};

// إظهار رسالة عند النقر على رابط الشراء
document.querySelectorAll('.product a').forEach(link => {
    link.addEventListener('click', function (event) {
        alert('شكراً لاهتمامك! سيتم توجيهك الآن إلى صفحة الشراء.');
    });
});

// تمرير القائمة من اليمين إلى اليسار
document.querySelector('nav ul').style.direction = 'rtl';

// تمرير سلس عند النقر على الروابط
document.querySelectorAll('nav a').forEach(anchor => {
    anchor.addEventListener('click', function (event) {
        event.preventDefault();
        const targetSection = document.querySelector(this.getAttribute('href'));
        targetSection.scrollIntoView({ behavior: 'smooth' });
    });
});
// تغيير رسالة الترحيب بعد 5 ثوانٍ
setTimeout(() => {
    const welcomeMessage = document.querySelector('.hero h2');
    welcomeMessage.textContent = 'استمتع بوقتك معنا!';
}, 5000);

// زر إرسال رسالة واتساب مباشرة
const whatsappButton = document.createElement('button');
whatsappButton.textContent = 'تواصل عبر الواتساب';
document.querySelector('footer').appendChild(whatsappButton);

whatsappButton.addEventListener('click', () => {
    const message = encodeURIComponent('مرحبًا! أود الاستفسار عن أحد المنتجات.');
    window.open(`https://wa.me/201152206421?text=${message}`, '_blank');
});
// التحقق من صحة البريد الإلكتروني
const form = document.getElementById('form');
const emailInput = document.getElementById('email');
const message = document.getElementById('message');

form.addEventListener('submit', (event) => {
    event.preventDefault(); // منع إرسال النموذج بشكل افتراضي

    if (emailInput.value.includes('@')) {
        message.style.color = 'green';
        message.textContent = 'تم إرسال الرسالة بنجاح!';
        emailInput.value = ''; // إعادة تعيين الحقل
    } else {
        message.style.color = 'red';
        message.textContent = 'يرجى إدخال بريد إلكتروني صالح.';
    }
});
// تأثير الكتابة التلقائية
const text = "أهلاً بك في موقعنا! نحن هنا لخدمتك.";
const typewriterElement = document.getElementById('typewriter');
let index = 0;

function typeWriter() {
    if (index < text.length) {
        typewriterElement.textContent += text.charAt(index);
        index++;
        setTimeout(typeWriter, 100); // التحكم بسرعة الكتابة
    }
}

window.onload = typeWriter; // تشغيل التأثير عند تحميل الصفحة
// التبديل بين اللغة العربية والإنجليزية
const toggleLanguage = document.getElementById('toggleLanguage');
const texts = {
    ar: {
        welcome: "أهلاً بك في موقعنا!",
        products: "منتجاتنا",
    },
    en: {
        welcome: "Welcome to our website!",
        products: "Our Products",
    }
};

let currentLanguage = 'ar';

toggleLanguage.addEventListener('click', () => {
    currentLanguage = currentLanguage === 'ar' ? 'en' : 'ar';
    document.querySelector('h2').textContent = texts[currentLanguage].welcome;
    document.querySelector('#products h2').textContent = texts[currentLanguage].products;
    toggleLanguage.textContent = currentLanguage === 'ar' ? 'Switch to English' : 'تبديل إلى العربية';
});
const themeSelector = document.getElementById('themeSelector');

themeSelector.addEventListener('change', (e) => {
    const theme = e.target.value;
    document.body.className = theme; // تطبيق النمط المختار
    localStorage.setItem('selectedTheme', theme); // حفظ النمط
});

// استعادة النمط المحفوظ
const savedTheme = localStorage.getItem('selectedTheme');
if (savedTheme) {
    document.body.className = savedTheme;
    themeSelector.value = savedTheme;
}
let cartCount = 0;
const cartCountElement = document.getElementById('cartCount');

document.querySelectorAll('a[href^="https://"]').forEach(button => {
    button.addEventListener('click', (e) => {
        e.preventDefault(); // منع الانتقال الفوري للرابط
        cartCount++;
        cartCountElement.textContent = cartCount; // تحديث العدد
        showToast('تمت إضافة المنتج إلى السلة!');
    });
});
const chatButton = document.getElementById('chatButton');
const chatWindow = document.getElementById('chatWindow');
const chatContent = document.getElementById('chatContent');
const chatInput = document.getElementById('chatInput');

// إظهار أو إخفاء نافذة الدردشة عند النقر على الزر
chatButton.addEventListener('click', () => {
    chatWindow.style.display = chatWindow.style.display === 'none' ? 'block' : 'none';
});

// إرسال الرسالة
chatInput.addEventListener('keypress', (e) => {
    if (e.key === 'Enter') {
        const message = chatInput.value;
        if (message) {
            chatContent.innerHTML += `<div style="margin-bottom: 5px;">أنت: ${message}</div>`;
            chatInput.value = ''; // مسح حقل الإدخال
            // هنا يمكن إضافة كود لإرسال الرسالة إلى خادم الدردشة
        }
    }
});
