# データ型

## 整数型

### 符号なし整数型

| 型      | ビット幅　       | 範囲                                                           | ビット幅の取得 | 最小値の取得 | 最大値の取得 |
| ------- | ---------------- | -------------------------------------------------------------- | -------------- | ------------ | ------------ |
| u8      | 8ビット 　       | 0 から 2<sup>8</sup> - 1                                       |    u8::BITS    | u8::MIN      | u8::MAX      |
| u16     | 16ビット         | 0 から 2<sup>16</sup> - 1                                      |   u16::BITS    | u16::MIN     | u16::MAX     |
| u32     | 32ビット         | 0 から 2<sup>32</sup> - 1                                      |   u32::BITS    | u32::MIN     | u32::MAX     |
| u64     | 64ビット         | 0 から 2<sup>64</sup> - 1                                      |   u64::BITS    | u64::MIN     | u64::MAX     |
| u128    | 128ビット        | 0 から 2<sup>128</sup> - 1                                     |  u128::BITS    | u128::MIN    | u128::MAX    |
| usize   | 計算機のワード長 | 0 から 2<sup>32</sup> - 1、 もしくは 0 から 2<sup>64</sup> - 1 | usize::BITS    | usize::MIN   | usize::MAX   |

``` rust title="unsigned-integer-type/main.rs"
fn main() {
    println!("   u8のビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}",    u8::BITS,    u8::MIN,    u8::MAX);
    println!("  u16のビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}",   u16::BITS,   u16::MIN,   u16::MAX);
    println!("  u32のビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}",   u32::BITS,   u32::MIN,   u32::MAX);
    println!("  u64のビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}",   u64::BITS,   u64::MIN,   u64::MAX);
    println!(" u128のビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}",  u128::BITS,  u128::MIN,  u128::MAX);
    println!("usizeのビット幅:{:>4}、最小値:{:>2}、最大値:{:>40}", usize::BITS, usize::MIN, usize::MAX);
}
```

```bash title="実行結果"
   u8のビット幅:   8、最小値: 0、最大値:                                     255
  u16のビット幅:  16、最小値: 0、最大値:                                   65535
  u32のビット幅:  32、最小値: 0、最大値:                              4294967295
  u64のビット幅:  64、最小値: 0、最大値:                    18446744073709551615
 u128のビット幅: 128、最小値: 0、最大値: 340282366920938463463374607431768211455
usizeのビット幅:  64、最小値: 0、最大値:                    18446744073709551615
```

### 符号あり整数型

| 型      | ビット幅　       | 範囲                                                                                         | ビット幅の取得 | 最小値の取得 | 最大値の取得 |
| ------- | ---------------- | -------------------------------------------------------------------------------------------- | -------------- | ------------ | ------------ |
| i8      | 8ビット 　       | - 2<sup>7</sup> から 2<sup>7</sup> - 1                                                       |    i8::BITS    | i8::MIN      | i8::MAX      |
| i16     | 16ビット         | - 2<sup>15</sup> から 2<sup>15</sup> - 1                                                     |   i16::BITS    | i16::MIN     | i16::MAX     |
| i32     | 32ビット         | - 2<sup>31</sup> から 2<sup>31</sup> - 1                                                     |   i32::BITS    | i32::MIN     | i32::MAX     |
| i64     | 64ビット         | - 2<sup>63</sup> から 2<sup>63</sup> - 1                                                     |   i64::BITS    | i64::MIN     | i64::MAX     |
| i128    | 128ビット        | - 2<sup>127</sup> から 2<sup>127</sup> - 1                                                   |  i128::BITS    | i128::MIN    | i128::MAX    |
| isize   | 計算機のワード長 | - 2<sup>31</sup> から 2<sup>31</sup> - 1、 もしくは - 2<sup>63</sup> から 2<sup>64</sup> - 1 | isize::BITS    | isize::MIN   | isize::MAX   |

