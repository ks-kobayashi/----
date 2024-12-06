# TypeScript ユーティリティ型

- typeof obj: 任意の値objの型を抽出
- keyof obj: 任意の値objの全てのKeyの値の直和の型を抽出
- Parameters<T>: 関数型Tの引数の型を配列形式で抽出
- ReturnType<T>: 関数型Tの戻り値の型を抽出
- ConstructorParameters<T>: クラス型Tのコンストラクタの引数の型を抽出
- Extract<T, U>: Union型 T から、T extends U を満たす型を抽出

→使用例
```ts
type Human = { name: string; age: string; };
type Employee = Human & { companyName: string; };
type Teacher = Human & { subject: string; };
type Doctor = Human & { companyName: string; patients: string[]; };

type HumanTypes = Employee | Teacher | Doctor | Human;

type NewType = Extract<HumanTypes, { companyName: string; }>;
// 中身: Employee | Doctor
```