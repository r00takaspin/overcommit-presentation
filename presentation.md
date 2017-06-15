#  👊 Overcommit - хуки хуками погоняют

###### Вольдэмар Дулецкий, ruby разработчик, компания Evrone

---

:scream: Не пытайтесь сами гуглить
===
**название не очень оригинальное*

<img src="./images/dont_google.png" alt="Drawing" style="width: 70%;"/>

---

# :fire: Что делает?
### Позволяет просто управлять хуками git


---

# :zap: Хуки 

### PreCommit:
* ### rubocop
* ### haml-lint
* #### scss-lint
### PrePush:
* ### rspec

###### Полный список (около 70 возможных проверок только на PreCommit): https://github.com/brigade/overcommit

---

# :floppy_disk: Конфигурационный файл `.overcommit.yml`

```yaml

PreCommit:
  RuboCop:
    enabled: true
    command: ['bin/bundle', 'exec', 'rubocop', '-R']
    on_warn: fail
  HamlLint:
    enabled: true
    command: ['bin/bundle', 'exec', 'haml-lint', 'app/views/']
    on_warn: fail
  ScssLint:
    enabled: true
    command: ['bin/bundle', 'exec', 'scss-lint']
    include: 'app/assets/**/*.scss'
    on_warn: fail

PrePush:
  RSpec:
    enabled: true
```

---
# :eyes: Как это выглядит?

<img src="https://camo.githubusercontent.com/1968863cd4be5843e9e9b2ba33f0e54059035958/68747470733a2f2f627269676164652e6769746875622e696f2f6f766572636f6d6d69742f6f766572636f6d6d69742e676966" />

---


# :moneybag: PROFIT

* ### не надо заморачиваться c настройкой CI
* ### код не прошедший проверку не попадает в репозиторий
* ### бесплатно
* ### идеально подходит для самоконтроля

---

# :rocket: В реальной жизни
* **overcommit**: pre-commit hooks - линтеры
* **overcommit**: pre-push hooks - тесты
* vexor.io - тесты в облаке, гоняются на каждый коммит
* codeclimate - еще раз гоняет линтеры на код, помещенный в коммит
* автоматический деплой при слиянии в ветку `develop` через сервис cloud66

---

# :clap: Контакты

### Вольдэмар Дулецкий (Voldemar Duletskiy)
### Email: voldemar.duletskiy@gmail.com
### GitHub: github.com/r00takaspin


:wine_glass: :wine_glass: :wine_glass:
=== 