```rust title="signed-integer-type/main.rs"
fn main() {
    println!("   i8のビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}",    i8::BITS,    i8::MIN,    i8::MAX);
    println!("  i16のビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}",   i16::BITS,   i16::MIN,   i16::MAX);
    println!("  i32のビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}",   i32::BITS,   i32::MIN,   i32::MAX);
    println!("  i64のビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}",   i64::BITS,   i64::MIN,   i64::MAX);
    println!(" i128のビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}",  i128::BITS,  i128::MIN,  i128::MAX);
    println!("isizeのビット幅:{:>4}、最小値:{:>41}、最大値:{:>40}", isize::BITS, isize::MIN, isize::MAX);
}
```

```bash title="実行結果"
   i8のビット幅:   8、最小値:                                     -128、最大値:                                     127
  i16のビット幅:  16、最小値:                                   -32768、最大値:                                   32767
  i32のビット幅:  32、最小値:                              -2147483648、最大値:                              2147483647
  i64のビット幅:  64、最小値:                     -9223372036854775808、最大値:                     9223372036854775807
 i128のビット幅: 128、最小値: -170141183460469231731687303715884105728、最大値: 170141183460469231731687303715884105727
isizeのビット幅:  64、最小値:                     -9223372036854775808、最大値:                     9223372036854775807
```

### 整数リテラル

整数リテラルには数値の後ろに型を付ける。38u8はu8の値、4953isizeはisizeになる。また、0x、0o、0bを先頭に付けると、16進数、8進数、2進数のリテラルになる。

| リテラル    | 型  | 10進数 |
| --------    | --- | ------ |
| 52i8        | i8  | 52     |
| 0xcafeu32   | u32 | 51966  |
| 0b0001_0100 | 推論される | 20 |
| 0o105       | 推論される | 69 |

```rust title="integer-literal/main.rs"
fn main() {
    println!("{}", 52i8);
    println!("{}", 0xcafeu32);
    println!("{}", 0b0001_0100);
    println!("{}", 0o105);    
}
```

```bash title="実行結果"
52
51966
20
69
```

### バイトリテラル

バイトリテラルb'X'は文字Xに対するACSIIコードのu8の値となる。
バイトリテラルはb'\xHH'のように16進数で書くこともできる。HHは値を表す16進数2文字である。

| 文字              | バイトリテラル  | バイトリテラル（16進表記） | 対応する数値リテラル |
| ----------------- | --------------- | -------------------------- | -------------------- |
| 英小文字a         | b'a'            | b'\x61'                    | 97u8                 |
| 英小文字b         | b'b'            | b'\x62'                    | 98u8                 |
| 英小文字c         | b'c'            | b'\x63'                    | 99u8                 |
| 英大文字A         | b'A'            | b'\x41'                    | 65u8                 |
| 英大文字B         | b'B'            | b'\x42'                    | 66u8                 |
| 英大文字C         | b'C'            | b'\x43'                    | 67u8                 |
| シングルクォート' | b'\' '          | b'\x27'                    | 39u8                 |
| バックスラッシュ\ | b'\\'           | b'\x5C'                    | 92u8                 |
| 改行              | b'\n'           | b'\x0A'                    | 10u8                 |

```rust title="byte-literal/main.rs"
fn main() {
    println!("{},{},{}", b'a'   , b'b'   , b'c'   );
    println!("{},{},{}", b'A'   , b'B'   , b'C'   );
    println!("{},{},{}", b'\''  , b'\\'  , b'\n'  );
    println!("{},{},{}", b'\x61', b'\x62', b'\x63');
    println!("{},{},{}", b'\x41', b'\x42', b'\x43');
    println!("{},{},{}", b'\x27', b'\x5C', b'\x0A');
}
```

```bash title="実行結果"
97,98,99
65,66,67
39,92,10
97,98,99
65,66,67
39,92,10
```

## 整数型に定義されたメソッド

### チェック付き演算

演算した結果をOption型として返します。オーバーフローが発生しなければ演算結果をvとしてSome(v)を返し、発生すればNoneを返します。

- [x] checked_add

=== "u8"

    ```rust
    // u8::MAX - 1に1を足すとu8::MAXとなりオーバーフローは発生しないのでSome(u8::MAX)が返ります。
    assert_eq!((u8::MAX - 1).checked_add(1), Some(u8::MAX));
    // u8::MAX - 1に2を足すとu8::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u8::MAX - 1).checked_add(2), None);
    ```

