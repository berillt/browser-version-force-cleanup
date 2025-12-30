# browser-version-force-cleanup
This script forcefully removes all Microsoft Edge versions **except** the specified version. It is designed for enterprise environments using **Microsoft Intune** or **SCCM**.
> ⚠️ This method is NOT officially supported by Microsoft.

TR: Bu script, belirlenen Microsoft Edge sürümü haricindeki tüm Edge sürümlerini zorla temizler.  
EN: This script forcefully removes all Microsoft Edge versions except the specified one.

TR: Intune veya SCCM ortamlarında SYSTEM yetkisi ile çalışacak şekilde tasarlanmıştır.  
EN: Designed to run with SYSTEM privileges in Intune or SCCM environments.

TR: Yeni bir Edge sürümü onaylandığında yalnızca `$KeepVersion` değeri güncellenmelidir.  
EN: When a new Edge version is approved, only the `$KeepVersion` value needs to be updated.
