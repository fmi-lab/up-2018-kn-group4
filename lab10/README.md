1. Да се напише функция `int hammingDistance(char firstString[100], char secondString[100])`, която по дадени два низа с еднаква дължина намира [разстоянието на Хеминг](https://bg.wikipedia.org/wiki/%D0%A0%D0%B0%D0%B7%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D0%B5_%D0%BD%D0%B0_%D0%A5%D0%B5%D0%BC%D0%B8%D0%BD%D0%B3) между тях, т.е. в колко позиции се различават.
2. [Шифърът на Цезар](https://en.wikipedia.org/wiki/Caesar_cipher) е метод за кодиране на съобщения, при който всяка буква от съобщението се замества
с буквата на фиксиран брой позиции от него в азбуката. Например при шифър с изместване 5, всяко срещане на буквата `a` ще се замени с `f`,
а всяко срещане на `z` - с `e` (т.е. ако стигнем края на азбуката, продължаваме да броим от началото).
Всички останали символи, които не са букви (включително интервали и пунктуация), не се променят.

   Декодирането става по обратния път - т.е. при изместване 5, всеки символ трябва да се върне 5 позиции назад.
 
   Да се напишат функции:
     * `void encodeCaesar(char plaintext[1000], int shift, char ciphertext[1000])` - кодира даденото plaintext съобщение с изместване `shift` и записва резултата в ciphertext
     * `void decodeCaesar(char ciphertext[1000], int shift, char plaintext[1000])` - декодира даденото кодирано съобщение ciphertext с изместване `shift` и записва резултата в plaintext
     
   Не забравяйте да запишете завършваща 0 в края резултатния низ.
   
3. [Шифър на Виженер](https://bg.wikipedia.org/wiki/%D0%A8%D0%B8%D1%84%D1%8A%D1%80_%D0%BD%D0%B0_%D0%92%D0%B8%D0%B6%D0%B5%D0%BD%D0%B5%D1%80)
е друг метод за кодиране на съобщения, малко по-сложен от Цезаровия шифър. Шифърът на Виженер е комбинация от няколко шифъра на Цезар с различно отместване, които се прилагат върху поредните символи от съобщението.
Комбинацията от шифри се задава с ключова дума, като изместването на i-тия шифър е равно на номера в азбуката на i-тата буква от ключовата дума -
например при ключова дума `fmi`, първият символ на съобщението се отмества с 6 позиции, вторият с 13, а третият с 9. Четвъртият символ от съобщението отново се отмества с 6 позиции и т.н. (вижте и примера в линка).

   Да се напишат функции:
     * `void encodeVigenere(char plaintext[1000], char keyWord[10], char ciphertext[1000])` - кодира даденото plaintext съобщение с ключова дума `keyWord` и записва резултата в ciphertext
     * `void decodeVigenere(char ciphertext[1000], char keyWord[10], char plaintext[1000])` - декодира даденото кодирано съобщение ciphertext с ключова дума `keyWord` и записва резултата в plaintext
     
   Не забравяйте да запишете завършваща 0 в края резултатния низ.

4. Разбиване на шифър на Цезар:
   Нека е даден масив от думи, които знаем, че могат да се срещнат в дадено съобщение. Дадено е и съобщение, кодирано с шифър на Цезар с неизвестно отместване. Да се намери отместването на шифъра.
   
   Сигнатура на функцията: `int crackCaesarCipher(char ciphertext[1000], char knownWords[10000][10], int knownWordsLength)`

   Упътване: Изпробвайте всички възможни варианти за декодиране с отместване от 1 до 26 (с функцията от задача 2). За всеки вариант проверете дали декодираното съобщение е смислено, т.е. дали се състои само от известните думи от масива. Примерни помощни функции, които да имплементирате:
     * `bool isValidWord(char word[10], char knownWords[10000][10], int knownWordsLength);`
     * `bool isValidSentence(char plaintext[1000], char knownWords[10000][10], int knownWordsLength);`
   
