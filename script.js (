document.addEventListener('DOMContentLoaded', function() {
    const generateBtn = document.getElementById('generateBtn');
    const downloadBtn = document.getElementById('downloadBtn');
    const newVideoBtn = document.getElementById('newVideoBtn');
    const playBtn = document.getElementById('playBtn');
    const pauseBtn = document.getElementById('pauseBtn');
    const restartBtn = document.getElementById('restartBtn');
    const textInput = document.getElementById('textInput');
    const outputSection = document.getElementById('outputSection');
    const videoPreview = document.getElementById('videoPreview');
    
    let generatedVideo = null;
    let videoProgressInterval = null;
    
    // Video oluşturma butonu
    generateBtn.addEventListener('click', function() {
        if (textInput.value.trim() === '') {
            alert('Lütfen video için metin giriniz.');
            return;
        }
        
        // Yükleme ekranını göster
        showLoadingScreen();
        
        // Simüle edilmiş video oluşturma süreci
        simulateVideoCreation();
    });
    
    // İndirme butonu
    downloadBtn.addEventListener('click', function() {
        if (!generatedVideo) {
            alert('Önce bir video oluşturmalısınız.');
            return;
        }
        
        alert('Bu demo sürümünde indirme işlemi simüle edilmiştir. Gerçek uygulamada video indirilebilir.');
        
        // Gerçek uygulamada burada video indirme işlemi yapılır
        // Örnek: const url = URL.createObjectURL(generatedVideo);
        // Örnek: const a = document.createElement('a');
        // Örnek: a.href = url;
        // Örnek: a.download = 'olusturulan-video.mp4';
        // Örnek: document.body.appendChild(a);
        // Örnek: a.click();
        // Örnek: document.body.removeChild(a);
    });
    
    // Yeni video butonu
    newVideoBtn.addEventListener('click', function() {
        textInput.value = '';
        outputSection.style.display = 'none';
        generatedVideo = null;
        
        // Seçimleri sıfırla
        document.getElementById('voiceSelect').selectedIndex = 0;
        document.getElementById('styleSelect').selectedIndex = 0;
        document.getElementById('bgMusic').selectedIndex = 0;
    });
    
    // Video kontrol butonları
    playBtn.addEventListener('click', function() {
        alert('Video oynatılıyor...');
    });
    
    pauseBtn.addEventListener('click', function() {
        alert('Video duraklatıldı...');
    });
    
    restartBtn.addEventListener('click', function() {
        alert('Video başa sarılıyor...');
    });
    
    // Yükleme ekranını göster
    function showLoadingScreen() {
        videoPreview.innerHTML = `
            <div class="loading">
                <div class="spinner"></div>
                <p>Video oluşturuluyor, lütfen bekleyin...</p>
                <div class="progress-bar">
                    <div class="progress" id="progressBar"></div>
                </div>
            </div>
        `;
        
        outputSection.style.display = 'block';
        generateBtn.disabled = true;
        generateBtn.textContent = 'Oluşturuluyor...';
        
        // Sayfayı çıktı bölümüne kaydır
        outputSection.scrollIntoView({ behavior: 'smooth' });
    }
    
    // Video oluşturma simülasyonu
    function simulateVideoCreation() {
        const progressBar = document.getElementById('progressBar');
        let progress = 0;
        
        videoProgressInterval = setInterval(function() {
            progress += 5;
            progressBar.style.width = `${progress}%`;
            
            if (progress >= 100) {
                clearInterval(videoProgressInterval);
                finishVideoCreation();
            }
        }, 200);
    }
    
    // Video oluşturma tamamlandığında
    function finishVideoCreation() {
        // Yükleme ekranını kaldır
        videoPreview.innerHTML = '';
        
        // Video önizlemesi oluştur
        const videoElement = document.createElement('div');
        videoElement.style.width = '100%';
        videoElement.style.height = '100%';
        videoElement.style.background = 'linear-gradient(45deg, #6e8efb, #a777e3)';
        videoElement.style.display = 'flex';
        videoElement.style.alignItems = 'center';
        videoElement.style.justifyContent = 'center';
        videoElement.style.color = 'white';
        videoElement.style.fontSize = '18px';
        videoElement.style.fontWeight = 'bold';
        videoElement.innerHTML = `
            <div style="text-align: center;">
                <div style="font-size: 48px; margin-bottom: 15px;">🎬</div>
                <p>Videonuz Hazır!</p>
                <p style="font-size: 14px; margin-top: 10px;">${truncateText(textInput.value, 50)}</p>
            </div>
        `;
        
        videoPreview.appendChild(videoElement);
        generatedVideo = true; // Gerçek uygulamada bu bir video blob'u olurdu
        
        // Butonları etkinleştir
        generateBtn.disabled = false;
        generateBtn.textContent = 'Video Oluştur';
        
        // İndirme butonunu göster
        downloadBtn.style.display = 'block';
    }
    
    // Uzun metinleri kısaltma
    function truncateText(text, maxLength) {
        if (text.length <= maxLength) return text;
        return text.substring(0, maxLength) + '...';
    }
    
    // Sayfa yüklendiğinde yapılacaklar
    function init() {
        // Mobil cihaz kontrolü
        if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
            console.log("Mobil cihazda çalışıyor");
        }
        
        // Tarayıcı özellik kontrolü
        if (!('indexedDB' in window)) {
            console.log("Bu tarayıcı IndexedDB'yi desteklemiyor");
        }
    }
    
    // Uygulamayı başlat
    init();
});
