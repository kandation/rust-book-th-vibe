## การติดตั้ง

ขั้นตอนแรกคือการติดตั้ง Rust เราจะดาวน์โหลด Rust ผ่าน `rustup` ซึ่งเป็นเครื่องมือบรรทัดคำสั่งสำหรับจัดการเวอร์ชัน Rust และเครื่องมือที่เกี่ยวข้อง คุณจะต้องเชื่อมต่ออินเทอร์เน็ตเพื่อดาวน์โหลด

> หมายเหตุ: หากคุณไม่ต้องการใช้ `rustup` ด้วยเหตุผลบางประการ โปรดดูหน้า [วิธีการติดตั้ง Rust อื่นๆ][otherinstall] สำหรับตัวเลือกเพิ่มเติม

ขั้นตอนต่อไปนี้เป็นการติดตั้งคอมไพเลอร์ Rust เวอร์ชันเสถียรล่าสุด การรับประกันความเสถียรของ Rust ช่วยให้มั่นใจได้ว่าตัวอย่างทั้งหมดในหนังสือที่คอมไพล์ได้จะยังคงคอมไพล์ได้กับ Rust เวอร์ชันใหม่กว่า ผลลัพธ์อาจแตกต่างกันเล็กน้อยระหว่างเวอร์ชัน เนื่องจาก Rust มักจะปรับปรุงข้อความแสดงข้อผิดพลาดและคำเตือนอยู่เสมอ กล่าวอีกนัยหนึ่งคือ Rust เวอร์ชันเสถียรที่ใหม่กว่าใดๆ ที่คุณติดตั้งโดยใช้ขั้นตอนเหล่านี้ควรทำงานตามที่คาดไว้กับเนื้อหาของหนังสือเล่มนี้

> ### สัญกรณ์บรรทัดคำสั่ง
>
> ในบทนี้และตลอดทั้งเล่ม เราจะแสดงคำสั่งบางอย่างที่ใช้ในเทอร์มินัล บรรทัดที่คุณควรป้อนในเทอร์มินัลทั้งหมดจะขึ้นต้นด้วย `$` คุณไม่จำเป็นต้องพิมพ์อักขระ `$` มันคือพรอมต์บรรทัดคำสั่งที่แสดงเพื่อระบุการเริ่มต้นของแต่ละคำสั่ง บรรทัดที่ไม่ได้ขึ้นต้นด้วย `$` โดยทั่วไปจะแสดงผลลัพธ์ของคำสั่งก่อนหน้า นอกจากนี้ ตัวอย่างเฉพาะสำหรับ PowerShell จะใช้ `>` แทน `$`

### การติดตั้ง `rustup` บน Linux หรือ macOS

หากคุณใช้ Linux หรือ macOS ให้เปิดเทอร์มินัลแล้วป้อนคำสั่งต่อไปนี้:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

คำสั่งนี้จะดาวน์โหลดสคริปต์และเริ่มการติดตั้งเครื่องมือ `rustup` ซึ่งจะติดตั้ง Rust เวอร์ชันเสถียรล่าสุด คุณอาจถูกขอให้ป้อนรหัสผ่านของคุณ หากการติดตั้งสำเร็จ บรรทัดต่อไปนี้จะปรากฏขึ้น:

```text
Rust is installed now. Great!
```

คุณจะต้องมี _linker_ ด้วย ซึ่งเป็นโปรแกรมที่ Rust ใช้เพื่อรวมผลลัพธ์ที่คอมไพล์แล้วเข้าเป็นไฟล์เดียว มีแนวโน้มว่าคุณมีอยู่แล้ว หากคุณได้รับข้อผิดพลาดเกี่ยวกับ linker คุณควรติดตั้งคอมไพเลอร์ C ซึ่งโดยทั่วไปจะมี linker รวมอยู่ด้วย คอมไพเลอร์ C ยังมีประโยชน์เนื่องจากแพ็กเกจ Rust ทั่วไปบางตัว εξαρτώμαι (depend on) โค้ด C และจะต้องใช้คอมไพเลอร์ C

บน macOS คุณสามารถรับคอมไพเลอร์ C ได้โดยการรัน:

```console
$ xcode-select --install
```

ผู้ใช้ Linux โดยทั่วไปควรติดตั้ง GCC หรือ Clang ตามเอกสารประกอบของ дистрибутив (distribution) ของตน ตัวอย่างเช่น หากคุณใช้ Ubuntu คุณสามารถติดตั้งแพ็กเกจ `build-essential` ได้

### การติดตั้ง `rustup` บน Windows