=== "u16"

    ```rust
    // u16::MAX - 1に1を足すとu16::MAXとなりオーバーフローは発生しないのでSome(u16::MAX)が返ります。
    assert_eq!((u16::MAX - 1).checked_add(1), Some(u16::MAX));
    // u16::MAX - 1に2を足すとu16::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u16::MAX - 1).checked_add(2), None);
    ```

=== "u32"

    ```rust
    // u32::MAX - 1に1を足すとu32::MAXとなりオーバーフローは発生しないのでSome(u32::MAX)が返ります。
    assert_eq!((u32::MAX - 1).checked_add(1), Some(u32::MAX));
    // u32::MAX - 1に2を足すとu32::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u32::MAX - 1).checked_add(2), None);
    ```

=== "u64"

    ```rust
    // u64::MAX - 1に1を足すとu64::MAXとなりオーバーフローは発生しないのでSome(u64::MAX)が返ります。
    assert_eq!((u64::MAX - 1).checked_add(1), Some(u64::MAX));
    // u64::MAX - 1に2を足すとu64::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u64::MAX - 1).checked_add(2), None);
    ```

=== "u128"

    ```rust
    // u128::MAX - 1に1を足すとu128::MAXとなりオーバーフローは発生しないのでSome(u128::MAX)が返ります。
    assert_eq!((u128::MAX - 1).checked_add(1), Some(u128::MAX));
    // u128::MAX - 1に2を足すとu128::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u128::MAX - 1).checked_add(2), None);
    ```

=== "i8"

    ```rust
    // i8::MAX - 1に1を足すとi8::MAXとなりオーバーフローは発生しないのでSome(i8::MAX)が返ります。
    assert_eq!((i8::MAX - 1).checked_add(1), Some(i8::MAX));
    // i8::MAX - 1に2を足すとi8::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i8::MAX - 1).checked_add(2), None);
    ```

=== "i16"

    ```rust
    // i16::MAX - 1に1を足すとi16::MAXとなりオーバーフローは発生しないのでSome(i16::MAX)が返ります。
    assert_eq!((i16::MAX - 1).checked_add(1), Some(i16::MAX));
    // i16::MAX - 1に2を足すとi16::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i16::MAX - 1).checked_add(2), None);
    ```

=== "i32"

    ```rust
    // i32::MAX - 1に1を足すとi32::MAXとなりオーバーフローは発生しないのでSome(i32::MAX)が返ります。
    assert_eq!((i32::MAX - 1).checked_add(1), Some(i32::MAX));
    // i32::MAX - 1に2を足すとi32::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i32::MAX - 1).checked_add(2), None);
    ```

=== "i64"

    ```rust
    // i64::MAX - 1に1を足すとi64::MAXとなりオーバーフローは発生しないのでSome(i64::MAX)が返ります。
    assert_eq!((i64::MAX - 1).checked_add(1), Some(i64::MAX));
    // i64::MAX - 1に2を足すとi64::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i64::MAX - 1).checked_add(2), None);
    ```

=== "i128"

    ```rust
    // i128::MAX - 1に1を足すとi128::MAXとなりオーバーフローは発生しないのでSome(i128::MAX)が返ります。
    assert_eq!((i128::MAX - 1).checked_add(1), Some(i128::MAX));
    // i128::MAX - 1に2を足すとi128::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i128::MAX - 1).checked_add(2), None);
    ```

- [x] checked_sub

=== "u8"

    ```rust
    // u8::MIN - 1から1を引くとu8::MINとなりオーバーフローは発生しないのでSome(u8::MIN)が返ります。
    assert_eq!((u8::MIN + 1).checked_sub(1), Some(u8::MIN));
    // u8::MIN - 1から2を引くとu8::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u8::MIN + 1).checked_sub(2), None);
    ```

=== "u16"

    ```rust
    // u16::MIN - 1から1を引くとu16::MINとなりオーバーフローは発生しないのでSome(u16::MIN)が返ります。
    assert_eq!((u16::MIN + 1).checked_sub(1), Some(u16::MIN));
    // u16::MIN - 1から2を引くとu16::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u16::MIN + 1).checked_sub(2), None);
    ```

