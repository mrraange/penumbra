# penumbra

Скрипт/ 
<code>curl -s https://raw.githubusercontent.com/mrraange/penumbra/main/update_penumbra.sh > update_penumbra.sh && chmod +x update_penumbra.sh && ./update_penumbra.sh</code>




ПОСЛЕ завершения

<code>grep -A3 address ~/penumbra/validator.json</code> - выводит адрес кошелька Penumbra

Запрашиваем монеты в дискорде проекта в канал #testnet-faucet


2. Далее

<code>cd penumbra</code>

<code>nano validator.json</code>

меняем значения:

identity_key
(берем отсюда)
![Screenshot_3](https://user-images.githubusercontent.com/100018176/187976898-a0478207-c20e-4d83-8fad-15cde07c50df.png)

name

![Screenshot_4](https://user-images.githubusercontent.com/100018176/187977061-5679e462-9215-4e5c-b108-07db93fb1f58.png)

CTR+O Enter
CRT+X


3. Выгружаем файл  validator.json
<code>cargo run --release --bin pcli -- validator definition upload --file validator.json</code>

4. Запрашиваем список валидаторов и наблюдаем себя в самом низу
<code>cargo run --release --bin pcli -- query validator list -i</code>

5. Делегируем себе на адрес монеты

<code>cargo run --release --bin pcli transaction delegate 100penumbra --to penumbravalid1dcv9p........</code>


