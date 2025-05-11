## 📌 역설계를 통한 전파분석 소프트웨어 GUI 개발
기존에 개발된 전파분석 시뮬레이션 시스템을 역설계하여 WPF 기반으로 다시 구현한 프로젝트입니다. <br>
개발 기간 : 2024.09 ~ 2024.11 <br>
사용 기술 : C, C++, WPF, DevExpress <br>
개발 인원 : 1명 <br>

#

### 📖 프로젝트 개요

- 일학습병행 기업현장훈련(OJT) 중 수행한 과제
- 회사에서 개발한 기존 프로그램을 분석하여 주요 기능과 UI를 동일하게 구현
- 제한된 시간 내 요구사항 분석 및 일부 기능 구현에 초점
- SW 개발 프로세스 일부 적용:  
  `요구사항 분석 → (설계 생략) → 구현 → 테스트`

#

### 🧑‍💻 역할 및 기여

- 기존 프로그램의 UI 구조 분석
- 주요 화면의 기능 요구사항 도출
- WPF + DevExpress를 사용해 유사한 UI 구현
- SQLite 데이터베이스 연동 및 테스트 수행
- 엑셀 파일 업로드 및 DB 저장 기능 개발

#

<!--
### 💻 주요 기능 및 코드 설명

#### 1. UI 구성 (WPF + DevExpress)

MainWindow.xaml

DevExpress의 SimpleButton을 사용해 사용자 친화적 UI를 구성했습니다.

#### 2. Excel 업로드 → DB 저장
// UploadExcel_Click.cs
OpenFileDialog openFileDialog = new OpenFileDialog();
if (openFileDialog.ShowDialog() == true)
{
    string filePath = openFileDialog.FileName;
    // Excel 처리 로직
    SaveToDatabase(parsedData);
}
엑셀 파일을 선택하면 내부 데이터를 파싱하고 SQLite에 저장합니다.

#### 3. SQLite 데이터베이스 연동
// SQLite 연결 (C++)
sqlite3* db;
int rc = sqlite3_open("rf_data.db", &db);
if (rc) {
    fprintf(stderr, "DB 연결 실패: %s\n", sqlite3_errmsg(db));
} else {
    fprintf(stdout, "DB 연결 성공\n");
}
기존 데이터를 관리하고 시뮬레이션 결과 저장을 위해 SQLite 사용. SQLiteSpy로 데이터 확인 가능.

#### 4. NuGet 패키지 활용
DevExpress.Wpf
Microsoft.Data.Sqlite
ExcelDataReader (엑셀 파싱용)
Visual Studio의 NuGet을 통해 외부 라이브러리를 편리하게 관리했습니다.

-->


### 🗂️ 프로젝트 구조
```
PBLProject
├── MainWindow.xaml
├── MfcDll/                  # 주요 DLL 파일들
├── PBL.sln                  # 솔루션 파일
├── x64/                     # 빌드된 바이너리 파일
└── lib/                     # 라이브러리 파일
```
#

### 🧪 테스트 및 결과
엑셀 업로드 → 파싱 및 SQLite 저장 정상 작동
UI 구성과 기능 동작이 기존 프로그램과 유사함을 확인
MFC DLL 연동을 통해 기본 분석 기능 일부 작동 확인

#

### ✍️ 회고
제한된 시간과 경험 안에서 역설계를 시도하며 기능을 구조적으로 분석하고 구현하는 능력을 키울 수 있었습니다.
실무 소프트웨어의 규모와 복잡성을 이해하는 데 큰 도움이 되었습니다.
