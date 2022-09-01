# penumbra

ПОСЛЕ завершения выполнения скрипта
1. Запрашиваем монеты в дискорде проекта в канале #testnet-faucet
![Screenshot_2](https://user-images.githubusercontent.com/100018176/187976175-d59e2b2c-6e1f-486d-9c15-3dfca8768a4e.png)

2. переходим в папку 
cd penumbra

nano validator.json

меняем значения:

identity_key
(берем отсюда)
![Screenshot_3](https://user-images.githubusercontent.com/100018176/187976898-a0478207-c20e-4d83-8fad-15cde07c50df.png)

name

![Screenshot_4](https://user-images.githubusercontent.com/100018176/187977061-5679e462-9215-4e5c-b108-07db93fb1f58.png)

CTR+O Enter
CRT+X


3. Выгружаем файл  validator.json
cargo run --release --bin pcli -- validator definition upload --file validator.json

4. Запрашиваем список валидаторов и наблюдаем себя в самом низу
cargo run --release --bin pcli -- query validator list -i

5. Делегируем себе на адрес монеты

cargo run --release --bin pcli transaction delegate 100penumbra --to penumbravalid1dcv9p........


