# Git-Komutlar-
# GIT

![Markdown resim](https://miro.medium.com/max/910/1*hvk5m3x_Ky_wq-d5uOAB0Q.png "title-1")
## Git Nedir?
Git, **yazılım geliştirme süreçlerinde kullanılan**, hız odaklı, dağıtık çalışan bir sürüm kontrol ve **kaynak kod yönetim sistemidir**.
Günlük programlamanın önemli bir parçasıdır (**özellikle bir ekiple çalışıyorsanız**).
Kullanabileceğiniz birçok farklı komut vardır. Ancak bazı komutlar daha sık kullanılır.
## Git Komutları
Sıklıkla kullanılan komutlar şöyledir:
````bash
	* git clone
	* git branch
	* git checkout
	* git status
	* git commit
	* git push
	* git pull
	* git log
	* git revert
	* git commit --amend
	* git merge
	* git stash
	* git diff
	* git blame
	* git add
````
## Git clone
Git clone, **uzak bir depodan (örneğin GitHub gibi) mevcut kaynak kodunu indirmek** için kullanılan bir komuttur.
```bash
git clone <https://name-of-the-repository-link>
```
## Git branch
Branch kullanarak, birkaç geliştirici aynı proje üzerinde aynı anda paralel olarak çalışabilir. Bu komutu çalıştırdığınızda git, sizin için **projenizdeki dosyaların o anki halini barındıran** deneme isimli bir branch oluşturur.
>*Kullanımı: Oluştur, listele, sil*

Branch oluşturma:
```
git branch <branch-name>
```
Bu komut yerel olarak bit branch oluşturacaktır. Yeni branch'i uzak depoya göndermek için aşağıdaki komut kullanılır:
```bash
git push -u <remote> <branch-name>
```
Branchleri görüntüleme veya listeleme:
```bash
git branch 
```
veya
```bash
git branch --list
```
Branch silme:
```bash
git branch -d <branch-name>
```
## Git checkout
Bir branch'te çalışmak için önce branch'e geçmeniz gerekir. Git checkout'u çoğunlukla **branch'ler arasında geçiş yapmak** için kullanırız. Dosyaları ve commitleri kontrol etmek için de kullanabiliriz.
```bash
git checkout <name-of-your-branch>
```
>Branchler arasında başarılı bir şekilde geçiş yapmak için izlemeniz gereken bazı adımlar vardır:
>* Geçiş yapmadan önce mevcut branch'teki değişiklikler commit edilmeli veya saklanmalıdır.
>* Kontrol etmek istediğiniz branch bölgenizde mevcut olmalıdır.

Aynı anda bir branch oluşturmanıza ve o branch'e geçmenize izin veren bir kısayol komutu:
```
git chechout -b <name-of-your-branch>
```
## Git status
Git status komutu, **mevcut branch hakkında bize gerekli tüm bilgileri verir**.
```bash
git status
```
Aşağıdaki gibi bilgileri toplayabiliriz:
* Mevcut branch'in güncel olup olmadığı
* Commit, push veya pull edilecek bir şey olup olmadığı
* Oluşturulan, değiştirilen veya silinen dosyalar olup olmadığı
## Git commit
Bu komut, Git'in *en çok kullanılan* komutudur.
Geliştirmede  belirli bir noktaya ulaştığımızda, değişikliklerimizi kaydetmek isteriz (belirli bir görev veya sorundan sonra).
Git commit, geliştirme sürecinde gerektiğinde **daha sonra geri dönebileceğiniz bir kontrol noktası** belirlemek gibidir.
Ayrıca kaynak kodda ne geliştirdiğimizi veya değiştirdiğimizi anlatan kısa bir mesaj yazmamız gerekiyor.
```bash
git commit -m "commit massage"
```
## Git push
Değişikliklerinizi gerçekleştirdikten sonra yapmak istediğiniz sonraki şey, değişikliklerinizi uzak sunucuya göndermektir.
Git push, **commitlerinizi uzak depoya yükler**.
```bash
git push <remote> <branch-name>
```
Ancak branch'iniz yeni oluşturulduysa, branch'i aşağıdaki komutla da yüklemeniz gerekir:
```bash
git push --set-upstream <remote> <name-of-your-branch>
``` 
veya
```bash
git push -u origin <branch_name>
```
>"Origin", bir projenin orijinal olarak klonlandığı uzak deponun kısa adıdır. Daha doğrusu, o orijinal havuzun URL'si yerine kullanılır ve böylece referans vermeyi çok daha kolay hale getirir.
## Git pull
Git pull komutu, **uzak depodan güncellemeleri almak için kullanılır**.
Bu komut, git fetch ve git merge komutlarının bir kombinasyonudur.
Git pull kullandığımızda, güncellemeleri uzak depodan (git fetch) alır ve yerelinizdeki en son değişiklikleri hemen uygular (git merge).
```bash
git pull <remote>
```
## Git log
Git versiyon kontrol sisteminde oluşturulmuş **commit geçmişini tarihsel olarak sondan başa doğru sırasıyla konsola yazan** bir komuttur.
```bash
git log
```
>Sadece commit başlıklarını listelemek istiyorsak:
```bash
git log --oneline
```
>Graph şeklinde çıktı almak istiyorsak:
```bash
git log --graph
```
## Git revert
Bazen **yaptığımız değişiklikleri geri almamız** gerekir.
Değişikliklerimizi yerel olarak veya uzaktan geri almanın çeşitli yolları vardır, ancak istenmeyen silinmeleri önlemek için bu komutları dikkatli bir şekilde kullanmalıyız.
**Commitlerimizi geri almanın** daha güvenli bir yolu git revert kullanmaktır. Commit geçmişimizi görmek için önce "*git log --oneline*" kullanmamız gerekiyor:
```bash
git log --oneline
```
Ardından geri almak istediğimiz commit'in hash kodunu belirtmemiz yeterlidir:
```bash
git revert <hash_code>
```
>*En son çıkmak için shift+q tuşlarına basmanız yeterli olacak.*
## Git commit --amend
Son kaydedilen işlemdeki mesajı, yani **son commit mesajını değiştirir**. Yeni bir kayıt oluşturmak yerinde, aşamalı değişiklikler bir önceki işleme eklenecektir. Sistemin yapılandırılmış metin düzenleyicisini açarak bir önceki commit mesajını değiştirmenizi ister.

```
git commit --amend -m "değiştirilen commit mesajı"
```
## Git merge
Herhangi bir branch'te yaptığımız değişiklikleri diğer bir branch'e **birleştirme ve entegre etme işlemidir**. Farklı dallarda çalışarak yapılan geliştirmelerin, örneğin version3 branch'ine birleştirilmesi gerekiyor ki yeni geliştirmeler için farklı branch açılacağı zaman veya farklı bir geliştirici daha proje üzerinde çalışacağı zaman, güncel depo kullansın.
>Örneğin A branch'ini B branch'ine birleştirmek, entegre etmek istiyorsunuz. Bunun için A branch'ine geçiş yaptıktan sonra merge işlemi yapabilirsiniz.
```bash
git merge <branch_name>
```
## Git stash
Bazen günlük çalışmalarda **tam olarak bitmeyen değişiklikleri commit yapmadan kayıt altına almak** isteyebiliriz. Örneğin; bir değişiklik üzerinde çalışırken başka bir konu ile ilgili bir değişiklik isteği geldi ve yapmakta olduğumuz işi yarım bırakıp yeni işe odaklanmak durumundayız. Bu durumda yapılan değişiklikleri kaybetmemek için yeni ve temiz bir branch oluşturmalısınız. 
```bash
git stash
```
>Geçici olarak kaydettiğimiz değişiklikleri stash listesinin en üstüne eklemek için:
```bash
git stash push -m "message description :Last Changes on readMe file" 
```
>Geçici olarak kaydettiğimiz değişikliklerin listesini görmek için:
```bash 
git stash list
```
>Stash listesinin en üstündeki kaydı branch'e yüklemek ve stash listesinden silmek için:
```bash
git stash pop
```
>Stash listesindeki herhangi bir kaydı branch'e yüklemek fakat stash listesinden silmek istemiyorsanız:
```bash
git stash apply stash@{1}
```
>Stash listesindeki herhangi bir kaydı stash listesinden silmek için:
```bash
git stash drop stash@{2}
```
>Stash listesinin tamamını silmek için:
```bash
git stash clear
```
## Conflict
Aynı dosyadaki **aynı kısımlarda yapılan değişikliklerin uzak depoda birleştirildiğinde çakışması** durumudur. Bu çakışmaları (conflict) git otomatik olarak algılayarak bize bildiriyor ve yapılan hangi değişikliği entegre etmemiz gerektiğini belirlememiz gerekiyor.
Çakışmaları engellemenin en iyi yolu master-develop hangi ana branch'te çalışıyorsak, branh salımızı sık sık güncelleştirmektir. Ek olarak kullanılan rebase-merge-commit komutları öncesi stash kullanmak da kendinizi büyük ölçüde koruma altına alarak conflict çözme noktasında yardımcı olacaktır.
## Fork
Katkı yapmak istediğiniz **projeyi birebir kopyalar**.
![Markdown resim](https://cangelis.com/wp-content/uploads/2014/10/Screen-Shot-2014-10-05-at-20.18.33.png)
Projeyi forkladıktan sonra birebir kopyası kendi depomuzda görünecek.
![Markdown resim](https://cangelis.com/wp-content/uploads/2014/10/Screen-Shot-2014-10-05-at-20.22.50.png)
### Clone ve Fork Arasındaki Fark Nedir?
Yerel depoda değişiklik yaptıktan veya **clone** yaptıktan sonra direkt push edebilirsiniz.
**Fork** depoları için, değişiklik yaptıktan sonra orijinal depoya birleştirmek için pull talebi başlatabilirsiniz.
![Markdown resim](https://visual-foxpro-programmer.com/img/some-experience/09/difference-between-git-clone-4.png)
## Git diff
Git diff komutu **iki dosyanın arasındaki farklılıkları (ve dolayısıyla benzerlikleri) bularak ekranda göstermeye yarar**.
Kendi yerelimizde yaptığımız değişiklikler neticesinde, projeyi yönlendirdiğimiz depo arasında oluşan farkları gösterir. **Hangi satırı sildiğimiz, hangi satırı eklediğimiz gibi bilgileri içerir**.
>Yapılan bütün değişiklikleri görmek için:
```bash
git diff
```
>Sadece istediğimiz dosya içerisinde nasıl bir değişiklik yapıldığını görmek için:
```bash
git diff <file_name>
```
## Git blame
Git blame komutu belirlenen dosyadaki her bir satırın **hangi commit ile eklendiği, kim tarafından ve ne zaman eklendiği bilgilerini gösterir**.
```bash
git blame <file_name>
```
## Git add
Bir dosya bir depoya kaydedilmeden önce, dosyanın Git hazırlama alanına eklenmesi gerekir. Bu komut sayesinde çalışma dizinindeki dosyalar, Git için hazırlama alanına (stage area) eklenir.

Belirli veya tüm unstaged dizinleri/ dosyaları  **git add**  komutu ile hazırlama alanına (stage area) ekleriz. Bu komutu kullanmanın birkaç farklı yolu vardır.
```
git add <file or directory name>
```
>Sahnelenmemiş tüm dosyaları eklemek için:
```
git add .
```
>Belirli bir dosyayı sahnelemek için:
```
git add index.html
```
>Tüm bir dizini sahnelemek için:
```
git add css
```
## Git rebase 
Git’de **merge** ve **rebase** komutları benzer işlevleri yerine getirmek için kullanılıyor. Her iki komut da **bir daldaki değişiklikleri başka bir dala birleştirmek için kullanılır**. Ancak bu iki komut arasında proje tarihçesinin oluşturulması ile ilgili ciddi bir farklılık vardır.

**merge** komutu ile A dalındaki değişiklikler B dalı ile birleştirildiğinde B dalının commit tarihçesinde merge işleminden kaynaklanan ve merge commit adı verilen otomatik oluşturulmuş bir commit yer alır. Bu commit A ve B dallarının tarihçelerini birbiri ile ilişkilendirir.

**rebase**  komutu kullandığımızda ise ile A dalındaki her bir commit B dalına sanki commit işlemi B dalında yapılmış gibi yeniden yazılır. Bu sayede B dalının commit tarihçesi sanki tüm değişiklikler bu dalda olmuş gibi düz ve kesintisiz görünür.

**rebase** komutu yerel ve kısa süreliğine (örneğin bir hata giderme veya deneysel bir çalışma için oluşturulan) geçerli dallar için kullanılmalı.
```bash
git rebase <branch_name>
```

## Stage
Bir dosyayı stage'lemek, aslında o dosyayı bir sonraki commit'e hazırlamak demektir. Aynı dosyada olsa bile, sadece stage'lediğimiz  değişiklikler bir sonraki commit'imizde uzaktaki git sunucusuna gönderilecektir.
>Örneğin; saat 6 oldu ve işten ayrılmak üzeresiniz ve A ve B adında 2 adet geliştirmeniz var. A geliştirmenizi tamamladınız fakat B geliştirmesi henüz tamamlanamadı. Commit yapıp eve gitmek istiyorsunuz, bu nedenle A geliştirmesine ait kısımları stage’leyip commit edebilirsiniz. B değişiklikleri hala sizin çalışma klasörünüzde olduğu gibi kalacağından, yarın sabah gelip bu geliştirmeye devam edebiliriniz.
>![Markdown resim](https://miro.medium.com/max/1400/0*5oXhSVAHm4Q7UNOj.jpg)
