## Devise

1. `devise` gem 설치
```bash
$ bundle install
```
2. deveise 설치
```bash
$ rails generate devise:install
```
- `config/initialize/devise.rb` 만들어짐.
3. user 모델 만들기
```bash
$ rails generate devise user
```

- `db/migrate/20180625_devise_create_users.rb`
- `model/user.rb`
- `config/db` :devise_for:users

4. migrate
```bash
$ rake db:migrate
```

- 회원가입 : `get 'users/sign_up'`
- 로그인 : `get 'users/sign_in'`
- 로그아웃 : `get 'users/sign_out'`

6. helper method
- `user_signed_in?` : 유저가 로그인 했는지 안했는지 true/false로 리턴
- `current_user` : 로그인 되어있는 user 오브젝트를 가지고 있음
- `before_action :authenticate_user!` : 로그인 되어있는 유저 검증 (필터)

7. View 파일 수정하기
```bash
$ rails generate devise:views users
```
