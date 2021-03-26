#Dibalik Masker

## Deteksi Masker Wajah

Program ini merupakan implementasi dari face mask detector berdasarkan artikel
https://www.goeduhub.com/10520/face-mask-detection-using-python-tensorflow-keras-opencv

Anda dapat mempelajari lebih detil bagaimana metode tsb menghasilkan model
untuk mendeteksi suatu foto wajah mengenakan masker atau tidak. Jadi program ini
hanya memanfaatkan model yang sudah terbentuk.

Untuk menggunakan model ini, dibutuhkan library python tensorflow dan keras, yang
didukung oleh CPU yang lebih modern karena penggunaan libcudart. PC jadul yang saya pakai (Dell Optiplex SX780) masih mampu mampu menggunakan classifier yang tersedia di OpenCV, tetapi mesin tidak mampu menghandle tensorflow/keras. Sehingga program ini diujicoba pada Notebook dengan prosesor i5 tanpa GPU.

Namun demikian saya akan tetap hunting untuk mendapatkan metode deteksi masker wajah yng lebih ringan hanya dengan OpenCV saja. 

## Text to Speech

Text to speech pada program ini mengunakan gTTS dan pyttsx3. gTTS menghasilkan  pronounsiasi yang lebih baik dari pyttsx3, tetapi harus dalam keadaan online saat melafalkan kalimat. Untuk menghemat penggunaan fitur gTTS, setiap pelafalan kalimat disimpan ke dalam cache dalam format mp3 agar pelafalan kalimat yang sama berikutnya tidak membutuhkan internet.

Untuk pyttsx3, di Linux dibutuhkan speech-engine eSpeak, jadi pastikan anda sudah menginstall espeak. Sementara di Windows dibutuhkan SAPI. Saya kurang tau fitur speech-engine ini apakah tersedia di semua versi Windows yau tidak (karena saya bukan pemakai Windows) Tetapi saya dengar pengucapn SAPI jauh lebih baik daripada espeak.

## Threading

Lag yang terjadi saat text-to-speeh sedang aktif begitu sangat terasa. Sehingga diperlukan threading agar keduanya berjalan seiringan / pararel. Mekanisme threading tentu dibutuhkan metode dan struktur yang tepat. Saya merasa threading yang saya lakukan masih belum sempurna, meski lag tidak muncul. Karena sering terjadi threading tsb tidak tertutup sempurna saat program utama selesai.

## Penutup

Terima kasih sudah mampir. Diskusi dan tanya-jawab bisa dilakukan via FaceBook messanger