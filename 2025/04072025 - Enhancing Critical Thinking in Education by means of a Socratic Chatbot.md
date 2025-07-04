**Bibliography**: Favero, Lucile, et al. "Enhancing critical thinking in education by means of a Socratic chatbot." arXiv preprint arXiv:2409.05511 (2024).<br>
**Summary Date**: 04/07/2025 <br>

---

## 🎯 What Problem Does the Paper Aim to Address? (What and Why)
Sekarang ini, chatbot sudah mulai banyak dikembangkan beberapa platform pendidikan, yang mana ditujukan sebagai sarana belajar siswa. Contohnya, khanmigo. 

Tapi, sepengetahuan author nya, belum ada yang mengembangkan chatbot yang merangsang kemampuan berpikir kritis siswa selama proses belajar. 

Dari gap itu, author bikinlah chatbot Socratic. Jadi kalau yang biasanya itu chatbotnya itu interaksi antara tutor AI 'biasa' sama siswa, nah ini tuh bukan tutor AI 'biasa' lagi, melainkan tutor AI 'Socratic'. 

Tutor AI Socratic ini dirancang punya pola pikir kayak Socrates, seorang filsuf mutakhir pada zamannya. Jadi kalau ada siswa nanya tentang suatu topik, si tutor AI Socratic ini ga bakal langsung ngasih jawaban mentahnya gitu aja, melainkan ngelempar lagi ke siswa pakai pertanyaan, dan terus ngelempar pertanyaan sampai si siswa itu ngerti dengan sendirinya melalui proses berpikir mandirinya dari pertanyaan trigger si tutor AI Socratic (bukannya dari jawaban langsung mentahnya gitu aja dari si tutor).

## 🔧 Methodology / Approach (How They Do It)
Chatbot Socratic dibuat dengan melakukan **fine-tuning** pada **model LLM pretrained** sbb: 
- Llama2 7B-parameter model
- Llama2 13B-parameter model,

yang dilatih dengan menggunakan **dataset**:
SocratiQ (dari platform Reddit: subreddit channel, namanya r/changemyview, dataset yang isinya pertanyaan-pertanyaan yang mempertanyakan sudut pandang yang sudah ada, supaya bisa ditinjau ulang kebenarannya)

Selanjutnya, model LLM yang sudah di-fine-tuning tadi itu di-**prompt tuning** (a.k.a dikasih instruksi berupa prompt) buat bikin 3 tutor yang beda: 1 tutor Socratic, 1 tutor biasa, 1 tutor random yang bisa aja responnya ga bantu siswa sama sekali. 

## 💡 Core Contribution (What's New)
Chatbot Socratic yang merangsang kemampuan berpikir kritis siswa

## 📊 Experiments & Results (What They Got)
- **Task**: fine-tuning model pretrained LLM --> prompt-tuning model yang udah di fine-tuning buat bikin 3 tutor berbeda (socratic, biasa, random) --> prompt-tuning model LLM sederhana untuk instruksiin siswa 'AI' --> generate chat antara siswa 'AI' dengan masing-masing tutor 'AI' yang sudah diinstruksikan pakai prompt-tuning --> evaluasi hasilnya pakai metrik: 
    - BLEU
    - ROUGE-L
    - METEOR
    - BERTScore
    - LLM-score (pakai prompt engineering, instruksiin AI jadi AI evaluator critical thinking)

- **Baselines compared**: baseline nya itu hasil percakapan antara siswa 'AI' dengan tutor 'AI' biasa dan random. Nah itu dibandingin sama hasil percakapan siswa 'AI' dengan tutor 'AI' socratic.
- **Main finding/results**: chatbot socratic yang ternyata berdasarkan hasil evaluasi, beneran outperformed chatbot biasa dalam meningkatkan kemampuan berpikir kritis siswa
- **Anything surprising? Overfitting? Underperform?**: Ada, ternyata LLM yang lebih canggih itu hasil metrik evaluasinya ga terlalu beda jomplang sama LLM yang lebih ringan. Dan ini bagus, karena ternyata kita ga perlu model yang canggih-canggih banget buat bisa bikin chatbot yang bagus. Dan efeknya, chatbot jadi bisa digunakan banyak orang (device nya ga harus yang canggih banget, jadi accessible). 

## 🤔 Any Gaps?
- Belum melibatkan siswa asli dalam eksperimennya (katanya bakal dilakukan sama authors di penelitian selanjutnya)
- Sentimen analisis hasil chat untuk uji keefektifan chatbot
- Reinforcement learning berbasis feedback orang untuk meningkatkan kemampuan chatbot dalam menginterpretasi chat siswa, supaya bisa ngasih respon dengan lebih akurat
- Bikin metode evaluasi yang lebih baik dari yang sudah digunakan di penelitian ini
- Investigasi jangka panjang dampak penggunaan chatbot socratic terhadap kemampuan berpikir kritis dan performansi akademik siswa

## 🔗 Next Reads
- Link to related paper