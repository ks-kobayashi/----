# Typescript
セットアップ
```cmd
npm init -y
npm i typescript @types/node
/src/フォルダを作成
/src/フォルダに、名前なんでもいいので空の.tsファイルを作成 ←これをやらないと何故かエラーが出る
npx tsc --init
```
実行
```cmd
npx ts-node [実行したいtsファイルの名前]
```
# React(vite)
```
npm create vite@latest
```
任意のプロジェクトを入力、フレームワークと言語を選択、
```
Project name: ... test
Select a framework: » React
Select a variant: » TypeScript
```
プロジェクトに移動、パッケージのセット、初回起動
```
cd test
npm install
```
開発用サーバーの起動
```
npm run dev
```