=== "u32"

    ```rust
    // u32::MIN - 1から1を引くとu32::MINとなりオーバーフローは発生しないのでSome(u32::MIN)が返ります。
    assert_eq!((u32::MIN + 1).checked_sub(1), Some(u32::MIN));
    // u32::MIN - 1から2を引くとu32::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u32::MIN + 1).checked_sub(2), None);
    ```

=== "u64"

    ```rust
    // u64::MIN - 1から1を引くとu64::MINとなりオーバーフローは発生しないのでSome(u64::MIN)が返ります。
    assert_eq!((u64::MIN + 1).checked_sub(1), Some(u64::MIN));
    // u64::MIN - 1から2を引くとu64::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u64::MIN + 1).checked_sub(2), None);
    ```

=== "u128"

    ```rust
    // u128::MIN - 1から1を引くとu128::MINとなりオーバーフローは発生しないのでSome(u128::MIN)が返ります。
    assert_eq!((u128::MIN + 1).checked_sub(1), Some(u128::MIN));
    // u128::MIN - 1から2を引くとu128::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u128::MIN + 1).checked_sub(2), None);
    ```

=== "i8"

    ```rust
    // i8::MIN - 1から1を引くとi8::MINとなりオーバーフローは発生しないのでSome(i8::MIN)が返ります。
    assert_eq!((i8::MIN + 1).checked_sub(1), Some(i8::MIN));
    // i8::MIN - 1から2を引くとi8::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i8::MIN + 1).checked_sub(2), None);
    ```

=== "i16"

    ```rust
    // i16::MIN - 1から1を引くとi16::MINとなりオーバーフローは発生しないのでSome(i16::MIN)が返ります。
    assert_eq!((i16::MIN + 1).checked_sub(1), Some(i16::MIN));
    // i16::MIN - 1から2を引くとi16::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i16::MIN + 1).checked_sub(2), None);
    ```

=== "i32"

    ```rust
    // i32::MIN - 1から1を引くとi32::MINとなりオーバーフローは発生しないのでSome(i32::MIN)が返ります。
    assert_eq!((i32::MIN + 1).checked_sub(1), Some(i32::MIN));
    // i32::MIN - 1から2を引くとi32::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i32::MIN + 1).checked_sub(2), None);
    ```

=== "i64"

    ```rust
    // i64::MIN - 1から1を引くとi64::MINとなりオーバーフローは発生しないのでSome(i64::MIN)が返ります。
    assert_eq!((i64::MIN + 1).checked_sub(1), Some(i64::MIN));
    // i64::MIN - 1から2を引くとi64::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i64::MIN + 1).checked_sub(2), None);
    ```

=== "i128"

    ```rust
    // i128::MIN - 1から1を引くとi128::MINとなりオーバーフローは発生しないのでSome(i128::MIN)が返ります。
    assert_eq!((i128::MIN + 1).checked_sub(1), Some(i128::MIN));
    // i128::MIN - 1から2を引くとi128::MIN - 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i128::MIN + 1).checked_sub(2), None);
    ```

- [x] checked_mul

=== "u8"

    ```rust
    // u8::MAXに1をかけるとu8::MAXとなりオーバーフローは発生しないのでSome(u8::MAX)が返ります。
    assert_eq!((u8::MAX).checked_mul(1), Some(u8::MAX));
    // u8::MAXに2をかけるとu8::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u8::MAX).checked_mul(2), None);
    ```

=== "u16"

    ```rust
    // u16::MAXに1をかけるとu16::MAXとなりオーバーフローは発生しないのでSome(u16::MAX)が返ります。
    assert_eq!((u16::MAX).checked_mul(1), Some(u16::MAX));
    // u16::MAXに2をかけるとu16::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u16::MAX).checked_mul(2), None);
    ```

=== "u32"

    ```rust
    // u32::MAXに1をかけるとu32::MAXとなりオーバーフローは発生しないのでSome(u32::MAX)が返ります。
    assert_eq!((u32::MAX).checked_mul(1), Some(u32::MAX));
    // u32::MAXに2をかけるとu32::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u32::MAX).checked_mul(2), None);
    ```

