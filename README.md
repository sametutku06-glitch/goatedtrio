# Cam Sınav Arşivi — GitHub Pages + Supabase

Bu sürüm GitHub Pages üzerinde görünür, Supabase Edge Function ile şifreleri ve özel PDF/müzik dosyalarını korur.

## Bir defalık Supabase kurulumu

Supabase Dashboard → SQL Editor içinde `supabase/migrations/20261024_portal.sql` dosyasının tamamını çalıştırın.

Dashboard → Edge Functions → **Create a new function** → adı `portal`. `supabase/functions/portal/index.ts` içeriğini yapıştırıp deploy edin. Function ayarlarında JWT verification kapalı olmalıdır.

Dashboard → Edge Functions → Secrets bölümüne şunları ekleyin:

- `STUDENT_PASSWORD` = `515`
- `ADMIN_PASSWORD` = `utku1`
- `PORTAL_TOKEN_SECRET` = 'uzun rastgele bir metin'
'
## GitHub Pages yayını

Bu klasörün içindekileri GitHub reposunun köküne yükleyin: `index.html`, `config.js`, `supabase/` ve `README.md`.

Repository → Settings → Pages → **Deploy from a branch** → `main` + `/ (root)` → Save.

Birkaç dakika sonra sitenin URL'si görünür. Öğrenci giriş şifresi `515`; yönetici şifresi `utku1` olur. Yönetici şifresini Supabase Secrets ekranından değiştirin.

`sb_publishable_...` anahtarı `config.js` içinde kalabilir; bu tarayıcı için tasarlanmış public anahtardır. Secret key asla GitHub'a veya `config.js` dosyasına konmamalıdır.
