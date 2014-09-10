% 秘伝のタレからコードへ.
% @koduki
% Sep 11, 2014

Agenda
================================================================================
- What is Jenkins?
- Jenkins gives us what?
- How to use?
- Conclusion


秘伝のタレあるある
================================================================================
- 長年運用されてきたので、全容を知ってる人が居ない
- 手順書は存在するが、変更毎の変更手順書なので新規に環境を作るときの参考にはできない
- 手順書と実態が違う
- 複数のサーバの１台だけ設定が違う

秘伝のタレあるある
================================================================================
\begin{center}
\fontsize{120px}{0pt}\selectfont
\textcolor{red}{同じ環境が２度と作れない！！}
\end{center}

解決策
================================================================================
- ドキュメント管理を徹底する！ <- 絶対破綻する。絶対にだ！
- 資産管理ツール(QND, SkySea, Lanscope)
- Infrastructure as Code

Infrastructure as Code
================================================================================

- 自動化（=プログラム化）を前提としてインフラをコードとして管理する考え方
- レビューやバージョン管理でプログラム言語で培われたベストプラクティスが使える
- 設定を見ることで、どのサーバに何が入ってるかを簡単に確認できる
- 自動構築でサーバの増設や、検証環境の構築コストが一気に下る

Infrastructure as Codeの良くある誤解
================================================================================

- Q. 仮想環境で使う技術
- A. 大量にサーバを扱う仮想環境で必須なだけで、ベアメタルでも十分有効

- Q. OSS製品にしか使えない
- A. CUIで作業出るものベースなら基本問題ない。WeblogicなどOracle製品の事例もある

Infrastructure as Codeの基本的な流れ
================================================================================
## step0 git等からChefリポジトリをチェックアウト
- 通常は開発と同様にこのタイミングでブランチを作成

## step1 sandboxで検証スクリプトと構築スクリプトを作成
- Vagrant等でローカルにsandboxを作成
- serverspecで修正したい内容のテストを記述
- 未知のインストール手順の確認
- sandbox向けにChefで構築スクリプト(cookbook)を作成
- serverspecの結果がOKなことを確認

## step2 検証環境等への反映
- テストスクリプトを流して、差分が今回修正分だけなのを確認
- 構築スクリプトを実行
- テストスクリプトを実行
- (必要があれば)アプリケーションのテストを実行

## step3 レビュー　＆　マージ
- Pull Requestにより第三者レビューを行う
- レビューで問題がなければmaster-branch等にマージ

Jenkins gives us what?
================================================================================
## Our Case Study 02 : deploy on stage environment
- We use deployment on stage environment.
- This is made of dependent tasks of 4.
	1. check out the latest code and build new module
	2. deploy new module
	3. activate new module
	4. undeploy old module
- If you do manualy this task, it's complexy.
- However, jenkins don't make mistake and don't complain.
- Because, he is a machine.

Jenkins gives us what?
================================================================================
## Our Case Study 03 : send veracode report.
- We use veracode. This is Static Application Security Testing(SAST).
- This analysis is very long time. Usually, it's half or 1 day.
- A report will not be sent, if you are rest or forget execute.
- However, jenkins don't forget and don't rest.
- Because, he is a machine.

Jenkins gives us what?
================================================================================
\begin{center}
\fontsize{120px}{0pt}\selectfont
\textcolor{yellow}{Jenkins execute task on your behalf !}
\end{center}


How to use?
================================================================================
## Install
- Download war file from official site(http://jenkins-ci.org/)
- Execute jar

```sh
java -jar jenkins.war
```

- Access "http://localhost:8080"
- It's so easy!
- Of course, you can use our common environemnt. please tell me.

参考
================================================================================
- http://www.slideshare.net/y05_net/infrastructure-as-code-35373108
- This tool execute build, test, deploy, analyze metrix, report... instead of you.
- A try is so easy!
```sh
java -jar jenkins.war
```