=== "u64"

    ```rust
    // u64::MAXに1をかけるとu64::MAXとなりオーバーフローは発生しないのでSome(u64::MAX)が返ります。
    assert_eq!((u64::MAX).checked_mul(1), Some(u64::MAX));
    // u64::MAXに2をかけるとu64::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u64::MAX).checked_mul(2), None);
    ```

=== "u128"

    ```rust
    // u128::MAXに1をかけるとu128::MAXとなりオーバーフローは発生しないのでSome(u128::MAX)が返ります。
    assert_eq!((u128::MAX).checked_mul(1), Some(u128::MAX));
    // u128::MAXに2をかけるとu128::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((u128::MAX).checked_mul(2), None);
    ```

=== "i8"

    ```rust
    // i8::MAXに1をかけるとi8::MAXとなりオーバーフローは発生しないのでSome(i8::MAX)が返ります。
    assert_eq!((i8::MAX).checked_mul(1), Some(i8::MAX));
    // i8::MAXに2をかけるとi8::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i8::MAX).checked_mul(2), None);
    ```

=== "i16"

    ```rust
    // i16::MAXに1をかけるとi16::MAXとなりオーバーフローは発生しないのでSome(i16::MAX)が返ります。
    assert_eq!((i16::MAX).checked_mul(1), Some(i16::MAX));
    // i16::MAXに2をかけるとi16::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i16::MAX).checked_mul(2), None);
    ```

=== "i32"

    ```rust
    // i32::MAXに1をかけるとi32::MAXとなりオーバーフローは発生しないのでSome(i32::MAX)が返ります。
    assert_eq!((i32::MAX).checked_mul(1), Some(i32::MAX));
    // i32::MAXに2をかけるとi32::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i32::MAX).checked_mul(2), None);
    ```

=== "i64"

    ```rust
    // i64::MAXに1をかけるとi64::MAXとなりオーバーフローは発生しないのでSome(i64::MAX)が返ります。
    assert_eq!((i64::MAX).checked_mul(1), Some(i64::MAX));
    // i64::MAXに2をかけるとi64::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i64::MAX).checked_mul(2), None);
    ```

=== "i128"

    ```rust
    // i128::MAXに1をかけるとi128::MAXとなりオーバーフローは発生しないのでSome(i128::MAX)が返ります。
    assert_eq!((i128::MAX).checked_mul(1), Some(i128::MAX));
    // i128::MAXに2をかけるとi128::MAX * 2となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i128::MAX).checked_mul(2), None);
    ```

- [x] checked_div

=== "u8"

    ```rust
    // 128u8を2で割ると64となりオーバーフローは発生しないので64が返ります。
    assert_eq!(128u8.checked_div(2), Some(64u8));
    // 0での除算はNoneが返ります。
    assert_eq!(1u8.checked_div(0), None);
    ```

=== "u16"

    ```rust
    // 128u16を2で割ると64となりオーバーフローは発生しないので64が返ります。
    assert_eq!(128u16.checked_div(2), Some(64u16));
    // 0での除算はNoneが返ります。
    assert_eq!(1u16.checked_div(0), None);
    ```

=== "u32"

    ```rust
    // 128u32を2で割ると64となりオーバーフローは発生しないので64が返ります。
    assert_eq!(128u32.checked_div(2), Some(64u32));
    // 0での除算はNoneが返ります。
    assert_eq!(1u32.checked_div(0), None);
    ```

=== "u64"

    ```rust
    // 128u64を2で割ると64となりオーバーフローは発生しないので64が返ります。
    assert_eq!(128u64.checked_div(2), Some(64u64));
    // 0での除算はNoneが返ります。
    assert_eq!(1u64.checked_div(0), None);
    ```

=== "u128"

    ```rust
    // 128u128を2で割ると64となりオーバーフローは発生しないので64が返ります。
    assert_eq!(128u128.checked_div(2), Some(64u128));
    // 0での除算はNoneが返ります。
    assert_eq!(1u128.checked_div(0), None);
    ```

=== "i8"

    ```rust
    // i8::MAXを-1で割るとi8::MIN + 1となりオーバーフローは発生しないのでSome(i8::MIN + 1)が返ります。
    assert_eq!((i8::MAX).checked_div(-1), Some(i8::MIN + 1));
    // i8::MINを-1で割るとi8::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i8::MIN).checked_div(-1), None);
    // 0での除算はNoneが返ります。
    assert_eq!((1i8).checked_div(0), None);
    ```