บน Windows ให้ไปที่ [https://www.rust-lang.org/tools/install][install] และทำตามคำแนะนำในการติดตั้ง Rust ในบางขั้นตอนของการติดตั้ง คุณจะได้รับแจ้งให้ติดตั้ง Visual Studio ซึ่งจะให้ linker และไลบรารีแบบเนทีฟที่จำเป็นในการคอมไพล์โปรแกรม หากคุณต้องการความช่วยเหลือเพิ่มเติมในขั้นตอนนี้ โปรดดู [https://rust-lang.github.io/rustup/installation/windows-msvc.html][msvc]

ส่วนที่เหลือของหนังสือเล่มนี้ใช้คำสั่งที่ทำงานได้ทั้งใน _cmd.exe_ และ PowerShell หากมีความแตกต่างเฉพาะเจาะจง เราจะอธิบายว่าควรใช้อันไหน

### การแก้ไขปัญหา

หากต้องการตรวจสอบว่าคุณติดตั้ง Rust อย่างถูกต้องหรือไม่ ให้เปิดเชลล์แล้วป้อนบรรทัดนี้:

```console
$ rustc --version
```

คุณควรเห็นหมายเลขเวอร์ชัน, commit hash และวันที่ commit สำหรับเวอร์ชันเสถียรล่าสุดที่เผยแพร่แล้ว ในรูปแบบต่อไปนี้:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

หากคุณเห็นข้อมูลนี้ แสดงว่าคุณติดตั้ง Rust สำเร็จแล้ว! หากคุณไม่เห็นข้อมูลนี้ ให้ตรวจสอบว่า Rust อยู่ในตัวแปรระบบ `%PATH%` ของคุณดังนี้

ใน Windows CMD ใช้:

```console
> echo %PATH%
```

ใน PowerShell ใช้:

```powershell
> echo $env:Path
```

ใน Linux และ macOS ใช้:

```console
$ echo $PATH
```

หากทั้งหมดถูกต้องแล้วแต่ Rust ยังคงใช้งานไม่ได้ มีหลายที่ที่คุณสามารถขอความช่วยเหลือได้ ค้นหาวิธีติดต่อกับ Rustaceans คนอื่นๆ (ชื่อเล่นตลกๆ ที่เราเรียกตัวเอง) ได้ที่ [หน้าชุมชน][community]

### การอัปเดตและถอนการติดตั้ง

เมื่อติดตั้ง Rust ผ่าน `rustup` แล้ว การอัปเดตเป็นเวอร์ชันที่เผยแพร่ใหม่นั้นทำได้ง่าย จากเชลล์ของคุณ ให้รันสคริปต์อัปเดตต่อไปนี้:

```console
$ rustup update
```

หากต้องการถอนการติดตั้ง Rust และ `rustup` ให้รันสคริปต์ถอนการติดตั้งต่อไปนี้จากเชลล์ของคุณ:

```console
$ rustup self uninstall
```

### เอกสารประกอบในเครื่อง

การติดตั้ง Rust ยังรวมสำเนาเอกสารประกอบในเครื่องเพื่อให้คุณสามารถอ่านแบบออฟไลน์ได้ รัน `rustup doc` เพื่อเปิดเอกสารประกอบในเครื่องในเบราว์เซอร์ของคุณ

เมื่อใดก็ตามที่มีไทป์หรือฟังก์ชันที่ไลบรารีมาตรฐานมีให้ และคุณไม่แน่ใจว่ามันทำอะไรหรือใช้งานอย่างไร ให้ใช้เอกสารประกอบ Application Programming Interface (API) เพื่อค้นหา!

### โปรแกรมแก้ไขข้อความและ Integrated Development Environments (IDE)

หนังสือเล่มนี้ไม่ได้ตั้งสมมติฐานเกี่ยวกับเครื่องมือที่คุณใช้ในการเขียนโค้ด Rust โปรแกรมแก้ไขข้อความเกือบทุกตัวสามารถทำงานได้! อย่างไรก็ตาม โปรแกรมแก้ไขข้อความและ Integrated Development Environments (IDE) จำนวนมากมีการสนับสนุน Rust ในตัว คุณสามารถค้นหารายชื่อโปรแกรมแก้ไขและ IDE ที่ค่อนข้างเป็นปัจจุบันได้เสมอที่ [หน้าเครื่องมือ][tools] บนเว็บไซต์ Rust

### การทำงานแบบออฟไลน์กับหนังสือเล่มนี้

ในหลายตัวอย่าง เราจะใช้แพ็กเกจ Rust นอกเหนือจากไลบรารีมาตรฐาน ในการทำงานผ่านตัวอย่างเหล่านั้น คุณจะต้องมีการเชื่อมต่ออินเทอร์เน็ตหรือดาวน์โหลด εξάρτηση (dependencies) เหล่านั้นล่วงหน้า หากต้องการดาวน์โหลด εξάρτηση (dependencies) ล่วงหน้า คุณสามารถรันคำสั่งต่อไปนี้ได้ (เราจะอธิบายรายละเอียดว่า `cargo` คืออะไรและแต่ละคำสั่งเหล่านี้ทำอะไรในภายหลัง)

```console
$ cargo new get-dependencies
$ cd get-dependencies
$ cargo add rand@0.8.5 trpl@0.2.0
```

สิ่งนี้จะแคชการดาวน์โหลดสำหรับแพ็กเกจเหล่านี้ เพื่อที่คุณจะไม่ต้องดาวน์โหลดในภายหลัง เมื่อคุณรันคำสั่งนี้แล้ว คุณไม่จำเป็นต้องเก็บโฟลเดอร์ `get-dependencies` ไว้ หากคุณรันคำสั่งนี้แล้ว คุณสามารถใช้แฟล็ก `--offline` กับคำสั่ง `cargo` ทั้งหมดในส่วนที่เหลือของหนังสือเพื่อใช้เวอร์ชันที่แคชไว้เหล่านี้แทนที่จะพยายามใช้เครือข่าย

[otherinstall]: https://forge.rust-lang.org/infra/other-installation-methods.html
[install]: https://www.rust-lang.org/tools/install
[msvc]: https://rust-lang.github.io/rustup/installation/windows-msvc.html
[community]: https://www.rust-lang.org/community
[tools]: https://www.rust-lang.org/tools
