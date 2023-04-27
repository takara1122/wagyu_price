# Git Lesson

## リモートリポジトリとローカルリポジトリとはそれぞれなんでしょうか？
- リモートリポジトリは、ネット上に配置して複数人で共有するためのリポジトリ。
ネット上にソースコードをアップするための専用のサービスがある。代表的なものの一つとして、GitHubというリモートリポジトリを提供するサービスがある。

- ローカルリポジトリは、開発者一人ひとりが使用するために自分のPC上に配置するためのリポジトリ。ローカルリポジトリを使って手元のPCで開発を行うことができる。開発環境を共有・公開したい時はそれをリモートにアップロードする。



## プッシュとマージの違いは何でしょうか？
- プッシュは、ローカルリポジトリの内容をリモートリポジトリにアップロードすること。
- マージは、今いるブランチに他のブランチで編集した内容を取り込むこと。




## コミットとプッシュの違い
-コミットはローカルリポジトリへの変更を反映すること。
-プッシュはリモートリポジトリへの変更を反映すること。

-コミットとプッシュの関係性は、コミットでローカルリポジトリに変更を反映し、
そのコミットで反映した内容をプッシュでリモートリポジトリに反映させる。



## コミットのメッセージはどのように描いてあげるのが最適でしょうか？
- 一目で変更内容がわかるようにすること。各チームやプロジェクトでルールがある場合が多いので、必ずその決まりに準拠したメッセージにすること。
-コミットメッセージを分かりやすくするには、履歴を見た際にそのコミットメッセージから「なぜ変更を行ったのか」「どんな変更を行なったのか」がわかるようなメッセージにすることが大事。ログを見返した時に変更内容を把握するためには変更内容のコードを読まないといけなくなるため。


## ローカルでマージするフローと、プルリクエストでマージするフローの違いはなんでしょうか？
- ローカルでマージするフローを実際の現場で行うと、コードレビューをする前にmasterに反映されるため、コードにバグがあっても気づかない可能性がでてくる。そして、本番環境はmasterの内容を反映させることが一般的なので、最終的には誰も気づかなかったバグがそのまま本番環境にアップされ、大変な事態になる。
- それに対して、プルリクエストでマージするフローだと、コードレビューをしてからマージするという手順を踏むことで、事前にバグを発見する事ができる。
ただ、注意点が一つあり、リモート上でマージした内容を、ローカルのmasterブランチは知らないという点。自動でリモートリポジトリとローカルリポジトリは同期されない。そのため、ローカルのmasterに、リモートリポジトリのmasterで行った変更を反映させるpullを使用する。



## コンフリクトを起こしてしまった場合、どう対処すべきですか？
1. 先にマージされた変更内容を取り込む
2. 後にマージしようとしている変更内容を取り込む
3. どちらの変更内容も取り込む

- ただ、実際の現場ではもっと複雑な箇所でコンフリクトが起きることも珍しくない。コンフリクト解決には自分以外の人が書いたソースコードの内容を把握する必要があるため、少しでも意図が読み取れない処理とぶつかってしまった場合は、そのソースコードを書いた人と相談しながら作業を進めるようにしよう。