=== "i16"

    ```rust
    // i16::MAXを-1で割るとi16::MIN + 1となりオーバーフローは発生しないのでSome(i16::MIN + 1)が返ります。
    assert_eq!((i16::MAX).checked_div(-1), Some(i16::MIN + 1));
    // i16::MINを-1で割るとi16::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i16::MIN).checked_div(-1), None);
    // 0での除算はNoneが返ります。
    assert_eq!((1i16).checked_div(0), None);
    ```

=== "i32"

    ```rust
    // i32::MAXを-1で割るとi32::MIN + 1となりオーバーフローは発生しないのでSome(i32::MIN + 1)が返ります。
    assert_eq!((i32::MAX).checked_div(-1), Some(i32::MIN + 1));
    // i32::MINを-1で割るとi32::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i32::MIN).checked_div(-1), None);
    // 0での除算はNoneが返ります。
    assert_eq!((1i32).checked_div(0), None);
    ```

=== "i64"

    ```rust
    // i64::MAXを-1で割るとi64::MIN + 1となりオーバーフローは発生しないのでSome(i64::MIN + 1)が返ります。
    assert_eq!((i64::MAX).checked_div(-1), Some(i64::MIN + 1));
    // i64::MINを-1で割るとi64::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i64::MIN).checked_div(-1), None);
    // 0での除算はNoneが返ります。
    assert_eq!((1i64).checked_div(0), None);
    ```

=== "i128"

    ```rust
    // i128::MAXを-1で割るとi128::MIN + 1となりオーバーフローは発生しないのでSome(i128::MIN + 1)が返ります。
    assert_eq!((i128::MAX).checked_div(-1), Some(i128::MIN + 1));
    // i128::MINを-1で割るとi128::MAX + 1となりオーバーフローが発生するのでNoneが返ります。
    assert_eq!((i128::MIN).checked_div(-1), None);
    // 0での除算はNoneが返ります。
    assert_eq!((1i128).checked_div(0), None);
    ```

- [x] checked_div_euclid

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_rem

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_rem_euclid

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_shl

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_shr

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_pow

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

- [x] checked_neg

TODO

=== "u8"

    ```rust
    ```

=== "u16"

    ```rust
    ```

=== "u32"

    ```rust
    ```

=== "u64"

    ```rust
    ```

=== "u128"

    ```rust
    ```

=== "i8"

    ```rust
    ```

=== "i16"

    ```rust
    ```

=== "i32"

    ```rust
    ```

=== "i64"

    ```rust
    ```

=== "i128"

    ```rust
    ```

### ラップ演算

TODO

### 飽和演算

TODO

### オーバーフロー演算

TODO

## 浮動小数点型

IEEE754規格準拠の単精度と倍精度の浮動小数点数をサポートしています。f32が単精度、f64が倍精度に対応しています。

| 型  | 精度          | 範囲                                                                          | 最小値の取得 | 最大値の取得 |
| --- | ------------- | ----------------------------------------------------------------------------- | -------------| ------------ |
| f32 | IEEE754単精度 | -3.4028235×10<sup>38</sup>から3.4028235×10<sup>38</sup>                     | f32::MIN     | f32::MAX     |
| f64 | IEEE754倍精度 | -1.7976931348623157×10<sup>308</sup>から1.7976931348623157×10<sup>308</sup> | f64::MIN     | f64::MAX     |

```rust title="floating-point-type/main.rs"
fn main() {
    println!("f32型の最小値:{:e}、最大値:{:e}", f32::MIN, f32::MAX);
    println!("{},{}", f32::NEG_INFINITY, f32::INFINITY);
    println!("f64型の最小値:{:e}、最大値:{:e}", f64::MIN, f64::MAX);
    println!("{},{}", f64::NEG_INFINITY, f64::INFINITY);
}
```

```bash title="実行結果"
f32型の最小値:-3.4028235e38、最大値:3.4028235e38
-inf,inf
f64型の最小値:-1.7976931348623157e308、最大値:1.7976931348623157e308
-inf,inf
```
