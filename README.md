# ระบบ CRUD ด้วย HTML, JavaScript และ PocketBase

ระบบจัดการข้อมูลแบบ CRUD (Create, Read, Update, Delete) ที่ใช้ HTML, JavaScript และ PocketBase เป็นฐานข้อมูล

## คุณสมบัติ

- 📝 **หน้าบันทึกข้อมูล** - เพิ่มข้อมูลใหม่ลงในระบบ
- 📊 **หน้าแดชบอร์ด** - แสดงข้อมูลทั้งหมดพร้อมสถิติ
- 🔍 **ค้นหาและกรองข้อมูล** - ค้นหาตามชื่อ, อีเมล หรือกรองตามหมวดหมู่
- ✏️ **แก้ไขข้อมูล** - แก้ไขข้อมูลที่มีอยู่
- 🗑️ **ลบข้อมูล** - ลบข้อมูลที่ไม่ต้องการ
- 📱 **Responsive Design** - ใช้งานได้ทั้งบนมือถือและคอมพิวเตอร์

## การติดตั้งและใช้งาน

### 1. ติดตั้ง PocketBase

1. ดาวน์โหลด PocketBase จาก [https://pocketbase.io/](https://pocketbase.io/)
2. แตกไฟล์และรัน PocketBase server:
   \`\`\`bash
   ./pocketbase serve
   \`\`\`
3. เปิดเบราว์เซอร์ไปที่ `http://127.0.0.1:8090/_/` เพื่อเข้าสู่ Admin UI

### 2. สร้าง Collection

1. ใน PocketBase Admin UI ให้สร้าง Collection ใหม่ชื่อ `contacts`
2. เพิ่ม Fields ดังนี้:
   - `name` (Text) - Required
   - `email` (Email) - Required, Unique
   - `phone` (Text) - Optional
   - `category` (Select) - Options: customer, supplier, employee, other
   - `notes` (Text) - Optional

### 3. รันเว็บไซต์

1. วางไฟล์ทั้งหมดในโฟลเดอร์เว็บเซิร์ฟเวอร์ของคุณ
2. เปิดไฟล์ `index.html` ในเบราว์เซอร์
3. หรือใช้ Live Server extension ใน VS Code

## โครงสร้างไฟล์

\`\`\`
├── index.html          # หน้าบันทึกข้อมูล
├── dashboard.html      # หน้าแดชบอร์ด
├── js/
│   ├── config.js       # การตั้งค่า PocketBase
│   ├── crud.js         # ฟังก์ชันสำหรับบันทึกข้อมูล
│   └── dashboard.js    # ฟังก์ชันสำหรับแดชบอร์ด
└── README.md          # คู่มือการใช้งาน
\`\`\`

## การปรับแต่ง

### เปลี่ยน URL ของ PocketBase

แก้ไขไฟล์ `js/config.js`:
\`\`\`javascript
const POCKETBASE_URL = 'http://your-pocketbase-url:8090';
\`\`\`

### เปลี่ยนชื่อ Collection

แก้ไขไฟล์ `js/config.js`:
\`\`\`javascript
const COLLECTION_NAME = 'your_collection_name';
\`\`\`

## การใช้งาน

1. **เพิ่มข้อมูล**: ไปที่หน้า `index.html` กรอกข้อมูลและกดบันทึก
2. **ดูข้อมูล**: ไปที่หน้า `dashboard.html` เพื่อดูข้อมูลทั้งหมด
3. **ค้นหา**: ใช้ช่องค้นหาในหน้าแดชบอร์ด
4. **กรองข้อมูล**: เลือกหมวดหมู่ที่ต้องการดู
5. **แก้ไข**: กดปุ่ม "แก้ไข" ในตารางข้อมูล
6. **ลบ**: กดปุ่ม "ลบ" ในตารางข้อมูล

## ข้อกำหนดระบบ

- เบราว์เซอร์ที่รองรับ ES6+ (Chrome, Firefox, Safari, Edge)
- PocketBase Server ที่รันอยู่
- การเชื่อมต่ออินเทอร์เน็ต (สำหรับโหลด PocketBase SDK)

## การแก้ไขปัญหา

### ไม่สามารถเชื่อมต่อ PocketBase ได้
- ตรวจสอบว่า PocketBase Server รันอยู่
- ตรวจสอบ URL ในไฟล์ `config.js`
- ตรวจสอบ CORS settings ใน PocketBase

### Collection ไม่พบ
- ตรวจสอบว่าสร้าง Collection ชื่อ `contacts` แล้ว
- ตรวจสอบชื่อ Collection ในไฟล์ `config.js`

## License

MIT License - ใช้งานได้อย่างอิสระ
