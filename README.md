
<body>
  <h1>Таны манлайлах хэв маяг юу вэ?</h1>
  <form id="quizForm">
   
    <div class="question" id="q1">
      <p><b>1. Өсөж том болох явцад тань...</b></p>
      <label><input type="radio" name="q1" value="A"> А. Таны асран хамгаалагчид таны хэрэгцээнд анхаардаггүй байсан.</label><br>
      <label><input type="radio" name="q1" value="B"> Б. Та гэр бүлийнхээ том хүмүүсийг дийлдэг байсан.</label><br>
      <label><input type="radio" name="q1" value="C"> В. Асран хамгаалагчдын аль нэг нь давуу эрхтэй байсан.</label><br>
      <label><input type="radio" name="q1" value="D"> Г. Асран хамгаалагчдын дунд эрх ашгийн зөрчил байсан.</label>
    </div>
   
    <div class="question" id="q2">
      <p><b>2. Хүүхэд байхдаа та...</b></p>
      <label><input type="radio" name="q2" value="A"> А. Насанд хүрсэн хүний үүрэг гүйцэтгэдэг байсан уу?</label><br>
      <label><input type="radio" name="q2" value="B"> Б. Асран хамгаалагчдынхаа сэтгэл санааг дэмждэг байсан.</label><br>
      <label><input type="radio" name="q2" value="C"> В. Гэр бүлийн хүчтэй хүнийг дуурайх гэж хичээдэг байсан.</label><br>
      <label><input type="radio" name="q2" value="D"> Г. Асран хамгаалагчдынхаа статусыг магтуулахыг хичээдэг байсан.</label>
    </div>
   
    <div class="question" id="q3">
      <p><b>3. Ажил дээрээ та...</b></p>
      <label><input type="radio" name="q3" value="A"> А. Бусдын хийхийг хүсдэггүй ажлыг хийдэг.</label><br>
      <label><input type="radio" name="q3" value="B"> Б. Үйл явцаас илүү үр дүнд анхаардаг.</label><br>
      <label><input type="radio" name="q3" value="C"> В. Бусдаас илүү хурдан урагшилдаг мэт санагддаг.</label><br>
      <label><input type="radio" name="q3" value="D"> Г. Хуучирсан зүйлийг эхэлж олж хардаг.</label>
    </div>
   
    <div class="question" id="q4">
      <p><b>4. Ажлын байран дээрээ та...</b></p>
      <label><input type="radio" name="q4" value="A"> А. Өөрийгөө хамгаалах нь хэцүү байдаг.</label><br>
      <label><input type="radio" name="q4" value="B"> Б. Үр дүнгүй хурлуудаас зайлсхийдэг.</label><br>
      <label><input type="radio" name="q4" value="C"> В. Бусдыг айлгасан санал, гомдол сонсдог.</label><br>
      <label><input type="radio" name="q4" value="D"> Г. Шинийг санаачлагч нь байдаг.</label>
    </div>
    
    <div class="question" id="q5">
      <p><b>5. Хамтран ажиллагсадтайгаа харьцахдаа та...</b></p>
      <label><input type="radio" name="q5" value="A"> А. Бусдын орхигдуулдаг нарийн зүйлсийг анзаардаг.</label><br>
      <label><input type="radio" name="q5" value="B"> Б. Ачааллын үед холддог.</label><br>
      <label><input type="radio" name="q5" value="C"> В. Удирдлага байхгүй үед таныг сонсдог.</label><br>
      <label><input type="radio" name="q5" value="D"> Г. Бусдын хувь нэмрийг үнэлдэг.</label>
    </div>

    <button type="button" onclick="calculateResult()">Submit</button>
  </form>
  <div id="result" class="result"></div>

  <script>
    
    function calculateResult() {
  const form = document.getElementById('quizForm');
  const answers = new FormData(form);
  const counts = { A: 0, B: 0, C: 0, D: 0 };
  let allAnswered = true;

  
  for (let i = 1; i <= 5; i++) {
    if (!answers.has('q' + i)) {
      allAnswered = false;
    }
  }

  if (!allAnswered) {
    alert("Та бүх асуултад хариулна уу.");
    return;
  }


  for (let value of answers.values()) {
    counts[value]++;
  }


  let result = "";
  if (counts.A >= 3) {
    result = `
      <h1>Та 'Pleaser' хүн юм.</h1>
      <p>“Pleaser” хэв маяг нь бусадтай илүү дотно холбогдох замаар эрх мэдлийг бий болгодог хүмүүс юм.
      Энэ хэв маягийн гол цөм нь гэр бүлийн ямар нэгэн гачигдалд байдаг. Санхүүгийн асуудлаас эхлээд өвчтэй гэр бүлийн гишүүнтэй байсан гэх мэт
      гадны хүчин зүйлсийн улмаас энэ хэв маягийн хүмүүс амьдралынхаа эхэн үед асран хамгаалагчдаасаа анхаарал халамж авч чадаагүй байдаг. Үүний үр дүнд эдгээр хүмүүс
      ихэвчлэн бусдаар хүлээн зөвшөөрөгдөх маш их хэрэгцээтэй байдаг ба бусдад анхаарал халамж тавихаар бүтээгдсэн байдаг.</p>`;
  } else if (counts.B >= 3) {
    result = `
      <h1>Та 'Charmer' хүн юм.</h1>
      <p>“Charmer” хэв маяг нь бусдыг өөртөө татахад маш их анхаардаг хүмүүс байдаг.
      Тэд дийлэнхдээ удирдлага, захиргааг тэр бүр хүндэлдэггүй.
      Учир нь тэд хүүхэд ахуй насандаа сэтгэл санааны хувьд тусламж хэрэгтэй асран хамгаалагчаа тайвшруулах үүрэгтэй байсан ба
      тэд ямар нэгэн асуудалтай эсвэл хэвийн энгийн гэр бүл ч байсан гэсэн асран хамгаалагчдынх нь аль нэг нь хамтрагчаасаа илүү хүүхдээсээ сэтгэл санааны дэмжлэг авдаг байсан байдаг.
      Тиймээс тэд ихэвчлэн яаж бусдыг удирдаж өөрийнхөөрөө чиглүүлж хүссэн зүйлээ авахыг сурсан байдаг.</p>`;
  } else if (counts.C >= 3) {
    result = `
      <h1>Та 'Commander' хүн юм.</h1>
      <p>“Commander” хэв маяг нь эцсийн үр дүнд илүү анхаарч ажилладаг бөгөөд бусдыг яаруулах шахах мэдрэмжийг төрүүлэх хандлагатай байдаг.
      Тэд дүрэм журмыг чанд сахидаг, эрх мэдлийн хатуу шатлалтай гэр бүлээс гаралтай байх магадлалтай.
      Ихэвчлэн спорт, шашин шүтлэг, цэрэг арми эсвэл маш хатуу дүрэм журамтай гэр бүлийн тогтолцоонд өссөн байдаг.</p>`;
  } else if (counts.D >= 3) {
    result = `
      <h1>Та 'Inspirer' хүн юм.</h1>
      <p>“Inspirer” хэв маяг нь шинийг сэтгэгчид, сайн сайхны төлөө тууштай ажилладаг хүмүүс байдаг.
      Тэд өөртөө юу ашигтайг ч тооцоололгүй бусад хүмүүсийг дэмждэг. Энэ хэв маягийн хүмүүс ихэвчлэн өөрийгөө сайн илэрхийлдэг урлагийн эсвэл шинжлэх ухааны ажил хийдэг гэр бүлд өссөн байдаг
      ба ажил мэргэжлийнхээ хувьд өндөр түвшинд хүрэхийн төлөө өөрийгөө золиослоход ч бэлэн асран хамгаалагчидтай байсан байдаг.</p>`;
  } else {
    result = `
      <h1>Таны сонголт тодорхой үр дүн өгөөгүй.</h1>
      <p>Та асуултуудыг өөр хариултаар бөглөж дахин туршиж үзээрэй.</p>`;
  }

  const resultWindow = window.open("", "_blank", "width=800,height=600");
  resultWindow.document.write(`
    <html>
      <head>
        <title>Үр дүн</title>
        <style>
          body {
            font-family: Arial, sans-serif;
            text-align: center;
            background: linear-gradient(to right, #d4fc79, #96e6a1); /* Light Green to Soft Blue */
            color: #333;
            padding: 20px;
          }
          h1 {
            font-size: 2em;
          }
          p {
            font-size: 1.2em;
          }
        </style>
      </head>
      <body>
        ${result}
      </body>
    </html>
  `);
  resultWindow.document.close();
}

  </script>
</body>
</html>
