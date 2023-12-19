# penumbra

Церемония Пенумбра 
https://summoning.penumbra.zone/

Ceremony contributions require using the command line. Follow the Penumbra Guide to set up pcli and create a wallet.

If you already have pcli installed, make sure you're using v0.63.1:  

<code>cargo run --quiet --release --bin pcli -- --version</code>

Contributing
The coordinator uses the Penumbra testnet to run an anonymous auction for contribution slots. At each slot, the connected participant with the highest bid is selected to contribute.

To join the queue, use pcli ceremony contribute to place a bid:

<code>cargo run --quiet --release --bin pcli -- ceremony contribute --phase 1 --bid 60penumbra --coordinator-address penumbra1qvqr8cvqyf4pwrl6svw9kj8eypf3fuunrcs83m30zxh57y2ytk94gygmtq5k82cjdq9y3mlaa3fwctwpdjr6fxnwuzrsy4ezm0u2tqpzw0sed82shzcr42sju55en26mavjnw4</code>

The minimum bid for this ceremony is 60penumbra.

Once in the queue, you just have to wait until the command completes.

Sharing your Contribution

pcli will output your contribution hash after submission.

Posting your contribution hash publicly allows others to verify that your contribution was included in the transcript!

Reconnecting and Rebidding

To change your bid, you can simply run the command again with a different bid amount. Note that each time you bid with the command above, this adds additional funds to all of the previous bids you've already submitted.

If you get disconnected for some reason, you can simply bid 0penumbra and recover your position in the queue, since all of your previous bids have been recorded.


далее неактуально


Скрипт 
<code>curl -s https://raw.githubusercontent.com/mrraange/penumbra/main/update_penumbra.sh > update_penumbra.sh && chmod +x update_penumbra.sh && ./update_penumbra.sh</code>



1.


<code>grep -A3 address ~/penumbra/validator.json</code> - выводит адрес кошелька Penumbra

Запрашиваем монеты в дискорде проекта в канал #testnet-faucet


2

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


