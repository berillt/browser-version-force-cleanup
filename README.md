# Browser Force Version Cleanup / Tarayıcı Zorla Versiyon Temizliği

---

## Tanım / Description

TR: Bu PowerShell scriptleri, belirlenen sürümler dışında kalan Microsoft Edge ve Google Chrome sürümlerini zorla temizler.  
TR: Scriptler, tarayıcı klasörlerini, MSI uninstall registry kayıtlarını ve Update cache'lerini temizler.  
TR: Kurumsal ortamlar (Intune, SCCM) için SYSTEM yetkisi ile çalışacak şekilde tasarlanmıştır.

EN: These PowerShell scripts forcefully remove all Microsoft Edge and Google Chrome versions except the specified ones.  
EN: The scripts clean browser folders, MSI uninstall registry entries, and update caches.  
EN: Designed to run with SYSTEM privileges in enterprise environments (Intune, SCCM).

---

## Özellikler / Features

- TR: Belirlenen sürüm haricindeki klasörleri kaldırır.  
- EN: Removes all browser version folders except the specified versions.

- TR: MSI uninstall registry kayıtlarını temizler.  
- EN: Cleans MSI uninstall registry entries.

- TR: Update cache dizinlerini temizler (EdgeUpdate / GoogleUpdate).  
- EN: Cleans Update cache directories (EdgeUpdate / GoogleUpdate).

- TR: Intune veya SCCM ile otomatik dağıtıma uygundur.  
- EN: Suitable for automatic deployment via Intune or SCCM.

- TR: Log dosyası ile hangi işlemlerin yapıldığını takip edebilirsiniz.  
- EN: Provides a log file to track what actions have been performed.

---

##  Kullanım / Usage

1. TR: Script dosyalarını cihazlara dağıtın.  
   EN: Deploy the script files to target devices.

2. TR: Intune'da "Devices → Windows → Scripts → Add" yolunu takip edin.  
   EN: In Intune, go to "Devices → Windows → Scripts → Add".

3. TR: Script ayarları:  
   - Run as logged-on user:  Hayır / No  
   - Run in 64-bit PowerShell:  Evet / Yes  
   - Enforce script signature check:  Hayır / No  
   - Execution policy: Bypass  

4. TR: Script `$KeepVersionEdge` ve `$KeepVersionChrome` değişkenlerinde belirtilen sürümleri bırakır, diğerlerini kaldırır.  
   EN: The scripts keep the versions specified in `$KeepVersionEdge` and `$KeepVersionChrome` and remove all others.

---

##  Konfigürasyon / Configuration

TR: Tek yapmanız gereken `$KeepVersionEdge` ve `$KeepVersionChrome` değişkenlerini güncellemek.  
TR: Örnek: 

   $KeepVersionEdge = "143.0.3650.96"
   $KeepVersionChrome = "143.0.7499.170"

TR: Scriptler çalışırken tüm işlemler aşağıdaki log dosyalarına yazılır:
EN: All actions performed by the scripts are logged to:

   Edge: C:\ProgramData\EdgeForceCleanup.log
   Chrome: C:\ProgramData\ChromeForceCleanup.log

## Doğrulama / Verification

TR: Script çalıştıktan sonra aşağıdaki komutlarla hangi sürümlerin kaldığını kontrol edebilirsiniz:
EN: After running the scripts, verify the remaining versions using:

# Edge
"C:\Program Files (x86)\Microsoft\Edge\Application\$KeepVersionEdge\msedge.exe" --version

# Chrome
"C:\Program Files\Google\Chrome\Application\$KeepVersionChrome\chrome.exe" --version

## Uyarılar / Warnings

TR: Scriptler Microsoft tarafından desteklenmez.
EN: These scripts are NOT officially supported by Microsoft.
TR: Edge ve Chrome Update politikaları ile birlikte kullanılmalıdır, aksi takdirde eski sürümler tekrar yüklenebilir.
EN: Should be used alongside Edge and Chrome Update policies; otherwise, older versions may be reinstalled.
TR: Kendi sorumluluğunuzda kullanın.
EN: Use at your own risk.

